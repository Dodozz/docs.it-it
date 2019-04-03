---
title: WSStreamedHttpBinding
ms.date: 03/30/2017
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
ms.openlocfilehash: 96dccbc971c9ef5a59557100adb6df24a745ea5d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828022"
---
# <a name="wsstreamedhttpbinding"></a><span data-ttu-id="04de7-102">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="04de7-102">WSStreamedHttpBinding</span></span>
<span data-ttu-id="04de7-103">Nell'esempio viene illustrato come creare un'associazione progettata per supportare scenari basati sul flusso quando viene utilizzato il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="04de7-103">The sample demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04de7-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="04de7-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="04de7-105">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="04de7-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="04de7-106">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="04de7-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="04de7-107">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="04de7-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="04de7-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="04de7-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 <span data-ttu-id="04de7-109">I passaggi per creare e configurare una nuova associazione standard sono i seguenti.</span><span class="sxs-lookup"><span data-stu-id="04de7-109">The steps to create and configure a new standard binding are as follows.</span></span>  
  
1.  <span data-ttu-id="04de7-110">Creazione di una nuova associazione standard</span><span class="sxs-lookup"><span data-stu-id="04de7-110">Create a new standard binding</span></span>  
  
     <span data-ttu-id="04de7-111">Le associazioni standard in Windows Communication Foundation (WCF), ad esempio basicHttpBinding e netTcpBinding configurare i trasporti sottostanti e stack di canali per i requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="04de7-111">The standard bindings in Windows Communication Foundation (WCF) such as basicHttpBinding, and netTcpBinding configure the underlying transports and channel stack for specific requirements.</span></span> <span data-ttu-id="04de7-112">In questo esempio, `WSStreamedHttpBinding` configura lo stack di canali per supportare il flusso.</span><span class="sxs-lookup"><span data-stu-id="04de7-112">In this sample, `WSStreamedHttpBinding` configures the channel stack to support streaming.</span></span> <span data-ttu-id="04de7-113">Per impostazione predefinita, WS-Security e la messaggistica affidabile non vengono aggiunti allo stack di canali perché entrambi le funzionalità non sono supportate dal flusso.</span><span class="sxs-lookup"><span data-stu-id="04de7-113">By default, WS-Security and reliable messaging are not added to the channel stack because both features are not supported by streaming.</span></span> <span data-ttu-id="04de7-114">La nuova associazione viene implementata nella classe `WSStreamedHttpBinding` che deriva da <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="04de7-114">The new binding is implemented in the class `WSStreamedHttpBinding` that derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="04de7-115">`WSStreamedHttpBinding` contiene i seguenti elementi di associazione: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> e <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="04de7-115">The `WSStreamedHttpBinding` contains the following binding elements: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, and <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span> <span data-ttu-id="04de7-116">La classe fornisce un metodo `CreateBindingElements()` per configurare lo stack dell'associazione risultante, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="04de7-116">The class provides a `CreateBindingElements()` method to configure the resulting binding stack, as shown in the following sample code.</span></span>  
  
    ```  
    public override BindingElementCollection CreateBindingElements()  
    {  
         // return collection of BindingElements  
         BindingElementCollection bindingElements = new BindingElementCollection();  
  
        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by  
        // the message encoder, and finally the transport at the end  
        if (flowTransactions)  
        {  
            bindingElements.Add(transactionFlow);  
        }  
        bindingElements.Add(textEncoding);  
  
        // add transport (http or https)  
        bindingElements.Add(transport);  
        return bindingElements.Clone();  
    }  
    ```  
  
