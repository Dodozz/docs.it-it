---
title: 'Procedura: Creare un contratto Windows Communication Foundation con una classe'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 37d0e6fae8ad0f3a91f1bead23fb5823fc52d420
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787582"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Procedura: Creare un contratto Windows Communication Foundation con una classe
Il modo migliore di creazione di un contratto Windows Communication Foundation (WCF) consiste nell'usare un'interfaccia. Per altre informazioni, vedere [Procedura: Definire un contratto di servizio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Un'alternativa, illustrata qui, consiste nel creare una classe e quindi nell'applicare l'attributo <xref:System.ServiceModel.ServiceContractAttribute> direttamente alla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> a ognuno dei metodi nella classe che fanno parte del contratto.  
  
> [!WARNING]
>  `[ServiceContract]` e `[ServiceContractAttribute]` eseguono la stessa operazione. La stessa cosa vale per `[OperationContract]` e `[OperationContractAttribute]`. In ogni caso, il primo è l'abbreviazione del secondo.  
  
 Per altre informazioni sui contratti di servizio, vedere [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Creazione di un contratto Windows Communication Foundation con una classe  
  
1. Creare una nuova classe utilizzando Visual Basic, C#, o qualsiasi altro linguaggio common language runtime.  
  
2. Applicare la classe <xref:System.ServiceModel.ServiceContractAttribute> alla classe.  
  
3. Creare metodi nella classe.  
  
4. Applicare il <xref:System.ServiceModel.OperationContractAttribute> classe a ogni metodo che deve essere esposto come parte del contratto pubblico di WCF.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrata una classe che definisce un contratto di servizio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 I metodi a cui è applicata la classe <xref:System.ServiceModel.OperationContractAttribute> usano per impostazione predefinita un modello di messaggio request/reply. Per altre informazioni su questo modello di messaggio, vedere [come: Creare un contratto Request / Reply](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). È anche possibile creare e utilizzare altri modelli di messaggio impostando proprietà dell'attributo. Per altri esempi, vedere [Procedura: Creare un contratto unidirezionale](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) e [come: Creare un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
