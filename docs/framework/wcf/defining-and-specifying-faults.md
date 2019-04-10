---
title: Definizione e specifica degli errori
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling faults [WCF], specifying
- handling faults [WCF], defining
ms.assetid: c00c84f1-962d-46a7-b07f-ebc4f80fbfc1
ms.openlocfilehash: 24c05bf41152fba2f54636cd0c15dde6fa71aa2b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299331"
---
# <a name="defining-and-specifying-faults"></a>Definizione e specifica degli errori
Gli errori SOAP forniscono informazioni sulla condizione di errore da un servizio a un client e, nel caso duplex, da un client a un servizio in modo interoperativo. In questo argomento viene illustrato quando e come definire il contenuto di un errore personalizzato e specificare quali operazioni possono restituire tale contenuto. Per altre informazioni sul modo in cui un servizio o un client duplex può inviare tali errori e il modo in cui un'applicazione client o servizio gestisce questi errori, vedere [Sending and Receiving Faults](../../../docs/framework/wcf/sending-and-receiving-faults.md). Per una panoramica di gestione degli errori nelle applicazioni Windows Communication Foundation (WCF), vedere [se si specifica e gestione degli errori in contratti e servizi](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## <a name="overview"></a>Panoramica  
 Gli errori SOAP dichiarati sono quelli in cui un'operazione presenta un <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> che specifica un tipo di errore SOAP personalizzato. Gli errori SOAP non dichiarati sono quelli che non vengono specificati nel contratto per un'operazione. In questo argomento viene illustrato come identificare tali condizioni di errore e creare un contratto di errore per il servizio che i client possono usare per gestire correttamente tali condizioni di errore quando vengono segnalate dagli errori SOAP personalizzati. Le attività di base sono descritte di seguito, in ordine progressivo:  
  
1. Definire le condizioni di errore che un client del servizio deve conoscere.  
  
2. Definire il contenuto personalizzato degli errori SOAP per tali condizioni di errore.  
  
3. Contrassegnare le operazioni in modo che gli specifici errori SOAP generati vengano esposti ai client in WSDL.  
  
### <a name="defining-error-conditions-that-clients-should-know-about"></a>Definizione delle condizioni di errore che i client devono conoscere  
 Gli errori SOAP sono messaggi descritti pubblicamente che contengono informazioni sugli errori per una particolare operazione. Poiché vengono descritti insieme ad altri messaggi dell'operazione in WSDL, i client sono al corrente di tali errori e, pertanto, sono pronti a gestirli quando richiamano un'operazione. Tuttavia, poiché i servizi WCF sono scritti in codice gestito, decidere quale errore condizioni nel codice gestito devono essere convertite in errori e restituite al client offre la possibilità di separare le condizioni di errore e i bug del servizio dall'errore formale sostenute con un client.  
  
 Ad esempio, nell'esempio di codice seguente è mostrata un'operazione che accetta due numeri interi e restituisce un altro numero intero. In questo caso possono essere generate molte eccezioni, pertanto quando si progetta il contratto di errori, è necessario determinare quali condizioni di errore sono importanti per il client. In questo caso, il servizio deve rilevare l'eccezione <xref:System.DivideByZeroException?displayProperty=nameWithType>.  
  
```csharp  
[ServiceContract]  
public class CalculatorService  
{  
    [OperationContract]   
    int Divide(int a, int b)  
    {  
      if (b==0) throw new Exception("Division by zero!");  
      return a/b;  
    }  
}  
```  
  
```vb  
<ServiceContract> _  
Public Class CalculatorService  
    <OperationContract]> _  
    Public Function Divide(ByVal a As Integer, ByVal b As Integer) _  
       As Integer  
      If (b==0) Then   
            Throw New Exception("Division by zero!")  
      Return a/b  
    End Function  
End Class  
```  
  
 Nell'esempio precedente l'operazione può restituire un errore SOAP personalizzato che sia specifico della divisione per zero, un errore personalizzato che sia specifico per le operazioni di matematica ma contenga informazioni specifiche per la divisione per zero, più errori per diverse situazioni di errore o nessun errore SOAP.  
  
