---
title: Implementazione dei contratti di servizio
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: 766e0c4d30a4fa0eed9ce154ca932f5371a43211
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928635"
---
# <a name="implementing-service-contracts"></a>Implementazione dei contratti di servizio
Un servizio è una classe che espone le funzionalità disponibili per i client a uno o più endpoint. Per creare un servizio, scrivere una classe che implementa un contratto Windows Communication Foundation (WCF). Questa operazione può essere eseguita in due modi. È possibile definire il contratto separatamente come un'interfaccia e quindi creare una classe che implementi tale interfaccia. In alternativa, è possibile creare direttamente la classe e il contratto posizionando l'attributo <xref:System.ServiceModel.ServiceContractAttribute> sulla classe e l'attributo <xref:System.ServiceModel.OperationContractAttribute> sui metodi disponibili per i client del servizio.  
  
## <a name="creating-a-service-class"></a>Creazione di una classe di servizio  
 Nell'esempio seguente viene illustrato un servizio che implementa un contratto `IMath` definito separatamente.  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]   
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 In alternativa, un servizio può esporre direttamente un contratto. Nell'esempio seguente viene illustrata una classe di servizio che definisce e implementa un contratto `MathService`.  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 Si noti che i servizi precedenti espongono contratti diversi perché i nomi di contratto sono diversi. Nel primo caso, il contratto esposto è denominato "`IMath`" mentre nel secondo caso il contratto è denominato "`MathService`".  
  
 È possibile impostare alcuni aspetti a livello del servizio e dell'implementazione dell'operazione, ad esempio la concorrenza e la creazione di istanze. Per altre informazioni, vedere [progettazione e implementazione di servizi](../../../docs/framework/wcf/designing-and-implementing-services.md).  
  
 Dopo avere implementato un contratto di servizio, è necessario creare uno o più endpoint per il servizio. Per altre informazioni, vedere [Cenni preliminari sulla creazione di Endpoint](../../../docs/framework/wcf/endpoint-creation-overview.md). Per altre informazioni su come eseguire un servizio, vedere [servizi di Hosting](../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Progettazione e implementazione di servizi](../../../docs/framework/wcf/designing-and-implementing-services.md)
- [Procedura: Creare un servizio con una classe del contratto](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [Procedura: Creare un servizio con un'interfaccia del contratto](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [Specifica del comportamento in fase di esecuzione del servizio](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
