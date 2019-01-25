---
title: Elemento &lt;Field&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de8569c55ef50e3f18d084f7d7ad60c733e58e50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623105"
---
# <a name="ltfieldgt-element-net-native"></a><span data-ttu-id="d72b9-102">Elemento &lt;Field&gt; (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="d72b9-102">&lt;Field&gt; Element (.NET Native)</span></span>
<span data-ttu-id="d72b9-103">Applica i criteri di reflection di runtime a un campo.</span><span class="sxs-lookup"><span data-stu-id="d72b9-103">Applies runtime reflection policy to a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d72b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d72b9-104">Syntax</span></span>  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d72b9-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d72b9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d72b9-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d72b9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d72b9-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="d72b9-107">Attributes</span></span>  
  
|<span data-ttu-id="d72b9-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="d72b9-108">Attribute</span></span>|<span data-ttu-id="d72b9-109">Tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="d72b9-109">Attribute type</span></span>|<span data-ttu-id="d72b9-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d72b9-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="d72b9-111">Generale</span><span class="sxs-lookup"><span data-stu-id="d72b9-111">General</span></span>|<span data-ttu-id="d72b9-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d72b9-112">Required attribute.</span></span> <span data-ttu-id="d72b9-113">Specifica il nome del campo.</span><span class="sxs-lookup"><span data-stu-id="d72b9-113">Specifies the field name.</span></span>|  
|`Browse`|<span data-ttu-id="d72b9-114">Reflection</span><span class="sxs-lookup"><span data-stu-id="d72b9-114">Reflection</span></span>|<span data-ttu-id="d72b9-115">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d72b9-115">Optional attribute.</span></span> <span data-ttu-id="d72b9-116">Controlla le query per le informazioni o per l'enumerazione del campo, ma non abilita l'accesso dinamico al runtime.</span><span class="sxs-lookup"><span data-stu-id="d72b9-116">Controls querying for information about or enumerating the field but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="d72b9-117">Reflection</span><span class="sxs-lookup"><span data-stu-id="d72b9-117">Reflection</span></span>|<span data-ttu-id="d72b9-118">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d72b9-118">Optional attribute.</span></span> <span data-ttu-id="d72b9-119">Controlla l'accesso in fase di esecuzione al campo per abilitare la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="d72b9-119">Controls runtime access to the field to enable dynamic programming.</span></span> <span data-ttu-id="d72b9-120">Questo criterio assicura che un campo può essere impostato o recuperato dinamicamente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d72b9-120">This policy ensures that a field can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="d72b9-121">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="d72b9-121">Serialization</span></span>|<span data-ttu-id="d72b9-122">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d72b9-122">Optional attribute.</span></span> <span data-ttu-id="d72b9-123">Controlla l'accesso in fase di esecuzione a un campo per abilitare le istanze di tipo da serializzare in librerie quali il serializzatore JSON Newtonsoft o da usare per il data binding.</span><span class="sxs-lookup"><span data-stu-id="d72b9-123">Controls runtime access to a field to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="d72b9-124">Name (attributo)</span><span class="sxs-lookup"><span data-stu-id="d72b9-124">Name attribute</span></span>  
  
|<span data-ttu-id="d72b9-125">Valore</span><span class="sxs-lookup"><span data-stu-id="d72b9-125">Value</span></span>|<span data-ttu-id="d72b9-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d72b9-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d72b9-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="d72b9-127">*method_name*</span></span>|<span data-ttu-id="d72b9-128">Nome del campo.</span><span class="sxs-lookup"><span data-stu-id="d72b9-128">The field name.</span></span> <span data-ttu-id="d72b9-129">Il tipo del campo viene definito dall'elemento [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) padre.</span><span class="sxs-lookup"><span data-stu-id="d72b9-129">The type of the field is defined by the parent [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) or [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="d72b9-130">Tutti gli altri attributi</span><span class="sxs-lookup"><span data-stu-id="d72b9-130">All other attributes</span></span>  
  
|<span data-ttu-id="d72b9-131">Valore</span><span class="sxs-lookup"><span data-stu-id="d72b9-131">Value</span></span>|<span data-ttu-id="d72b9-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d72b9-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d72b9-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="d72b9-133">*policy_setting*</span></span>|<span data-ttu-id="d72b9-134">L'impostazione da applicare a questo tipo di criteri per il campo.</span><span class="sxs-lookup"><span data-stu-id="d72b9-134">The setting to apply to this policy type for the field.</span></span> <span data-ttu-id="d72b9-135">I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`.</span><span class="sxs-lookup"><span data-stu-id="d72b9-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="d72b9-136">Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).</span><span class="sxs-lookup"><span data-stu-id="d72b9-136">For more information, see [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d72b9-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d72b9-137">Child Elements</span></span>  
 <span data-ttu-id="d72b9-138">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d72b9-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d72b9-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d72b9-139">Parent Elements</span></span>  
  
|<span data-ttu-id="d72b9-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="d72b9-140">Element</span></span>|<span data-ttu-id="d72b9-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d72b9-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d72b9-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="d72b9-142">\<Type></span></span>](../../../docs/framework/net-native/type-element-net-native.md)|<span data-ttu-id="d72b9-143">Applica i criteri di reflection a un tipo e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="d72b9-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="d72b9-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="d72b9-144">\<TypeInstantiation></span></span>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|<span data-ttu-id="d72b9-145">Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="d72b9-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d72b9-146">Note</span><span class="sxs-lookup"><span data-stu-id="d72b9-146">Remarks</span></span>  
 <span data-ttu-id="d72b9-147">Se i criteri di un campo non sono definiti esplicitamente, l'evento eredita i criteri di runtime dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="d72b9-147">If a field's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72b9-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d72b9-148">See also</span></span>
- [<span data-ttu-id="d72b9-149">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="d72b9-149">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="d72b9-150">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="d72b9-150">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="d72b9-151">Impostazioni dei criteri delle direttive di runtime</span><span class="sxs-lookup"><span data-stu-id="d72b9-151">Runtime Directive Policy Settings</span></span>](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
