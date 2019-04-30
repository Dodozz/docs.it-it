---
title: 'Procedura: Esporre un contratto a client SOAP e Web'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: d82c5e3fc33528eadc3c404cca59a3dcf905e0e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000922"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="6d54f-102">Procedura: Esporre un contratto a client SOAP e Web</span><span class="sxs-lookup"><span data-stu-id="6d54f-102">How to: Expose a Contract to SOAP and Web Clients</span></span>

<span data-ttu-id="6d54f-103">Per impostazione predefinita, Windows Communication Foundation (WCF) rende disponibili endpoint solo ai client SOAP.</span><span class="sxs-lookup"><span data-stu-id="6d54f-103">By default, Windows Communication Foundation (WCF) makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="6d54f-104">In [come: Creare un servizio HTTP Web WCF base](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), un endpoint viene reso disponibile ai client non SOAP.</span><span class="sxs-lookup"><span data-stu-id="6d54f-104">In [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="6d54f-105">Possono verificarsi casi in cui si desidera rendere lo stesso contratto disponibile in entrambi i modi, come endpoint Web e come endpoint SOAP.</span><span class="sxs-lookup"><span data-stu-id="6d54f-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="6d54f-106">In questo argomento viene illustrato un esempio di come ottenere tale risultato.</span><span class="sxs-lookup"><span data-stu-id="6d54f-106">This topic shows an example of how to do this.</span></span>

## <a name="to-define-the-service-contract"></a><span data-ttu-id="6d54f-107">Per definire il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="6d54f-107">To define the service contract</span></span>

1. <span data-ttu-id="6d54f-108">Definire un contratto di servizio usando un'interfaccia contrassegnata con il <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> e il <xref:System.ServiceModel.Web.WebGetAttribute> attributi, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d54f-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code:</span></span>

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="6d54f-109">Per impostazione predefinita, <xref:System.ServiceModel.Web.WebInvokeAttribute> esegue il mapping delle chiamate POST all'operazione.</span><span class="sxs-lookup"><span data-stu-id="6d54f-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="6d54f-110">Tuttavia, è possibile definire il metodo di mapping all'operazione specificando un parametro "method=".</span><span class="sxs-lookup"><span data-stu-id="6d54f-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="6d54f-111"><xref:System.ServiceModel.Web.WebGetAttribute> non dispone di un parametro "method=" ed esegue solo il mapping delle chiamate GET all'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="6d54f-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="6d54f-112">Implementare il contratto di servizio, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d54f-112">Implement the service contract, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="6d54f-113">Per ospitare il servizio</span><span class="sxs-lookup"><span data-stu-id="6d54f-113">To host the service</span></span>

1. <span data-ttu-id="6d54f-114">Creare un <xref:System.ServiceModel.ServiceHost> dell'oggetto, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d54f-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. <span data-ttu-id="6d54f-115">Aggiungere un <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.BasicHttpBinding> per l'endpoint SOAP, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d54f-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. <span data-ttu-id="6d54f-116">Aggiungere un <xref:System.ServiceModel.Description.ServiceEndpoint> con <xref:System.ServiceModel.WebHttpBinding> per l'endpoint non SOAP e aggiungere il <xref:System.ServiceModel.Description.WebHttpBehavior> all'endpoint, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d54f-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. <span data-ttu-id="6d54f-117">Chiamare `Open()` su un <xref:System.ServiceModel.ServiceHost> istanza per aprire l'host del servizio, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6d54f-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="6d54f-118">Per chiamare operazioni del servizio mappate a GET in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="6d54f-118">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="6d54f-119">Aprire Internet Explorer, digitare "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="6d54f-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="6d54f-120">L'URL contiene l'indirizzo di base del servizio (`http://localhost:8000/`), l'indirizzo relativo dell'endpoint (""), l'operazione del servizio da chiamare ("EchoWithGet") e un punto interrogativo seguito da un elenco di parametri denominati separati da una e commerciale (&).</span><span class="sxs-lookup"><span data-stu-id="6d54f-120">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="6d54f-121">Per chiamare operazioni del servizio sull'endpoint Web nel codice</span><span class="sxs-lookup"><span data-stu-id="6d54f-121">To call service operations on the Web endpoint in code</span></span>

1. <span data-ttu-id="6d54f-122">Creare un'istanza di <xref:System.ServiceModel.Web.WebChannelFactory%601> all'interno di un blocco `using`, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6d54f-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> <span data-ttu-id="6d54f-123">`Close()` viene automaticamente chiamato sul canale alla fine del blocco `using`.</span><span class="sxs-lookup"><span data-stu-id="6d54f-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>

1. <span data-ttu-id="6d54f-124">Creare il canale e chiamare il servizio, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6d54f-124">Create the channel and call the service, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="6d54f-125">Per chiamare operazioni del servizio sull'endpoint SOAP</span><span class="sxs-lookup"><span data-stu-id="6d54f-125">To call service operations on the SOAP endpoint</span></span>

1. <span data-ttu-id="6d54f-126">Creare un'istanza di <xref:System.ServiceModel.ChannelFactory> all'interno di un blocco `using`, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6d54f-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. <span data-ttu-id="6d54f-127">Creare il canale e chiamare il servizio, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6d54f-127">Create the channel and call the service, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a><span data-ttu-id="6d54f-128">Per chiudere l'host del servizio</span><span class="sxs-lookup"><span data-stu-id="6d54f-128">To close the service host</span></span>

1. <span data-ttu-id="6d54f-129">Chiudere l'host del servizio, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6d54f-129">Close the service host, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a><span data-ttu-id="6d54f-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d54f-130">Example</span></span>

<span data-ttu-id="6d54f-131">Di seguito è riportato in questo argomento il codice completo:</span><span class="sxs-lookup"><span data-stu-id="6d54f-131">The following is the full code listing for this topic:</span></span>

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a><span data-ttu-id="6d54f-132">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6d54f-132">Compiling the code</span></span>

 <span data-ttu-id="6d54f-133">Durante la compilazione di Service.cs fare riferimento a System.ServiceModel.dll e System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="6d54f-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d54f-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d54f-134">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="6d54f-135">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="6d54f-135">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)