2.  <span data-ttu-id="04de7-117">Aggiunta del supporto di configurazione</span><span class="sxs-lookup"><span data-stu-id="04de7-117">Add configuration support</span></span>  
  
     <span data-ttu-id="04de7-118">Per esporre il trasporto tramite la configurazione l'esempio implementa altre due classi: `WSStreamedHttpBindingConfigurationElement` e `WSStreamedHttpBindingSection`.</span><span class="sxs-lookup"><span data-stu-id="04de7-118">To expose the transport through configuration the sample implements two more classes—`WSStreamedHttpBindingConfigurationElement` and `WSStreamedHttpBindingSection`.</span></span> <span data-ttu-id="04de7-119">La classe `WSStreamedHttpBindingSection` è un <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> che espone `WSStreamedHttpBinding` al sistema di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="04de7-119">The class `WSStreamedHttpBindingSection` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `WSStreamedHttpBinding` to the WCF configuration system.</span></span> <span data-ttu-id="04de7-120">La maggior parte dell'implementazione viene delegata a `WSStreamedHttpBindingConfigurationElement` che deriva da <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="04de7-120">The bulk of the implementation is delegated to `WSStreamedHttpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="04de7-121">La classe `WSStreamedHttpBindingConfigurationElement` è dotata delle proprietà che corrispondono alle proprietà di `WSStreamedHttpBinding` e funzioni che consentono di eseguire il mapping di ogni elemento di configurazione a un'associazione.</span><span class="sxs-lookup"><span data-stu-id="04de7-121">The class `WSStreamedHttpBindingConfigurationElement` has properties that correspond to the properties of `WSStreamedHttpBinding`, and functions to map each configuration element to a binding.</span></span>  
  
     <span data-ttu-id="04de7-122">Registrare il gestore nel sistema di configurazione, aggiungendo la sezione seguente al file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="04de7-122">Register the handler with the configuration system, by adding the following section to the service's configuration file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <extensions>  
          <bindingExtensions>  
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </bindingExtensions>  
        </extensions>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="04de7-123">È possibile fare riferimento al gestore dalla sezione di configurazione serviceModel.</span><span class="sxs-lookup"><span data-stu-id="04de7-123">The handler can then be referenced from the serviceModel configuration section.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint  
                    address="https://localhost/servicemodelsamples/service.svc"  
                    bindingConfiguration="Binding"  
                    binding="wsStreamedHttpBinding"  
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="04de7-124">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="04de7-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="04de7-125">Installare [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="04de7-125">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="04de7-126">Assicurarsi di avere eseguito i passaggi elencati in [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="04de7-126">Ensure that you have performed the steps listed in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="04de7-127">Assicurarsi di avere eseguito il [istruzioni di installazione certificato Server Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="04de7-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="04de7-128">Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="04de7-128">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="04de7-129">Per eseguire l'esempio in una configurazione tra più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="04de7-129">To run the sample in a cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
6.  <span data-ttu-id="04de7-130">Quando viene visualizzata la finestra client, digitare "Esempio.txt."</span><span class="sxs-lookup"><span data-stu-id="04de7-130">When the client window displays, type "Sample.txt".</span></span> <span data-ttu-id="04de7-131">Nella directory dovrebbe essere presente una "Copia di Esempio.txt".</span><span class="sxs-lookup"><span data-stu-id="04de7-131">You should find a "Copy of Sample.txt" in your directory.</span></span>  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a><span data-ttu-id="04de7-132">Esempio di servizio WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="04de7-132">The WSStreamedHttpBinding Sample Service</span></span>  
 <span data-ttu-id="04de7-133">L'esempio di servizio che utilizza `WSStreamedHttpBinding` si trova nella sottodirectory del servizio.</span><span class="sxs-lookup"><span data-stu-id="04de7-133">The sample service that uses `WSStreamedHttpBinding` is located in the service subdirectory.</span></span> <span data-ttu-id="04de7-134">L'implementazione di `OperationContract` utilizza un `MemoryStream` per recuperare tutti i dati dal flusso in ingresso prima di restituire `MemoryStream`.</span><span class="sxs-lookup"><span data-stu-id="04de7-134">The implementation of `OperationContract` uses a `MemoryStream` to first retrieve all data from the incoming stream before returning the `MemoryStream`.</span></span> <span data-ttu-id="04de7-135">L'esempio di servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="04de7-135">The sample service is hosted by Internet Information Services (IIS).</span></span>  
  
```  
[ServiceContract]  
public interface IStreamedEchoService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
}  
  
public class StreamedEchoService : IStreamedEchoService  
{  
    public Stream Echo(Stream data)  
    {  
        MemoryStream dataStorage = new MemoryStream();  
        byte[] byteArray = new byte[8192];  
        int bytesRead = data.Read(byteArray, 0, 8192);  
        while (bytesRead > 0)  
        {  
            dataStorage.Write(byteArray, 0, bytesRead);  
            bytesRead = data.Read(byteArray, 0, 8192);  
        }  
        data.Close();  
        dataStorage.Seek(0, SeekOrigin.Begin);  
  
        return dataStorage;  
    }  
}  
```  
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a><span data-ttu-id="04de7-136">Esempio di Client WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="04de7-136">The WSStreamedHttpBinding Sample Client</span></span>  
 <span data-ttu-id="04de7-137">Il client utilizzato per interagire con il servizio utilizzando `WSStreamedHttpBinding` si trova nella sottodirectory client.</span><span class="sxs-lookup"><span data-stu-id="04de7-137">The client that is used to interact with the service using `WSStreamedHttpBinding` is located in the client subdirectory.</span></span> <span data-ttu-id="04de7-138">Poiché il certificato usato in questo esempio è un certificato di prova creato con Makecert.exe, viene visualizzato un avviso di sicurezza quando si tenta di accedere a un indirizzo HTTPS nel browser, ad esempio https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="04de7-138">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert displays when you attempt to access an HTTPS address in your browser such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="04de7-139">Per consentire al client di WCF con un certificato di prova in luogo di lavoro, è stato aggiunto altro codice al client per sopprimere l'avviso di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="04de7-139">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="04de7-140">Il codice e la classe associata non sono richiesti quando si utilizzano i certificati di produzione.</span><span class="sxs-lookup"><span data-stu-id="04de7-140">The code and the accompanying class are not required when using production certificates.</span></span>  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
