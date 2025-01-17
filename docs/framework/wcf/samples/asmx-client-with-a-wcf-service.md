---
title: Client ASMX con un servizio WCF
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: 1eee814b17a7547bbbc07e17dd675c5f37860341
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002742"
---
# <a name="asmx-client-with-a-wcf-service"></a>Client ASMX con un servizio WCF
Questo esempio viene illustrato come creare un servizio che utilizza Windows Communication Foundation (WCF) e quindi accedere al servizio da un client non WCF, ad esempio un client ASMX.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Questo esempio è costituito da un programma di console client (.exe) e da una libreria di servizi (.dll) ospitati da Internet Information Services (IIS). Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta. Il contratto viene definito dall'interfaccia `ICalculator` che espone operazioni matematiche (`Add`, `Subtract`, `Multiply` e `Divide`). Il client ASMX esegue richieste sincrone a un'operazione matematica e il servizio risponde fornendo il risultato.  
  
 Il servizio implementa un contratto `ICalculator`, come definito nel codice seguente.  
  
```csharp  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Xml.Serialization.XmlSerializer> eseguono il mapping dei tipi CLR a una rappresentazione XML. <xref:System.Runtime.Serialization.DataContractSerializer> interpreta alcune rappresentazioni XML in modo diverso da XmlSerializer. Generatori proxy non WCF, ad esempio Wsdl.exe, generano un'interfaccia più efficace quando viene utilizzata XmlSerializer. Il <xref:System.ServiceModel.XmlSerializerFormatAttribute> viene applicato a di `ICalculator` interfaccia, per assicurarsi che venga utilizzata XmlSerializer per eseguire il mapping di tipi CLR in XML. L'implementazione del servizio calcola e restituisce il risultato appropriato.  
  
 Il servizio espone un solo endpoint per comunicare con il servizio che viene definito mediante un file di configurazione (Web.config). L'endpoint è costituito da un indirizzo, un'associazione e un contratto. Il servizio espone l'endpoint dell'indirizzo di base fornito dall'host IIS. L'attributo `binding` è impostato su basicHttpBinding  per fornire la comunicazione HTTP mediante SOAP 1.1, che è conforme a WS-BasicProfile 1.1, come illustrato nella configurazione di esempio seguente.  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->  
    <endpoint address=""  
              binding="basicHttpBinding"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </service>  
</services>  
```  
  
 Il client ASMX comunica con il servizio WCF utilizzando un proxy tipizzato generato dall'utilità di Web Services Description Language (WSDL) (Wsdl.exe). Il proxy tipizzato è contenuto nel file generatedClient.cs. L'utilità WSDL recupera i metadati per il servizio specificato e genera un proxy tipizzato che può essere utilizzato da un client per comunicare. Per impostazione predefinita, il framework non espone metadati. Per esporre i metadati necessari per generare il proxy, è necessario aggiungere un [ \<serviceMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) e impostare relativo `httpGetEnabled` attributo `True` come illustrato nella configurazione seguente.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- Setting httpGetEnabled to True on the serviceMetadata  
           behavior exposes the service's wsdl at <base address>?wsdl :  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Eseguire il comando seguente da un prompt dei comandi nella directory del client per generare il proxy tipizzato.  
  
```console  
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl  
```  
  
 Utilizzando il proxy tipizzato generato, il client può accedere a uno specifico endpoint del servizio configurando l'indirizzo appropriato. Il client utilizza un file di configurazione (App.config) per specificare l'endpoint con il quale comunicare.  
  
```xml  
<appSettings>  
  <add key="CalculatorServiceAddress"   
       value="http://localhost/ServiceModelSamples/service.svc"/>  
</appSettings>  
```  
  
 L'implementazione client costruisce un'istanza del proxy tipizzato per iniziare a comunicare con il servizio.  
  
```csharp
// Create a client to the CalculatorService.  
using (CalculatorService client = new CalculatorService())  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation.  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Multiply service operation.  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
}  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.  
  
```console 
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!NOTE]
>  Per altre informazioni sul passaggio e restituzione di dati complessi tipi, vedere: [Client di Data Binding in un Windows Form](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [Data Binding in un Client Windows Presentation Foundation](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md), e [Data Binding in un Client ASP.NET](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`  
