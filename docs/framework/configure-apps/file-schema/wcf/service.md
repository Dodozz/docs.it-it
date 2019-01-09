---
title: '&lt;Servizio&gt;'
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: ef0ae70440323c1ede5deca60e88f29861760e68
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145510"
---
# <a name="ltservicegt"></a><span data-ttu-id="125a3-102">&lt;Servizio&gt;</span><span class="sxs-lookup"><span data-stu-id="125a3-102">&lt;service&gt;</span></span>
<span data-ttu-id="125a3-103">L'elemento `service` contiene le impostazioni di un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="125a3-103">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="125a3-104">Contiene anche endpoint che espongono il servizio.</span><span class="sxs-lookup"><span data-stu-id="125a3-104">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="125a3-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="125a3-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="125a3-106">\<Services ></span><span class="sxs-lookup"><span data-stu-id="125a3-106">\<services></span></span>  
<span data-ttu-id="125a3-107">\<servizio ></span><span class="sxs-lookup"><span data-stu-id="125a3-107">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="125a3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="125a3-108">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="125a3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="125a3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="125a3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="125a3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="125a3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="125a3-111">Attributes</span></span>  
  
|<span data-ttu-id="125a3-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="125a3-112">Attribute</span></span>|<span data-ttu-id="125a3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="125a3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="125a3-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="125a3-114">behaviorConfiguration</span></span>|<span data-ttu-id="125a3-115">Stringa che contiene il nome del comportamento da usare per creare l'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="125a3-115">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="125a3-116">Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito.</span><span class="sxs-lookup"><span data-stu-id="125a3-116">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="125a3-117">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="125a3-117">The default value is an empty string.</span></span>|  
|<span data-ttu-id="125a3-118">name</span><span class="sxs-lookup"><span data-stu-id="125a3-118">name</span></span>|<span data-ttu-id="125a3-119">Attributo stringa obbligatorio che specifica il tipo del servizio per cui creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="125a3-119">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="125a3-120">Questa impostazione deve corrispondere a un tipo valido.</span><span class="sxs-lookup"><span data-stu-id="125a3-120">This setting must equate to a valid type.</span></span> <span data-ttu-id="125a3-121">Il formato deve essere `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="125a3-121">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="125a3-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="125a3-122">Child Elements</span></span>  
  
|<span data-ttu-id="125a3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="125a3-123">Element</span></span>|<span data-ttu-id="125a3-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="125a3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="125a3-125">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="125a3-125">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="125a3-126">Raccolta di elementi `endpoint` che espongono questo servizio.</span><span class="sxs-lookup"><span data-stu-id="125a3-126">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="125a3-127">\<host ></span><span class="sxs-lookup"><span data-stu-id="125a3-127">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="125a3-128">Specifica l'host dell'istanza del servizio.</span><span class="sxs-lookup"><span data-stu-id="125a3-128">Specifies the host of this service instance.</span></span> <span data-ttu-id="125a3-129">L'elemento è di tipo <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="125a3-129">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="125a3-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="125a3-130">Parent Elements</span></span>  
  
|<span data-ttu-id="125a3-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="125a3-131">Element</span></span>|<span data-ttu-id="125a3-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="125a3-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="125a3-133">\<services></span><span class="sxs-lookup"><span data-stu-id="125a3-133">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="125a3-134">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="125a3-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="125a3-135">Note</span><span class="sxs-lookup"><span data-stu-id="125a3-135">Remarks</span></span>  
 <span data-ttu-id="125a3-136">I servizi vengono definiti nella sezione `services` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="125a3-136">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="125a3-137">Un assembly può contenere un numero qualsiasi di servizi.</span><span class="sxs-lookup"><span data-stu-id="125a3-137">An assembly can contain any number of services.</span></span> <span data-ttu-id="125a3-138">Ogni servizio dispone di una propria sezione di configurazione `service`.</span><span class="sxs-lookup"><span data-stu-id="125a3-138">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="125a3-139">Questa sezione e il relativo contenuto definiscono il contratto di servizio, il comportamento e gli endpoint del particolare servizio.</span><span class="sxs-lookup"><span data-stu-id="125a3-139">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="125a3-140">L'elemento `behaviorConfiguration` è anche facoltativo.</span><span class="sxs-lookup"><span data-stu-id="125a3-140">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="125a3-141">Identifica il comportamento usato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="125a3-141">It identifies the behavior the service uses.</span></span> <span data-ttu-id="125a3-142">Il comportamento specificato in questo attributo deve collegarsi a un comportamento nell'ambito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="125a3-142">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="125a3-143">Ogni servizio espone uno o più endpoint, i quali sono provvisti di un proprio indirizzo e associazione.</span><span class="sxs-lookup"><span data-stu-id="125a3-143">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="125a3-144">Tutte le associazioni usate all'interno del file di configurazione devono essere definite nell'ambito del file.</span><span class="sxs-lookup"><span data-stu-id="125a3-144">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="125a3-145">Le associazioni sono collegate agli endpoint tramite la combinazione di attributi `name` e `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="125a3-145">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="125a3-146">L'attributo `name` descrive la sezione in cui è definita l'associazione.</span><span class="sxs-lookup"><span data-stu-id="125a3-146">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="125a3-147">L'attributo `bindingConfiguration` definisce quale configurazione viene usata tra quelle contenute nella sezione di associazione.</span><span class="sxs-lookup"><span data-stu-id="125a3-147">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="125a3-148">In una sezione di associazione è possibile definire diverse configurazioni.</span><span class="sxs-lookup"><span data-stu-id="125a3-148">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="125a3-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="125a3-149">Example</span></span>  
 <span data-ttu-id="125a3-150">Di seguito è riportato un esempio di una configurazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="125a3-150">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="125a3-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="125a3-151">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [<span data-ttu-id="125a3-152">Configurazione dei servizi</span><span class="sxs-lookup"><span data-stu-id="125a3-152">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
