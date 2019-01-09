---
title: '&lt;endpoint&gt; di &lt;client&gt;'
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 47b3599ed2d0868fcbc4a04a28936bcfe1c9c3f1
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147005"
---
# <a name="ltendpointgt-of-ltclientgt"></a><span data-ttu-id="00233-102">&lt;endpoint&gt; di &lt;client&gt;</span><span class="sxs-lookup"><span data-stu-id="00233-102">&lt;endpoint&gt; of &lt;client&gt;</span></span>
<span data-ttu-id="00233-103">Specifica proprietà di contratto, associazione e indirizzo dell'endpoint del canale usato dai client per connettersi agli endpoint del servizio nel server.</span><span class="sxs-lookup"><span data-stu-id="00233-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="00233-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="00233-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="00233-105">\<client></span><span class="sxs-lookup"><span data-stu-id="00233-105">\<client></span></span>  
<span data-ttu-id="00233-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="00233-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00233-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00233-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00233-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="00233-108">Attributes and Elements</span></span>  
 <span data-ttu-id="00233-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="00233-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00233-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="00233-110">Attributes</span></span>  
  
|<span data-ttu-id="00233-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="00233-111">Attribute</span></span>|<span data-ttu-id="00233-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00233-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00233-113">address</span><span class="sxs-lookup"><span data-stu-id="00233-113">address</span></span>|<span data-ttu-id="00233-114">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="00233-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="00233-115">Specifica l'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="00233-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="00233-116">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="00233-116">The default is an empty string.</span></span> <span data-ttu-id="00233-117">L'indirizzo deve essere un URI assoluto.</span><span class="sxs-lookup"><span data-stu-id="00233-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="00233-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="00233-118">behaviorConfiguration</span></span>|<span data-ttu-id="00233-119">Stringa che contiene il nome del comportamento da usare per creare un'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="00233-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="00233-120">Il nome del comportamento deve essere nell'ambito del punto in cui il servizio è definito.</span><span class="sxs-lookup"><span data-stu-id="00233-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="00233-121">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="00233-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="00233-122">associazione</span><span class="sxs-lookup"><span data-stu-id="00233-122">binding</span></span>|<span data-ttu-id="00233-123">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="00233-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="00233-124">Stringa che indica il tipo di associazione da usare.</span><span class="sxs-lookup"><span data-stu-id="00233-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="00233-125">Il tipo deve avere una sezione di configurazione registrata perché sia possibile farvi riferimento.</span><span class="sxs-lookup"><span data-stu-id="00233-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="00233-126">Il tipo viene registrato in base al nome di sezione invece che al nome del tipo di associazione.</span><span class="sxs-lookup"><span data-stu-id="00233-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="00233-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="00233-127">bindingConfiguration</span></span>|<span data-ttu-id="00233-128">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="00233-128">Optional.</span></span> <span data-ttu-id="00233-129">Stringa che contiene il nome della configurazione di associazione da usare quando viene creata un'istanza dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="00233-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="00233-130">La configurazione di associazione deve essere nell'ambito del punto in cui l'endpoint viene definito.</span><span class="sxs-lookup"><span data-stu-id="00233-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="00233-131">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="00233-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="00233-132">Questo attributo viene usato in combinazione con `binding` per fare riferimento a una configurazione di associazione specifica nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="00233-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="00233-133">Impostare questo attributo se si sta tentando di usare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="00233-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="00233-134">In caso contrario, può venire generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="00233-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="00233-135">contratto</span><span class="sxs-lookup"><span data-stu-id="00233-135">contract</span></span>|<span data-ttu-id="00233-136">Attributo stringa obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="00233-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="00233-137">Stringa che indica quale contratto viene esposto da questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="00233-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="00233-138">L'assembly deve implementare il tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="00233-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="00233-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="00233-139">endpointConfiguration</span></span>|<span data-ttu-id="00233-140">Stringa che specifica il nome dell'endpoint standard impostato dall'attributo `kind` che fa riferimento alle informazioni di configurazione aggiuntive di questo endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="00233-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="00233-141">Lo stesso nome deve essere definito nella sezione `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="00233-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="00233-142">kind</span><span class="sxs-lookup"><span data-stu-id="00233-142">kind</span></span>|<span data-ttu-id="00233-143">Stringa che specifica il tipo di endpoint standard applicato.</span><span class="sxs-lookup"><span data-stu-id="00233-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="00233-144">Il tipo deve essere registrato nella sezione `<extensions>` o in machine.config. Se non specificato, viene creato un endpoint del canale comune.</span><span class="sxs-lookup"><span data-stu-id="00233-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="00233-145">name</span><span class="sxs-lookup"><span data-stu-id="00233-145">name</span></span>|<span data-ttu-id="00233-146">Attributo stringa facoltativo.</span><span class="sxs-lookup"><span data-stu-id="00233-146">Optional string attribute.</span></span> <span data-ttu-id="00233-147">L'attributo identifica in modo univoco un endpoint per un dato contratto.</span><span class="sxs-lookup"><span data-stu-id="00233-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="00233-148">È possibile definire più client per un determinato tipo di contratto.</span><span class="sxs-lookup"><span data-stu-id="00233-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="00233-149">Ogni definizione deve essere differenziata da un nome di configurazione univoco.</span><span class="sxs-lookup"><span data-stu-id="00233-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="00233-150">Se questo attributo viene omesso, l'endpoint corrispondente viene usato come endpoint predefinito associato al tipo di contratto specificato.</span><span class="sxs-lookup"><span data-stu-id="00233-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="00233-151">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="00233-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="00233-152">L'attributo `name` di un'associazione viene usato per l'esportazione della definizione tramite WSDL.</span><span class="sxs-lookup"><span data-stu-id="00233-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00233-153">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="00233-153">Child Elements</span></span>  
  
|<span data-ttu-id="00233-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="00233-154">Element</span></span>|<span data-ttu-id="00233-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00233-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00233-156">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="00233-156">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="00233-157">Raccolte di intestazioni di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="00233-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="00233-158">\<identità ></span><span class="sxs-lookup"><span data-stu-id="00233-158">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="00233-159">Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.</span><span class="sxs-lookup"><span data-stu-id="00233-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00233-160">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="00233-160">Parent Elements</span></span>  
  
|<span data-ttu-id="00233-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="00233-161">Element</span></span>|<span data-ttu-id="00233-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00233-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00233-163">\<client ></span><span class="sxs-lookup"><span data-stu-id="00233-163">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="00233-164">Sezione di configurazione che definisce un elenco di endpoint ai quali può connettersi un client.</span><span class="sxs-lookup"><span data-stu-id="00233-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="00233-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="00233-165">Example</span></span>  
 <span data-ttu-id="00233-166">Di seguito è riportato un esempio di configurazione dell'endpoint di un canale.</span><span class="sxs-lookup"><span data-stu-id="00233-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="00233-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00233-167">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>  
 <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 [<span data-ttu-id="00233-168">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="00233-168">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="00233-169">Client</span><span class="sxs-lookup"><span data-stu-id="00233-169">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
