---
title: '&lt;comContracts&gt;'
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 2374155011b98822d47998cd1e4b8935db234752
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731526"
---
# <a name="ltcomcontractsgt"></a><span data-ttu-id="5da5c-102">&lt;comContracts&gt;</span><span class="sxs-lookup"><span data-stu-id="5da5c-102">&lt;comContracts&gt;</span></span>
<span data-ttu-id="5da5c-103">La sezione di configurazione `comContracts` contiene elementi che consentono di specificare varie proprietà di un contratto di servizio COM+ Integration.</span><span class="sxs-lookup"><span data-stu-id="5da5c-103">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="5da5c-104">Specifica di spazio dei nomi e contratto</span><span class="sxs-lookup"><span data-stu-id="5da5c-104">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="5da5c-105">Contratti di servizio COM+ integration sono limitati attualmente al `http://tempuri.org` spazio dei nomi e nome del contratto è derivato dall'interfaccia COM di supporto.</span><span class="sxs-lookup"><span data-stu-id="5da5c-105">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="5da5c-106">È tuttavia possibile specificare alternative usando la sezione `comContracts` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="5da5c-106">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="5da5c-107">Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi e il nome del contratto di servizio, oltre a un'opzione per imporre l'uso di associazioni con sessione.</span><span class="sxs-lookup"><span data-stu-id="5da5c-107">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="5da5c-108">Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.</span><span class="sxs-lookup"><span data-stu-id="5da5c-108">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="5da5c-109">Quando questa sezione è vuota, l'inizializzazione del servizio applica uno spazio dei nomi e un nome del contratto predefiniti presi dall'ID dell'interfaccia COM di supporto.</span><span class="sxs-lookup"><span data-stu-id="5da5c-109">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="5da5c-110">Inoltre, è possibile usare la [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elemento per specificare metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.</span><span class="sxs-lookup"><span data-stu-id="5da5c-110">In addition, you can use the [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="5da5c-111">È anche possibile usare la [ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) per specificare i tipi persistenti usati nell'integrazione.</span><span class="sxs-lookup"><span data-stu-id="5da5c-111">You can also use the [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="5da5c-112">Infine, è possibile usare la [ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) elemento includere definiti tipi utente (UDT) che devono essere inclusi nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="5da5c-112">Finally, you can use the [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da5c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5da5c-113">See also</span></span>
- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="5da5c-114">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="5da5c-114">\<exposedMethod></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)
- [<span data-ttu-id="5da5c-115">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="5da5c-115">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)
- [<span data-ttu-id="5da5c-116">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="5da5c-116">\<userDefinedType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)
- [<span data-ttu-id="5da5c-117">\<comContract></span><span class="sxs-lookup"><span data-stu-id="5da5c-117">\<comContract></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)
- [<span data-ttu-id="5da5c-118">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="5da5c-118">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="5da5c-119">Procedura: Configurare le impostazioni di servizio COM+</span><span class="sxs-lookup"><span data-stu-id="5da5c-119">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
