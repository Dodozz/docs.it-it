---
title: Elemento <linkedConfiguration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
ms.openlocfilehash: 909ee7cbb7cd31cf213f305b23237cb69e295882
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674649"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="e2aa3-102">\<linkedConfiguration > elemento</span><span class="sxs-lookup"><span data-stu-id="e2aa3-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="e2aa3-103">Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="e2aa3-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e2aa3-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="e2aa3-105">&nbsp;&nbsp;[ **\<assemblyBinding>** ](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e2aa3-105">&nbsp;&nbsp;[**\<assemblyBinding>**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) </span></span>  
<span data-ttu-id="e2aa3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="e2aa3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e2aa3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2aa3-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="e2aa3-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="e2aa3-108">Attribute</span></span>

|           | <span data-ttu-id="e2aa3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2aa3-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="e2aa3-110">**href**</span><span class="sxs-lookup"><span data-stu-id="e2aa3-110">**href**</span></span>  | <span data-ttu-id="e2aa3-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-111">Required attribute.</span></span><br><br><span data-ttu-id="e2aa3-112">L'URL del file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="e2aa3-113">L'unico formato supportato per il **href** attributo `file://`.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="e2aa3-114">File locali e UNC file sono supportati.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="e2aa3-115">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="e2aa3-115">Parent element</span></span>

|     | <span data-ttu-id="e2aa3-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2aa3-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e2aa3-117"> *\*\<assemblyBinding >** elemento</span><span class="sxs-lookup"><span data-stu-id="e2aa3-117">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | <span data-ttu-id="e2aa3-118">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e2aa3-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e2aa3-119">Child elements</span></span>

<span data-ttu-id="e2aa3-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="e2aa3-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="e2aa3-121">Note</span><span class="sxs-lookup"><span data-stu-id="e2aa3-121">Remarks</span></span>

<span data-ttu-id="e2aa3-122">Il  **\<linkedConfiguration >** elemento semplifica la gestione degli assembly del componente.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="e2aa3-123">Se uno o più applicazioni usano un assembly con un file di configurazione che si trova in un percorso noto, i file di configurazione delle applicazioni che usano l'assembly è possono usare la  **\<linkedConfiguration >** elemento da includere il file di configurazione di assembly, anziché includere le informazioni di configurazione direttamente.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="e2aa3-124">Quando viene gestita l'assembly del componente, l'aggiornamento del file di configurazione comune fornisce informazioni di configurazione aggiornate per tutte le applicazioni che usano l'assembly.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="e2aa3-125">Il  **\<linkedConfiguration >** elemento non è supportato per le applicazioni con i manifesti side-by-side di Windows.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="e2aa3-126">Le regole seguenti determinano l'uso di file di configurazione collegati:</span><span class="sxs-lookup"><span data-stu-id="e2aa3-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="e2aa3-127">Le impostazioni nel file di configurazione inclusi solo influisce sui criteri di associazione del caricatore e vengono usate solo dal caricatore.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="e2aa3-128">I file di configurazione inclusi possono avere impostazioni diverse da quelle di criteri di associazione, ma tali impostazioni non hanno alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="e2aa3-129">L'unico formato supportato per il `href` attributo è `file://`.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="e2aa3-130">File locali e UNC file sono supportati.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="e2aa3-131">È presente alcun vincolo per il numero di configurazioni collegate per ogni file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="e2aa3-132">Tutti i file di configurazione collegati vengono uniti per formare un file, analogamente al comportamento del `#include` direttiva in C/C++.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="e2aa3-133">Il  **\<linkedConfiguration >** l'elemento è consentito solo nei file di configurazione dell'applicazione; viene ignorata nelle *Machine. config*.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="e2aa3-134">I riferimenti circolari vengono rilevati e terminati.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="e2aa3-135">Vale a dire, se il  **\<linkedConfiguration >** elementi di una serie di file di configurazione formano un ciclo, il ciclo viene rilevato e arrestato.</span><span class="sxs-lookup"><span data-stu-id="e2aa3-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="e2aa3-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2aa3-136">Example</span></span>

<span data-ttu-id="e2aa3-137">Nell'esempio seguente viene illustrato come includere il file di configurazione dal disco rigido locale:</span><span class="sxs-lookup"><span data-stu-id="e2aa3-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e2aa3-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2aa3-138">See also</span></span>

- [<span data-ttu-id="e2aa3-139"> *\*\<assemblyBinding >** elemento</span><span class="sxs-lookup"><span data-stu-id="e2aa3-139">**\<assemblyBinding>** Element</span></span>](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="e2aa3-140">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e2aa3-140">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
