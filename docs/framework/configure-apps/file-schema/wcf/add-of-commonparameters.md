---
title: <add> di <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 6aaba3f82966ad4496e6edaae06b5d7a8aef3863
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199485"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="94e6c-102">\<aggiungere > di \<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="94e6c-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="94e6c-103">Specifica una coppia nome/valore di parametri che vengono usati globalmente tra più servizi.</span><span class="sxs-lookup"><span data-stu-id="94e6c-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="94e6c-104">Questo parametro in genere contiene una stringa di connessione al database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="94e6c-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="94e6c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="94e6c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="94e6c-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="94e6c-106">\<behaviors></span></span>  
<span data-ttu-id="94e6c-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="94e6c-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="94e6c-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="94e6c-108">\<behavior></span></span>  
<span data-ttu-id="94e6c-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="94e6c-109">\<workflowRuntime></span></span>  
<span data-ttu-id="94e6c-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="94e6c-110">\<commonParameters></span></span>  
<span data-ttu-id="94e6c-111">\<add></span><span class="sxs-lookup"><span data-stu-id="94e6c-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e6c-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94e6c-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94e6c-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="94e6c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="94e6c-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="94e6c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94e6c-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="94e6c-115">Attributes</span></span>  
  
|<span data-ttu-id="94e6c-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="94e6c-116">Attribute</span></span>|<span data-ttu-id="94e6c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94e6c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94e6c-118">name</span><span class="sxs-lookup"><span data-stu-id="94e6c-118">name</span></span>|<span data-ttu-id="94e6c-119">Nome del parametro specificato per un servizio.</span><span class="sxs-lookup"><span data-stu-id="94e6c-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="94e6c-120">predefinito</span><span class="sxs-lookup"><span data-stu-id="94e6c-120">value</span></span>|<span data-ttu-id="94e6c-121">Valore del parametro specificato per un servizio.</span><span class="sxs-lookup"><span data-stu-id="94e6c-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94e6c-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="94e6c-122">Child Elements</span></span>  
 <span data-ttu-id="94e6c-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="94e6c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94e6c-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="94e6c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="94e6c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="94e6c-125">Element</span></span>|<span data-ttu-id="94e6c-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94e6c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94e6c-127">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="94e6c-127">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="94e6c-128">Raccolta di parametri comuni usati dai servizi.</span><span class="sxs-lookup"><span data-stu-id="94e6c-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="94e6c-129">Questa raccolta in genere contiene la stringa di connessione del database che potrebbe essere condivisa dai servizi durevoli.</span><span class="sxs-lookup"><span data-stu-id="94e6c-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94e6c-130">Note</span><span class="sxs-lookup"><span data-stu-id="94e6c-130">Remarks</span></span>  
 <span data-ttu-id="94e6c-131">L'elemento `<commonParameters>` definisce qualsiasi parametro usato globalmente tra più servizi, ad esempio `ConnectionString` quando si usa <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="94e6c-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="94e6c-132">È possibile consentire a servizi che eseguono il commit di batch di lavoro su archivi di persistenza, ad esempio <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> e <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, di ritentare la transazione usando il parametro `EnableRetries`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="94e6c-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="94e6c-133">Si noti che il `EnableRetries` parametro può essere impostato su un livello globale (come illustrato nella *CommonParameters* sezione) o per servizi individuali che supportano `EnableRetries` (come illustrato nel *servizi*sezione).</span><span class="sxs-lookup"><span data-stu-id="94e6c-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="94e6c-134">Per altre informazioni sull'uso di un file di configurazione per controllare il comportamento di un <xref:System.Workflow.Runtime.WorkflowRuntime> oggetto di un'applicazione host di Windows Workflow Foundation, vedere [i file di configurazione del flusso di lavoro](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="94e6c-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e6c-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="94e6c-135">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="94e6c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94e6c-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- [<span data-ttu-id="94e6c-137">File di configurazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="94e6c-137">Workflow Configuration Files</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
- [<span data-ttu-id="94e6c-138">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="94e6c-138">\<commonParameters></span></span>](commonparameters.md)