### <a name="define-the-content-of-error-conditions"></a>Definire il contenuto delle condizioni di errore  
 Dopo aver identificato una condizione di errore adatta per restituire un errore SOAP personalizzato, il passaggio successivo consiste nel definire il contenuto di tale errore e verificare che la struttura del contenuto possa essere serializzata. L'esempio di codice nella sezione precedente mostra un errore specifico per un'operazione `Divide`. Tuttavia se nel servizio `Calculator` sono presenti altre operazioni, un solo errore SOAP personalizzato può informare il client di tutte le condizioni di errore della calcolatrice, inclusa l'operazione `Divide`. Nell'esempio di codice seguente viene illustrata la creazione di un errore SOAP personalizzato, `MathFault`, che può segnalare gli errori generati usando tutte le operazioni di matematica, inclusa l'operazione `Divide`. Mentre la classe può specificare un'operazione (la proprietà `Operation` ) e un valore che descrivono il problema (la proprietà `ProblemType` ), è necessario che la classe e queste proprietà siano serializzabili per essere trasferite al client in un errore SOAP personalizzato. Pertanto, gli attributi <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType> e <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType> vengono usati per rendere il tipo e le relative proprietà serializzabili e interoperativi.  
  
 [!code-csharp[Faults#2](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#2)]
 [!code-vb[Faults#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#2)]  
  
 Per altre informazioni su come verificare che i dati è serializzabili, vedere [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md). Per un elenco della serializzazione che supportano <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> offre, vedere [tipi supportati dal serializzatore dei contratti dati](../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
### <a name="mark-operations-to-establish-the-fault-contract"></a>Contrassegnare le operazioni per stabilire il contratto di errore  
 Dopo aver definito una struttura di dati serializzabile che viene restituita come parte di un errore SOAP personalizzato, l'ultimo passaggio consiste nel contrassegnare il contratto dell'operazione per indicare che genera un errore SOAP di quel tipo. Per questo scopo, usare l'attributo <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> e passare il tipo di dati personalizzato costruito. Nell'esempio di codice seguente viene illustrato come usare l'attributo <xref:System.ServiceModel.FaultContractAttribute> per specificare che l'operazione `Divide` può restituire un errore SOAP di tipo `MathFault`. In questo modo anche le altre operazioni matematiche possono specificare che restituiscono un `MathFault`.  
  
 [!code-csharp[Faults#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#1)]
 [!code-vb[Faults#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#1)]  
  
 È possibile specificare che un'operazione restituisce più di un errore personalizzato contrassegnando tale operazione con più attributi <xref:System.ServiceModel.FaultContractAttribute>.  
  
 Il passaggio successivo, per implementare il contratto di errore nell'implementazione dell'operazione, è descritto nell'argomento [Sending and Receiving Faults](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
#### <a name="soap-wsdl-and-interoperability-considerations"></a>Considerazioni su SOAP, WSDL e sull'interoperabilità  
 In alcune circostanze, specialmente quando si interagisce con altre piattaforme, può essere importante controllare il modo in cui un errore viene visualizzato in un messaggio SOAP o il modo in cui viene descritto nei metadati WSDL.  
  
 L'attributo <xref:System.ServiceModel.FaultContractAttribute> dispone della proprietà <xref:System.ServiceModel.FaultContractAttribute.Name%2A> che consente di controllare il nome dell'elemento di errore WSDL generato nei metadati per tale errore.  
  
 In base allo standard SOAP, a un errore può essere associato un elemento `Action`, un elemento `Code` e un elemento `Reason`. L'elemento `Action` è controllato dalla proprietà <xref:System.ServiceModel.FaultContractAttribute.Action%2A>. Le proprietà <xref:System.ServiceModel.FaultException.Code%2A> e <xref:System.ServiceModel.FaultException.Reason%2A> fanno entrambe parte della classe <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>, che costituisce la classe padre dell'eccezione generica <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>. La proprietà `Code` include un membro <xref:System.ServiceModel.FaultCode.SubCode%2A>.  
  
 Quando si accede a componenti non del servizio che generano errori, sono presenti alcune limitazioni. WCF supporta solo errori con tipi di dettaglio descritti nello schema e compatibili con i contratti dati. Ad esempio, come indicato in precedenza, WCF non supporta errori che usano attributi XML nei tipi di dettaglio o errori con più di un elemento di livello superiore nella sezione dei dettagli.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Specifica e gestione di errori in contratti e servizi](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
- [Invio e ricezione degli errori](../../../docs/framework/wcf/sending-and-receiving-faults.md)
- [Procedura: Dichiarare errori nei contratti di servizio](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md)
- [Informazioni sul livello di protezione](../../../docs/framework/wcf/understanding-protection-level.md)
- [Procedura: Impostare la proprietà ProtectionLevel](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md)
- [Specifica del trasferimento di dati nei contratti di servizio](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)
