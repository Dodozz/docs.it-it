---
title: Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Modernizza il ciclo di vita dell'app con le pipeline di integrazione continua/recapito Continuo e strumenti DevOps nel cloud
ms.date: 04/30/2018
ms.openlocfilehash: cc991bba5df3a9cd972d9a172c1a8f1035ce8c58
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758642"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="c5315-103">Modernizzare il ciclo di vita dell'app con le pipeline di integrazione continua/distribuzione continua e gli strumenti DevOps nel cloud</span><span class="sxs-lookup"><span data-stu-id="c5315-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="c5315-104">È necessario che le aziende moderne innovazione rapida per essere competitivi nel marketplace.</span><span class="sxs-lookup"><span data-stu-id="c5315-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="c5315-105">Distribuzione di alta qualità, le applicazioni moderne richiede strumenti DevOps e i processi di importanza cruciale per implementare questo ciclo costante di innovazione.</span><span class="sxs-lookup"><span data-stu-id="c5315-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="c5315-106">Con gli strumenti DevOps, gli sviluppatori possono semplificare la distribuzione continua e ottenere più rapidamente applicazioni innovative nelle mani degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c5315-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="c5315-107">Anche se l'integrazione e distribuzione continue sono ben definite, l'introduzione di contenitori introduce nuove considerazioni, specialmente quando si lavora con le applicazioni multi-contenitore.</span><span class="sxs-lookup"><span data-stu-id="c5315-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="c5315-108">Servizi di Azure DevOps supporta l'integrazione continua e distribuzione di applicazioni multi-contenitore in un'ampia gamma di ambienti tramite le attività di distribuzione di servizi di Azure DevOps ufficiale:</span><span class="sxs-lookup"><span data-stu-id="c5315-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- <span data-ttu-id="c5315-109">[Distribuire alla macchina virtuale Host Docker autonoma](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux o Windows Server 2016 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="c5315-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

- [<span data-ttu-id="c5315-110">Distribuire nel servizio contenitore di Azure – Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c5315-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="c5315-111">Ma è anche possibile distribuire [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/OS tramite le attività di servizi di Azure DevOps basato su script.</span><span class="sxs-lookup"><span data-stu-id="c5315-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="c5315-112">Per continuare a favorire l'agilità della distribuzione, questi strumenti offrono esperienze eccellente dev da-test-a-distribuzione di produzione per carichi di lavoro contenitore con una gamma di soluzioni di integrazione continua/recapito Continuo e sviluppo.</span><span class="sxs-lookup"><span data-stu-id="c5315-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="c5315-113">Figura 4-12 illustra una pipeline di distribuzione continua che distribuisce un cluster Kubernetes nel servizio contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="c5315-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Pipeline di distribuzione continua DevOps servizi Azure, la distribuzione in un cluster Kubernetes](./media/image12.png)

> <span data-ttu-id="c5315-115">**Figura 4-12.**</span><span class="sxs-lookup"><span data-stu-id="c5315-115">**Figure 4-12.**</span></span> <span data-ttu-id="c5315-116">Pipeline di distribuzione continua DevOps servizi Azure, la distribuzione in un cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c5315-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c5315-117">[Precedente](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Successivo](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="c5315-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
