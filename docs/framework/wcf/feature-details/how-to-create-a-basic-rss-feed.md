---
title: 'Procedura: Creare un feed RSS di base'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 431879b8-a5f8-4947-ad1e-4768c726aca8
ms.openlocfilehash: 7b1ff72295332be072d7c664a546ed6e4d998ac8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073832"
---
# <a name="how-to-create-a-basic-rss-feed"></a><span data-ttu-id="b5e2b-102">Procedura: Creare un feed RSS di base</span><span class="sxs-lookup"><span data-stu-id="b5e2b-102">How to: Create a Basic RSS Feed</span></span>
<span data-ttu-id="b5e2b-103">Windows Communication Foundation (WCF) consente di creare un servizio che espone un feed di diffusione.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="b5e2b-104">In questo argomento viene illustrato come creare un servizio di diffusione che espone un feed di diffusione RSS.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-104">This topic discusses how to create a syndication service that exposes an RSS syndication feed.</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="b5e2b-105">Per creare un servizio di diffusione di base</span><span class="sxs-lookup"><span data-stu-id="b5e2b-105">To create a basic syndication service</span></span>  
  
1.  <span data-ttu-id="b5e2b-106">Definire un contratto di servizio usando un'interfaccia contrassegnata con l'attributo <xref:System.ServiceModel.Web.WebGetAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-106">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="b5e2b-107">Ogni operazione esposta come feed di diffusione deve restituire un oggetto <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-107">Each operation that is exposed as a syndication feed should return a <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> object.</span></span>  
  
     [!code-csharp[htRssBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#0)]
     [!code-vb[htRssBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#0)]  
  
    > [!NOTE]
    >  <span data-ttu-id="b5e2b-108">Tutte le operazioni del servizio che applicano l'attributo <xref:System.ServiceModel.Web.WebGetAttribute> vengono mappate alle richieste HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-108">All service operations that apply the <xref:System.ServiceModel.Web.WebGetAttribute> attribute are mapped to HTTP GET requests.</span></span> <span data-ttu-id="b5e2b-109">Per eseguire il mapping dell'operazione a un metodo HTTP diverso, utilizzare invece <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-109">To map your operation to a different HTTP method, use the <xref:System.ServiceModel.Web.WebInvokeAttribute> instead.</span></span> <span data-ttu-id="b5e2b-110">Per altre informazioni, vedere [Procedura: Creare un servizio HTTP Web WCF](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).</span><span class="sxs-lookup"><span data-stu-id="b5e2b-110">For more information, see [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).</span></span>  
  
2.  <span data-ttu-id="b5e2b-111">Implementare il contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="b5e2b-111">Implement the service contract.</span></span>  
  
     [!code-csharp[htRssBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#1)]
     [!code-vb[htRssBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#1)]  
  
3.  <span data-ttu-id="b5e2b-112">Creare un oggetto <xref:System.ServiceModel.Syndication.SyndicationFeed> e aggiungere un autore, una categoria e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-112">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htRssBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#2)]
     [!code-vb[htRssBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#2)]  
  
4.  <span data-ttu-id="b5e2b-113">Creare diversi oggetti <xref:System.ServiceModel.Syndication.SyndicationItem>.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-113">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htRssBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#3)]
     [!code-vb[htRssBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#3)]  
  
5.  <span data-ttu-id="b5e2b-114">Aggiungere <xref:System.ServiceModel.Syndication.SyndicationItem> al feed.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-114">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> to the feed.</span></span>  
  
     [!code-csharp[htRssBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#4)]
     [!code-vb[htRssBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#4)]  
  
6.  <span data-ttu-id="b5e2b-115">Restituire il feed.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-115">Return the feed.</span></span>  
  
     [!code-csharp[htRssBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#5)]
     [!code-vb[htRssBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#5)]  
  
### <a name="to-host-a-service"></a><span data-ttu-id="b5e2b-116">Per ospitare un servizio</span><span class="sxs-lookup"><span data-stu-id="b5e2b-116">To host a service</span></span>  
  
1.  <span data-ttu-id="b5e2b-117">Creare un oggetto <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-117">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>  
  
     [!code-csharp[htRssBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#6)]
     [!code-vb[htRssBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#6)]  
  
2.  <span data-ttu-id="b5e2b-118">Aprire l'host del servizio e attendere finché l'utente non preme INVIO.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-118">Open the service host and wait until the user presses ENTER.</span></span>  
  
     [!code-csharp[htRssBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#8)]
     [!code-vb[htRssBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="b5e2b-119">Per chiamare GetBlog() con un HTTP GET</span><span class="sxs-lookup"><span data-stu-id="b5e2b-119">To call GetBlog() with an HTTP GET</span></span>  
  
1.  <span data-ttu-id="b5e2b-120">Aprire Internet Explorer, digitare l'URL seguente e premere INVIO: `http://localhost:8000/BlogService/GetBlog`.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-120">Open Internet Explorer, type the following URL, and press ENTER: `http://localhost:8000/BlogService/GetBlog`.</span></span> <span data-ttu-id="b5e2b-121">L'URL contiene l'indirizzo di base del servizio (`http://localhost:8000/BlogService`), l'indirizzo relativo dell'endpoint e l'operazione di servizio da chiamare.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-121">The URL contains the base address of the service (`http://localhost:8000/BlogService`), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="b5e2b-122">Per chiamare GetBlog() dal codice</span><span class="sxs-lookup"><span data-stu-id="b5e2b-122">To call GetBlog() from code</span></span>  
  
1.  <span data-ttu-id="b5e2b-123">Creare un <xref:System.Xml.XmlReader> con l'indirizzo di base e il metodo che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-123">Create an <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htRssBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#9)]
     [!code-vb[htRssBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#9)]  
  
2.  <span data-ttu-id="b5e2b-124">Chiamare il metodo statico <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> passando l'oggetto <xref:System.Xml.XmlReader> appena creato.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-124">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htRssBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#10)]
     [!code-vb[htRssBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#10)]  
  
     <span data-ttu-id="b5e2b-125">Verrà in tal modo richiamata l'operazione del servizio e verrà popolato un nuovo <xref:System.ServiceModel.Syndication.SyndicationFeed> con il formattatore restituito dall'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-125">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3.  <span data-ttu-id="b5e2b-126">Accedere all'oggetto feed.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-126">Access the feed object.</span></span>  
  
     [!code-csharp[htRssBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#11)]
     [!code-vb[htRssBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="b5e2b-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5e2b-127">Example</span></span>  
 <span data-ttu-id="b5e2b-128">Di seguito è riportato il codice completo per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-128">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htRssBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#12)]
 [!code-vb[htRssBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b5e2b-129">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b5e2b-129">Compiling the Code</span></span>  
 <span data-ttu-id="b5e2b-130">Durante la compilazione del codice precedente, fare riferimento a System.ServiceModel.dll e a System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-130">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e2b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5e2b-131">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
