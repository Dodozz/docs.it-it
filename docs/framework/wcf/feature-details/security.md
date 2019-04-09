---
title: Funzionalità di sicurezza di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 58bec40f197dd1f2b104607a65c3ad456b95f69d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118196"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="a74a8-102">Funzionalità di sicurezza di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a74a8-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="a74a8-103">Negli argomenti di questa sezione descrivono le funzionalità di sicurezza di Windows Communication Foundation (WCF) e come usarli per proteggere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="a74a8-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="a74a8-104">Per altre informazioni sulla sicurezza e Windows Server AppFabric, vedere [modello di sicurezza per Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="a74a8-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a74a8-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a74a8-105">In This Section</span></span>  
 [<span data-ttu-id="a74a8-106">Cenni preliminari sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="a74a8-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="a74a8-107">Descrive le funzionalità di sicurezza in WCF.</span><span class="sxs-lookup"><span data-stu-id="a74a8-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="a74a8-108">Concetti sulla protezione</span><span class="sxs-lookup"><span data-stu-id="a74a8-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="a74a8-109">Descrive la terminologia di base e concetti usati nella sicurezza WCF.</span><span class="sxs-lookup"><span data-stu-id="a74a8-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="a74a8-110">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="a74a8-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="a74a8-111">Descrive gli scenari e le topologie che configurabili con WCF.</span><span class="sxs-lookup"><span data-stu-id="a74a8-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="a74a8-112">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="a74a8-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="a74a8-113">Fornisce cenni preliminari su comportamenti WCF che influiscono sulla sicurezza, ad esempio l'impostazione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="a74a8-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="a74a8-114">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="a74a8-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="a74a8-115">Vengono forniti vari argomenti che descrivono le funzionalità di sicurezza relative alle associazioni. In particolare, vengono forniti argomenti che descrivono come creare associazioni di sicurezza personalizzate.</span><span class="sxs-lookup"><span data-stu-id="a74a8-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="a74a8-116">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="a74a8-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="a74a8-117">Descrive come proteggere i messaggi usando le funzionalità di sicurezza WCF.</span><span class="sxs-lookup"><span data-stu-id="a74a8-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="a74a8-118">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="a74a8-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="a74a8-119">Vengono illustrate alcune attività comuni di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="a74a8-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="a74a8-120">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a74a8-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="a74a8-121">Vengono descritti alcuni scenari comuni di autorizzazione contenenti implementazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a74a8-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="a74a8-122">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="a74a8-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="a74a8-123">Vengono descritti i concetti di base della federazione e viene fornita la procedura per creare client che comunicano con server federati.</span><span class="sxs-lookup"><span data-stu-id="a74a8-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="a74a8-124">Attendibilità parziale</span><span class="sxs-lookup"><span data-stu-id="a74a8-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="a74a8-125">Descrive come eseguire scenari parzialmente attendibile e le limitazioni di WCF durante l'esecuzione parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="a74a8-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="a74a8-126">Controllo</span><span class="sxs-lookup"><span data-stu-id="a74a8-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="a74a8-127">Viene descritto come controllare gli eventi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a74a8-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="a74a8-128">Indicazioni di sicurezza e procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="a74a8-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="a74a8-129">Linee guida per la creazione di proteggere le applicazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="a74a8-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a74a8-130">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="a74a8-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="a74a8-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a74a8-131">Related Sections</span></span>  
 [<span data-ttu-id="a74a8-132">Dettagli delle funzionalità di WCF</span><span class="sxs-lookup"><span data-stu-id="a74a8-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="a74a8-133">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="a74a8-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="a74a8-134">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="a74a8-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="a74a8-135">Panoramica dei concetti</span><span class="sxs-lookup"><span data-stu-id="a74a8-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="a74a8-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a74a8-136">See also</span></span>

- [<span data-ttu-id="a74a8-137">Configurazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a74a8-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
