---
title: Recupero di informazioni di installazione da un dominio applicazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- AppDomainSetup object
- retrieving setup information
- application domains, retrieving setup information
ms.assetid: 5cdb12ae-1e37-4a62-8ec7-93d6dcc6e8d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80c9fe6de0fca86497ffe84cd8dadf0eb8cef6c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108953"
---
# <a name="retrieving-setup-information-from-an-application-domain"></a><span data-ttu-id="8453e-102">Recupero di informazioni di installazione da un dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="8453e-102">Retrieving Setup Information from an Application Domain</span></span>
<span data-ttu-id="8453e-103">Ogni istanza di un dominio dell'applicazione è costituita da proprietà e da informazioni <xref:System.AppDomainSetup>.</span><span class="sxs-lookup"><span data-stu-id="8453e-103">Each instance of an application domain consists of both properties and <xref:System.AppDomainSetup> information.</span></span> <span data-ttu-id="8453e-104">È possibile recuperare informazioni di installazione da un dominio dell'applicazione mediante la classe <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8453e-104">You can retrieve setup information from an application domain using the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="8453e-105">Questa classe include diversi membri che recuperano informazioni di configurazione relative a un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8453e-105">This class provides several members that retrieve configuration information about an application domain.</span></span>  
  
 <span data-ttu-id="8453e-106">È anche possibile eseguire una query sull'oggetto **AppDomainSetup** per il dominio dell'applicazione al fine di ottenere le informazioni di installazione passate al dominio quando è stato creato.</span><span class="sxs-lookup"><span data-stu-id="8453e-106">You can also query the **AppDomainSetup** object for the application domain to obtain setup information that was passed to the domain when it was created.</span></span>  
  
 <span data-ttu-id="8453e-107">Nell'esempio seguente viene creato un nuovo dominio dell'applicazione, quindi vengono visualizzati diversi valori membro nella console.</span><span class="sxs-lookup"><span data-stu-id="8453e-107">The following example creates a new application domain and then prints several member values to the console.</span></span>  
  
 [!code-cpp[AppDomain_Setup#2](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source2.cpp#2)]
 [!code-csharp[AppDomain_Setup#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source2.cs#2)]
 [!code-vb[AppDomain_Setup#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source2.vb#2)]  
  
 <span data-ttu-id="8453e-108">Nel seguente esempio vengono impostate e quindi recuperate informazioni di installazione per un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8453e-108">The following example sets, and then retrieves, setup information for an application domain.</span></span> <span data-ttu-id="8453e-109">Si noti che le informazioni di configurazione vengono ottenute da `AppDomain.SetupInformation.ApplicationBase`.</span><span class="sxs-lookup"><span data-stu-id="8453e-109">Note that `AppDomain.SetupInformation.ApplicationBase` gets the configuration information.</span></span>  
  
 [!code-cpp[AppDomain_Setup#3](../../../samples/snippets/cpp/VS_Snippets_CLR/AppDomain_Setup/CPP/source3.cpp#3)]
 [!code-csharp[AppDomain_Setup#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AppDomain_Setup/CS/source3.cs#3)]
 [!code-vb[AppDomain_Setup#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AppDomain_Setup/VB/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8453e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8453e-110">See also</span></span>

- [<span data-ttu-id="8453e-111">Programmazione con i domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8453e-111">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="8453e-112">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8453e-112">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
