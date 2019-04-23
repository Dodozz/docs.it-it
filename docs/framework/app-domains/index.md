---
title: Programmazione con i domini applicazione e gli assembly
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7124b6b234601e3afc27109ac318f47e3fe40c35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675351"
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="a0b80-102">Programmazione con i domini applicazione e gli assembly</span><span class="sxs-lookup"><span data-stu-id="a0b80-102">Programming with Application Domains and Assemblies</span></span>
<span data-ttu-id="a0b80-103">Gli host come Microsoft Internet Explorer, ASP.NET e la shell di Windows caricano Common Language Runtime in un processo, creano un [dominio dell'applicazione](../../../docs/framework/app-domains/application-domains.md) in tale processo e quindi caricano ed eseguono codice dell'utente in tale dominio dell'applicazione quando eseguono un'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a0b80-103">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](../../../docs/framework/app-domains/application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="a0b80-104">Nella maggior parte dei casi, non è necessario occuparsi della creazione dei domini dell'applicazione e del caricamento di assembly all'interno degli stessi, perché è l'host di runtime a eseguire tali attività.</span><span class="sxs-lookup"><span data-stu-id="a0b80-104">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
 <span data-ttu-id="a0b80-105">Tuttavia, se si sta creando un'applicazione che ospita Common Language Runtime, strumenti o codice che si vogliono scaricare a livello di codice o componenti modulari che possono essere scaricati e ricaricati in tempo reale, si creano anche domini dell'applicazione personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a0b80-105">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="a0b80-106">Anche se non si sta creando un host di runtime, questa sezione fornisce importanti informazioni su come utilizzare i domini dell'applicazione e gli assembly caricati al loro interno.</span><span class="sxs-lookup"><span data-stu-id="a0b80-106">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0b80-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a0b80-107">In This Section</span></span>  
 [<span data-ttu-id="a0b80-108">Argomenti relativi alle procedure per domini applicazione e assembly</span><span class="sxs-lookup"><span data-stu-id="a0b80-108">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 <span data-ttu-id="a0b80-109">Fornisce i collegamenti a tutte le procedure contenute nella documentazione sui concetti relativi alla programmazione con domini dell'applicazione e assembly.</span><span class="sxs-lookup"><span data-stu-id="a0b80-109">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
 [<span data-ttu-id="a0b80-110">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a0b80-110">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)  
 <span data-ttu-id="a0b80-111">Fornisce esempi di creazione, configurazione e uso dei domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a0b80-111">Provides examples of creating, configuring, and using application domains.</span></span>  
  
 [<span data-ttu-id="a0b80-112">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="a0b80-112">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="a0b80-113">Descrive come creare, firmare e impostare attributi sugli assembly.</span><span class="sxs-lookup"><span data-stu-id="a0b80-113">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a0b80-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a0b80-114">Related Sections</span></span>  
 [<span data-ttu-id="a0b80-115">Creazione di assembly e metodi dinamici</span><span class="sxs-lookup"><span data-stu-id="a0b80-115">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="a0b80-116">Descrive come creare gli assembly dinamici.</span><span class="sxs-lookup"><span data-stu-id="a0b80-116">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="a0b80-117">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a0b80-117">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="a0b80-118">Viene fornita una panoramica sui concetti di base relativi agli assembly.</span><span class="sxs-lookup"><span data-stu-id="a0b80-118">Provides a conceptual overview of assemblies.</span></span>  
  
 [<span data-ttu-id="a0b80-119">Domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a0b80-119">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="a0b80-120">Viene fornita una panoramica sui concetti di base relativi ai domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="a0b80-120">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="a0b80-121">Panoramica della reflection</span><span class="sxs-lookup"><span data-stu-id="a0b80-121">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="a0b80-122">Descrive come usare la classe **Reflection** per ottenere informazioni su un assembly.</span><span class="sxs-lookup"><span data-stu-id="a0b80-122">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
