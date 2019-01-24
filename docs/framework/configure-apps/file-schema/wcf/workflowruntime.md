---
title: '&lt;workflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 5560d74a5c69a01a2e05d4c2461a280244e4cd0d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580616"
---
# <a name="ltworkflowruntimegt"></a><span data-ttu-id="7a56f-102">&lt;workflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="7a56f-102">&lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="7a56f-103">Specifica le impostazioni per un'istanza di <xref:System.Workflow.Runtime.WorkflowRuntime> per ospitare i servizi Windows Communication Foundation (WCF) in base al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7a56f-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="7a56f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7a56f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7a56f-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7a56f-105">\<behaviors></span></span>  
<span data-ttu-id="7a56f-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7a56f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="7a56f-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7a56f-107">\<behavior></span></span>  
<span data-ttu-id="7a56f-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="7a56f-108">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a56f-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a56f-109">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"
                 enablePerformanceCounters="Boolean"
                 name="String"
                 validateOnCreate="Boolean">
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a56f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7a56f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7a56f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7a56f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a56f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7a56f-112">Attributes</span></span>  
  
|<span data-ttu-id="7a56f-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7a56f-113">Attribute</span></span>|<span data-ttu-id="7a56f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a56f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a56f-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="7a56f-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="7a56f-116">Valore <xref:System.TimeSpan> facoltativo che specifica la durata massima di memorizzazione in stato inattivo di un'istanza del flusso di lavoro prima che venga interrotta o scaricata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7a56f-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="7a56f-117">Se l'attributo `PersistenceService` di workflowruntime esegue il metodo unloadOnIdle, questo attributo viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="7a56f-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="7a56f-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="7a56f-118">enablePerformanceCounters</span></span>|<span data-ttu-id="7a56f-119">Valore booleano facoltativo che specifica se i contatori delle prestazioni sono attivi.</span><span class="sxs-lookup"><span data-stu-id="7a56f-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="7a56f-120">I contatori delle prestazioni forniscono informazioni su varie statistiche correlate al flusso di lavoro, ma provocano una riduzione delle prestazioni quando il motore di runtime del flusso di lavoro viene avviato e quando le istanze del flusso di lavoro sono in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7a56f-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="7a56f-121">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="7a56f-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="7a56f-122">name</span><span class="sxs-lookup"><span data-stu-id="7a56f-122">name</span></span>|<span data-ttu-id="7a56f-123">Stringa contenente il nome del motore di runtime del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7a56f-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="7a56f-124">Il nome viene usato in output per distinguere questo runtime da altri runtime che potrebbero essere in esecuzione nel sistema, ad esempio nei contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7a56f-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="7a56f-125">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="7a56f-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="7a56f-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="7a56f-126">validateOnCreate</span></span>|<span data-ttu-id="7a56f-127">Valore booleano facoltativo che specifica se all'apertura dell'elemento WorkflowServiceHost verrà eseguita la convalida della definizione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7a56f-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="7a56f-128">Quando questo attributo viene impostato su `true`, la convalida del flusso di lavoro viene eseguita ogni volta che viene chiamato il metodo `WorkflowServiceHost.Open`.</span><span class="sxs-lookup"><span data-stu-id="7a56f-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="7a56f-129">Se vengono individuati errori di convalida, viene generata un'eccezione <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException>.</span><span class="sxs-lookup"><span data-stu-id="7a56f-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="7a56f-130">Quando questa proprietà è impostata su `false` la definizione del flusso di lavoro non viene convalidata.</span><span class="sxs-lookup"><span data-stu-id="7a56f-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="7a56f-131">Il valore predefinito di questa proprietà è `true`.</span><span class="sxs-lookup"><span data-stu-id="7a56f-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a56f-132">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7a56f-132">Child Elements</span></span>  
  
|<span data-ttu-id="7a56f-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a56f-133">Element</span></span>|<span data-ttu-id="7a56f-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a56f-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a56f-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="7a56f-135">commonParameters</span></span>|<span data-ttu-id="7a56f-136">Raccolta di parametri comuni usati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="7a56f-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="7a56f-137">Questa raccolta in genere contiene la stringa di connessione del database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="7a56f-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="7a56f-138">servizi</span><span class="sxs-lookup"><span data-stu-id="7a56f-138">services</span></span>|<span data-ttu-id="7a56f-139">Raccolta di servizi da aggiungere al motore di <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="7a56f-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="7a56f-140">Gli elementi sono di tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="7a56f-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="7a56f-141">I servizi specificati nella raccolta verranno inizializzati dal motore di runtime del flusso di lavoro e verranno aggiunti ai relativi servizi quando verrà chiamato il costruttore <xref:System.Workflow.Runtime.WorkflowRuntime> appropriato.</span><span class="sxs-lookup"><span data-stu-id="7a56f-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="7a56f-142">Pertanto, i servizi specificati nella raccolta devono seguire regole precise riguardanti le firme dei relativi costruttori.</span><span class="sxs-lookup"><span data-stu-id="7a56f-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="7a56f-143">Per altre informazioni, vedere <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="7a56f-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7a56f-144">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7a56f-144">Parent Elements</span></span>  
  
|<span data-ttu-id="7a56f-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a56f-145">Element</span></span>|<span data-ttu-id="7a56f-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a56f-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a56f-147">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7a56f-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7a56f-148">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="7a56f-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a56f-149">Note</span><span class="sxs-lookup"><span data-stu-id="7a56f-149">Remarks</span></span>  
 <span data-ttu-id="7a56f-150">Per altre informazioni sull'uso di un file di configurazione per controllare il comportamento di un <xref:System.Workflow.Runtime.WorkflowRuntime> oggetto di un'applicazione host di Windows Workflow Foundation, vedere [i file di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="7a56f-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a56f-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a56f-151">Example</span></span>  
  
```xml  
<serviceBehaviors>
   <behavior name="ServiceBehavior">
      <workflowRuntime name="WorkflowServiceHostRuntime"
                       validateOnCreate="true"
                       enablePerformanceCounters="true">
         <commonParameters>
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
            <add name="EnableRetries" value="True" />
         </commonParameters>
         <services>
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>
         </services>
      </workflowRuntime>
   </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="7a56f-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a56f-152">See also</span></span>
- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="7a56f-153">[File di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="7a56f-153">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
