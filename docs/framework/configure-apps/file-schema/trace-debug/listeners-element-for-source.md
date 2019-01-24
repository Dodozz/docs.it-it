---
title: '&lt;i listener&gt; (elemento) per &lt;origine&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 949b6c7272b39900698b618760f5e5bad11ccc3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670641"
---
# <a name="ltlistenersgt-element-for-ltsourcegt"></a><span data-ttu-id="951d1-102">&lt;i listener&gt; (elemento) per &lt;origine&gt;</span><span class="sxs-lookup"><span data-stu-id="951d1-102">&lt;listeners&gt; Element for &lt;source&gt;</span></span>
<span data-ttu-id="951d1-103">Aggiunge o rimuove nei listener di traccia le <xref:System.Diagnostics.TraceSource.Listeners%2A> insieme per un <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="951d1-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="951d1-104">I listener indirizzano l'output di traccia a una destinazione appropriata, ad esempio un log, una finestra o un file di testo.</span><span class="sxs-lookup"><span data-stu-id="951d1-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="951d1-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="951d1-105">\<configuration></span></span>  
<span data-ttu-id="951d1-106">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="951d1-106">\<system.diagnostics></span></span>  
<span data-ttu-id="951d1-107">\<sources></span><span class="sxs-lookup"><span data-stu-id="951d1-107">\<sources></span></span>  
<span data-ttu-id="951d1-108">\<origine ></span><span class="sxs-lookup"><span data-stu-id="951d1-108">\<source></span></span>  
<span data-ttu-id="951d1-109">\<i listener > elemento</span><span class="sxs-lookup"><span data-stu-id="951d1-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951d1-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="951d1-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="951d1-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="951d1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="951d1-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="951d1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="951d1-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="951d1-113">Attributes</span></span>  
 <span data-ttu-id="951d1-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="951d1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="951d1-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="951d1-115">Child Elements</span></span>  
  
|<span data-ttu-id="951d1-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="951d1-116">Element</span></span>|<span data-ttu-id="951d1-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="951d1-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="951d1-118">\<add></span><span class="sxs-lookup"><span data-stu-id="951d1-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="951d1-119">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="951d1-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="951d1-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="951d1-120">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="951d1-121">Rimuove un listener dal `Listeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="951d1-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="951d1-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="951d1-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="951d1-123">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="951d1-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="951d1-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="951d1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="951d1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="951d1-125">Element</span></span>|<span data-ttu-id="951d1-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="951d1-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="951d1-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="951d1-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="951d1-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="951d1-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="951d1-129">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="951d1-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="951d1-130">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="951d1-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="951d1-131">Note</span><span class="sxs-lookup"><span data-stu-id="951d1-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="951d1-132">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="951d1-132">Configuration File</span></span>  
 <span data-ttu-id="951d1-133">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="951d1-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="951d1-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="951d1-134">Example</span></span>  
 <span data-ttu-id="951d1-135">Nell'esempio seguente viene illustrato come utilizzare il `<listeners>` elemento a cui aggiungere un listener di traccia console il `mySource` origine e di rimuovere il listener di traccia predefinito.</span><span class="sxs-lookup"><span data-stu-id="951d1-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="951d1-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="951d1-136">See also</span></span>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="951d1-137">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="951d1-137">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="951d1-138">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="951d1-138">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
