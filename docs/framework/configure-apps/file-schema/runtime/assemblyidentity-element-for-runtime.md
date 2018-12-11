---
title: '&lt;assemblyIdentity&gt; (elemento) per &lt;runtime&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2d82aed13e185b2957a22f097b60e12265a5f190
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128206"
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a><span data-ttu-id="af469-102">&lt;assemblyIdentity&gt; (elemento) per &lt;runtime&gt;</span><span class="sxs-lookup"><span data-stu-id="af469-102">&lt;assemblyIdentity&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="af469-103">Contiene le informazioni di identificazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="af469-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="af469-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="af469-104">\<configuration></span></span>  
<span data-ttu-id="af469-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="af469-105">\<runtime></span></span>  
<span data-ttu-id="af469-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="af469-106">\<assemblyBinding></span></span>  
<span data-ttu-id="af469-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="af469-107">\<dependentAssembly></span></span>  
<span data-ttu-id="af469-108">\<assemblyIdentity ></span><span class="sxs-lookup"><span data-stu-id="af469-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af469-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af469-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af469-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="af469-110">Attributes and Elements</span></span>  
 <span data-ttu-id="af469-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="af469-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af469-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="af469-112">Attributes</span></span>  
  
|<span data-ttu-id="af469-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="af469-113">Attribute</span></span>|<span data-ttu-id="af469-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af469-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="af469-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="af469-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="af469-116">Il nome dell'assembly</span><span class="sxs-lookup"><span data-stu-id="af469-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="af469-117">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="af469-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="af469-118">Stringa che specifica la lingua e paese/area geografica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="af469-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="af469-119">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="af469-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="af469-120">Valore esadecimale che specifica il nome sicuro dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="af469-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="af469-121">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="af469-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="af469-122">Uno dei valori "x86", "amd64", "msil" o "ia64", che specifica l'architettura del processore per un assembly che contiene codice specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="af469-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="af469-123">I valori non sono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="af469-123">The values are not case-sensitive.</span></span> <span data-ttu-id="af469-124">Se l'attributo viene assegnato a qualsiasi altro valore, l'intera `<assemblyIdentity>` elemento viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="af469-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="af469-125">Vedere <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="af469-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="af469-126">processorArchitecture attributo</span><span class="sxs-lookup"><span data-stu-id="af469-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="af469-127">Value</span><span class="sxs-lookup"><span data-stu-id="af469-127">Value</span></span>|<span data-ttu-id="af469-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af469-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="af469-129">Architettura solo di AMD 64 x86.</span><span class="sxs-lookup"><span data-stu-id="af469-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="af469-130">Solo l'architettura Itanium di Intel.</span><span class="sxs-lookup"><span data-stu-id="af469-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="af469-131">Neutro rispetto al processore e bit per parola.</span><span class="sxs-lookup"><span data-stu-id="af469-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="af469-132">Un x86 a 32 processori, nativo o in di Windows nell'ambiente di Windows (WOW) su una piattaforma a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="af469-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af469-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="af469-133">Child Elements</span></span>  
 <span data-ttu-id="af469-134">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="af469-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af469-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="af469-135">Parent Elements</span></span>  
  
|<span data-ttu-id="af469-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="af469-136">Element</span></span>|<span data-ttu-id="af469-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af469-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="af469-138">Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.</span><span class="sxs-lookup"><span data-stu-id="af469-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="af469-139">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af469-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="af469-140">Incapsula i criteri di associazione e il percorso dell'assembly per ciascun assembly.</span><span class="sxs-lookup"><span data-stu-id="af469-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="af469-141">Usare uno `<dependentAssembly>` (elemento) per ogni assembly.</span><span class="sxs-lookup"><span data-stu-id="af469-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="af469-142">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="af469-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af469-143">Note</span><span class="sxs-lookup"><span data-stu-id="af469-143">Remarks</span></span>  
 <span data-ttu-id="af469-144">Ogni  **\<dependentAssembly >** elemento deve avere uno  **\<assemblyIdentity >** elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="af469-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="af469-145">Se il `processorArchitecture` attributo è presente, il `<assemblyIdentity>` elemento si applica solo agli assembly con l'architettura del processore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="af469-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="af469-146">Se il `processorArchitecture` attributo non è presente, il `<assemblyIdentity>` elemento può essere applicato a un assembly con qualsiasi architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="af469-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="af469-147">Nell'esempio seguente viene illustrato un file di configurazione per i due assembly con lo stesso nome che hanno come destinazione due differenti architetture del processore due e le cui versioni non sono state mantenute sincronizzate. Quando l'applicazione esegue su x86 piattaforma il primo `<assemblyIdentity>` si applica l'elemento e l'altra viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="af469-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="af469-148">Se l'applicazione viene eseguita su una piattaforma diversa da x86 o ia64, entrambi vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="af469-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="af469-149">Se un file di configurazione contiene un' `<assemblyIdentity>` elemento senza alcun `processorArchitecture` dell'attributo e non contiene un elemento che corrisponde alla piattaforma, l'elemento senza il `processorArchitecture` viene utilizzato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="af469-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af469-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="af469-150">Example</span></span>  
 <span data-ttu-id="af469-151">Nell'esempio seguente viene illustrato come fornire informazioni relative a un assembly.</span><span class="sxs-lookup"><span data-stu-id="af469-151">The following example shows how to provide information about an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af469-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af469-152">See Also</span></span>  
 [<span data-ttu-id="af469-153">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="af469-153">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="af469-154">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="af469-154">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="af469-155">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="af469-155">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
