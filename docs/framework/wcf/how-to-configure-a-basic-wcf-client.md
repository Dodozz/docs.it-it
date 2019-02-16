---
title: 'Procedura: Configurare un Client di base di Windows Communication Foundation'
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 18acec48b2af78877f99335da38ccb0ae8942824
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332319"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="678e6-102">Procedura: Configurare un Client di base di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="678e6-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>

<span data-ttu-id="678e6-103">Questa è la quinta delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="678e6-103">This is the fifth of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="678e6-104">Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="678e6-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="678e6-105">Questo argomento viene illustrato il file di configurazione client generato tramite il **Aggiungi riferimento al servizio** funzionalità di Visual Studio o il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="678e6-105">This topic discusses the client configuration file that was generated using the **Add Service Reference** functionality of Visual Studio or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="678e6-106">La configurazione del client è costituita dalla specifica dell'endpoint usato dal client per accedere al servizio.</span><span class="sxs-lookup"><span data-stu-id="678e6-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="678e6-107">Un endpoint ha un indirizzo, un'associazione e un contratto, e ognuno di questi deve essere specificato nel processo di configurazione del client.</span><span class="sxs-lookup"><span data-stu-id="678e6-107">An endpoint has an address, a binding, and a contract, and each of these must be specified in the process of configuring the client.</span></span>

## <a name="configure-a-windows-communication-foundation-client"></a><span data-ttu-id="678e6-108">Configurare un client Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="678e6-108">Configure a Windows Communication Foundation client</span></span>

<span data-ttu-id="678e6-109">Aprire il file di configurazione generato (App.config) dal progetto GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="678e6-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="678e6-110">L'esempio seguente è una visualizzazione del file di configurazione generato.</span><span class="sxs-lookup"><span data-stu-id="678e6-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="678e6-111">Sotto il [ \<System. ServiceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sezione, trovare il [ \<endpoint >](../configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="678e6-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
          <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

<span data-ttu-id="678e6-112">In questo esempio viene configurato l'endpoint utilizzato dal client per accedere al servizio che si trova all'indirizzo seguente: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="678e6-112">This example configures the endpoint that the client uses to access the service that is located at the following address: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.</span></span>

<span data-ttu-id="678e6-113">L'elemento endpoint specifica che il contratto di servizio `ServiceReference1.ICalculator` viene usato per la comunicazione tra il client e il servizio di WCF.</span><span class="sxs-lookup"><span data-stu-id="678e6-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="678e6-114">Il canale WCF è configurato con l'oggetto <xref:System.ServiceModel.WSHttpBinding> fornito dal sistema.</span><span class="sxs-lookup"><span data-stu-id="678e6-114">The WCF channel is configured with the system-provided <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="678e6-115">Il presente contratto è stato generato utilizzando **Aggiungi riferimento al servizio** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="678e6-115">This contract was generated by using **Add Service Reference** in Visual Studio.</span></span> <span data-ttu-id="678e6-116">Si tratta essenzialmente di una copia del contratto che è stato definito nel progetto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="678e6-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="678e6-117">Con l'associazione <xref:System.ServiceModel.WSHttpBinding> vengono specificati HTTP come trasporto, la sicurezza interoperativa e altri dettagli di configurazione.</span><span class="sxs-lookup"><span data-stu-id="678e6-117">The <xref:System.ServiceModel.WSHttpBinding> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

<span data-ttu-id="678e6-118">Per altre informazioni su come usare il client generato con questa configurazione, vedere [come: Usare un Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="678e6-118">For more information about how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="678e6-119">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="678e6-119">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="678e6-120">Procedura: Usare un client WCF</span><span class="sxs-lookup"><span data-stu-id="678e6-120">How to: Use a WCF client</span></span>](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

## <a name="see-also"></a><span data-ttu-id="678e6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="678e6-121">See also</span></span>

- [<span data-ttu-id="678e6-122">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="678e6-122">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="678e6-123">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="678e6-123">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="678e6-124">Procedura: Creare un Client</span><span class="sxs-lookup"><span data-stu-id="678e6-124">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="678e6-125">Introduzione</span><span class="sxs-lookup"><span data-stu-id="678e6-125">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="678e6-126">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="678e6-126">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)