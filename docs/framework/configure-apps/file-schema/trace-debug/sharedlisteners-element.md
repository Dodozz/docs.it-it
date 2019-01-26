---
title: '&lt;sharedListeners&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 7eaeffb365dd2c9999d4faa6b28c6d50e8cd6a6e
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084328"
---
# <a name="ltsharedlistenersgt-element"></a><span data-ttu-id="a1d9b-102">&lt;sharedListeners&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="a1d9b-102">&lt;sharedListeners&gt; Element</span></span>
<span data-ttu-id="a1d9b-103">Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="a1d9b-104">Questi listener non ricevono tutte le tracce per impostazione predefinita e non è possibile recuperare questi listener in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="a1d9b-105">I listener identificati come listener condivisi possono essere aggiunti alle origini o delle tracce in base al nome.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="a1d9b-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a1d9b-106">\<configuration></span></span>  
<span data-ttu-id="a1d9b-107">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="a1d9b-107">\<system.diagnostics></span></span>  
<span data-ttu-id="a1d9b-108">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="a1d9b-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d9b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1d9b-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1d9b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a1d9b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a1d9b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1d9b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="a1d9b-112">Attributes</span></span>  
 <span data-ttu-id="a1d9b-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a1d9b-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a1d9b-114">Child Elements</span></span>  
  
|<span data-ttu-id="a1d9b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1d9b-115">Element</span></span>|<span data-ttu-id="a1d9b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1d9b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1d9b-117">\<add></span><span class="sxs-lookup"><span data-stu-id="a1d9b-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="a1d9b-118">Aggiunge un listener alla raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1d9b-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a1d9b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a1d9b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1d9b-120">Element</span></span>|<span data-ttu-id="a1d9b-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1d9b-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="a1d9b-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a1d9b-123">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1d9b-124">Note</span><span class="sxs-lookup"><span data-stu-id="a1d9b-124">Remarks</span></span>  
 <span data-ttu-id="a1d9b-125">Aggiunta di un listener per la raccolta di listener condivisi non renderlo un listener attivo.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="a1d9b-126">È necessario comunque aggiungerlo a un'origine di traccia o da una traccia, aggiungerlo al `Listeners` raccolta per tale elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="a1d9b-127">Le classi di listener in .NET Framework derivano dal <xref:System.Diagnostics.TraceListener> classe.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="a1d9b-128">Questo elemento può essere usato nel file di configurazione del computer (Machine. config) e il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1d9b-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1d9b-129">Example</span></span>  
 <span data-ttu-id="a1d9b-130">Nell'esempio seguente viene illustrato come utilizzare il `<sharedListeners>` elemento a cui aggiungere il listener `console` per il `Listeners` raccolta sia per il <xref:System.Diagnostics.TraceSource> e <xref:System.Diagnostics.Trace> classi.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="a1d9b-131">Il listener di traccia console scrive le informazioni di traccia nella console mediante chiamate a <xref:System.Diagnostics.TraceSource> o <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="a1d9b-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## <a name="see-also"></a><span data-ttu-id="a1d9b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1d9b-132">See also</span></span>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="a1d9b-133">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="a1d9b-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="a1d9b-134">Listener di traccia</span><span class="sxs-lookup"><span data-stu-id="a1d9b-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
