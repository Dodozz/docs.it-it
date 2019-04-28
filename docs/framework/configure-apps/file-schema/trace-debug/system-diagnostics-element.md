---
title: Elemento < Diagnostics >
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 026805ffb9b89aa55e84cf9a5c4afb8ed63cec09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673693"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="bf4d1-102">\<System. Diagnostics > elemento</span><span class="sxs-lookup"><span data-stu-id="bf4d1-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="bf4d1-103">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="bf4d1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bf4d1-104">\<configuration></span></span>  
<span data-ttu-id="bf4d1-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="bf4d1-105">\<system.diagnostics></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf4d1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf4d1-106">Syntax</span></span>  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf4d1-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bf4d1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="bf4d1-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf4d1-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="bf4d1-109">Attributes</span></span>  
 <span data-ttu-id="bf4d1-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bf4d1-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bf4d1-111">Child Elements</span></span>  
  
|<span data-ttu-id="bf4d1-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf4d1-112">Element</span></span>|<span data-ttu-id="bf4d1-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf4d1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf4d1-114">\<assert></span><span class="sxs-lookup"><span data-stu-id="bf4d1-114">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="bf4d1-115">Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-115">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="bf4d1-116">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="bf4d1-116">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="bf4d1-117">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-117">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="bf4d1-118">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="bf4d1-118">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="bf4d1-119">Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-119">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="bf4d1-120">I listener identificati come listener condivisi possono essere aggiunti alle origini o delle tracce in base al nome.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-120">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[<span data-ttu-id="bf4d1-121">\<sources></span><span class="sxs-lookup"><span data-stu-id="bf4d1-121">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="bf4d1-122">Specifica le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-122">Specifies trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="bf4d1-123">\<switches></span><span class="sxs-lookup"><span data-stu-id="bf4d1-123">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="bf4d1-124">Contiene le opzioni di traccia e i livelli in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-124">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[<span data-ttu-id="bf4d1-125">\<trace></span><span class="sxs-lookup"><span data-stu-id="bf4d1-125">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="bf4d1-126">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-126">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf4d1-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bf4d1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="bf4d1-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf4d1-128">Element</span></span>|<span data-ttu-id="bf4d1-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf4d1-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bf4d1-130">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf4d1-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf4d1-131">Example</span></span>  
 <span data-ttu-id="bf4d1-132">Nell'esempio seguente viene illustrato come incorporare un'opzione di traccia e un listener di traccia all'interno di  **\<System. Diagnostics >** elemento.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-132">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="bf4d1-133">Il `General` opzione di traccia è impostato sul <xref:System.Diagnostics.TraceLevel> livello.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-133">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="bf4d1-134">Il listener di traccia `myListener` crea un file denominato `MyListener.log` e scrive l'output del file.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-134">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf4d1-135">In .NET Framework versione 2.0 è possibile usare testo per specificare il valore di un'opzione,</span><span class="sxs-lookup"><span data-stu-id="bf4d1-135">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="bf4d1-136">Ad esempio, è possibile specificare `true` per un <xref:System.Diagnostics.BooleanSwitch> o usare il testo che rappresenta un valore di enumerazione, ad esempio `Error` per un <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-136">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="bf4d1-137">La riga `<add name="myTraceSwitch" value="Error" />` equivale a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="bf4d1-137">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf4d1-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf4d1-138">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="bf4d1-139">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="bf4d1-139">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
