---
title: '&lt;declaredTypes&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: 405a6f21af1cb3508b7b88625101ed75f198bbaa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682667"
---
# <a name="ltdeclaredtypesgt"></a><span data-ttu-id="aaf30-102">&lt;declaredTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="aaf30-102">&lt;declaredTypes&gt;</span></span>
<span data-ttu-id="aaf30-103">Contiene i tipi noti usati dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="aaf30-103">Contains the known types that the <xref:System.Runtime.Serialization.DataContractSerializer> uses when deserializing.</span></span>  
  
 <span data-ttu-id="aaf30-104">Per altre informazioni sui contratti dati e i tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="aaf30-104">For more information about data contracts and known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
 <span data-ttu-id="aaf30-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="aaf30-105">system.runtime.serialization</span></span>  
<span data-ttu-id="aaf30-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="aaf30-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="aaf30-107">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="aaf30-107">\<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaf30-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aaf30-108">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaf30-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="aaf30-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aaf30-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="aaf30-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaf30-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="aaf30-111">Attributes</span></span>  
 <span data-ttu-id="aaf30-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="aaf30-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aaf30-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="aaf30-113">Child Elements</span></span>  
  
|<span data-ttu-id="aaf30-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="aaf30-114">Element</span></span>|<span data-ttu-id="aaf30-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aaf30-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaf30-116">\<add></span><span class="sxs-lookup"><span data-stu-id="aaf30-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|<span data-ttu-id="aaf30-117">Aggiunge tipi che richiedono tipi noti.</span><span class="sxs-lookup"><span data-stu-id="aaf30-117">Adds types that require known types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aaf30-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="aaf30-118">Parent Elements</span></span>  
  
|<span data-ttu-id="aaf30-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="aaf30-119">Element</span></span>|<span data-ttu-id="aaf30-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aaf30-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaf30-121">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="aaf30-121">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="aaf30-122">Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="aaf30-122">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaf30-123">Note</span><span class="sxs-lookup"><span data-stu-id="aaf30-123">Remarks</span></span>  
 <span data-ttu-id="aaf30-124">Per altre informazioni sui tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="aaf30-124">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaf30-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="aaf30-125">Example</span></span>  
 <span data-ttu-id="aaf30-126">Il codice XML seguente mostra i tipi dichiarati e i tipi noti aggiunti a un `DataContractSerializer` elemento.</span><span class="sxs-lookup"><span data-stu-id="aaf30-126">The following XML code shows declared types and known types added to a `DataContractSerializer` element.</span></span> <span data-ttu-id="aaf30-127">In particolare, l'esempio illustra l'aggiunta di tre tipi.</span><span class="sxs-lookup"><span data-stu-id="aaf30-127">The example shows three types being added.</span></span> <span data-ttu-id="aaf30-128">Il primo è un tipo personalizzato denominato "Orders" che usa un tipo conosciuto denominato "Item".</span><span class="sxs-lookup"><span data-stu-id="aaf30-128">The first is a custom type named "Orders" that uses a known type named "Item".</span></span> <span data-ttu-id="aaf30-129">Il secondo tipo dichiarato è un elenco <xref:System.Collections.Generic.List%601> che usa `Item` come tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="aaf30-129">The second declared type is a <xref:System.Collections.Generic.List%601> that uses `Item` as a known type.</span></span> <span data-ttu-id="aaf30-130">Infine, il terzo tipo dichiarato è un dizionario <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="aaf30-130">Finally the third declared type is a <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="aaf30-131">Il tipo della classe <xref:System.Collections.Generic.Dictionary%602> è un tipo generico, con due parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="aaf30-131">The <xref:System.Collections.Generic.Dictionary%602> class type is a generic type, with two type parameters.</span></span> <span data-ttu-id="aaf30-132">Il primo rappresenta la chiave e il secondo rappresenta il valore.</span><span class="sxs-lookup"><span data-stu-id="aaf30-132">The first represents the key and the second represents the value.</span></span> <span data-ttu-id="aaf30-133">Nell'esempio seguente viene aggiunto un elenco <xref:System.Collections.Generic.List%601> del secondo tipo (ovvero il valore) all'elenco dei tipi noti.</span><span class="sxs-lookup"><span data-stu-id="aaf30-133">The following example adds a <xref:System.Collections.Generic.List%601> of the second type (the value) to the list of known types.</span></span> <span data-ttu-id="aaf30-134">È necessario usare l'attributo `index` per specificare quale parametro di tipo usare nel tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="aaf30-134">You must use the `index` attribute to specify which type parameter to use in the known type.</span></span> <span data-ttu-id="aaf30-135">In questo caso, il tipo di valore viene indicato impostando l'attributo index su "1", in quanto la raccolta è in base zero.</span><span class="sxs-lookup"><span data-stu-id="aaf30-135">In this case, the value type is indicated by the index attribute set to "1" (the collection is zero-based).</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="aaf30-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaf30-136">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="aaf30-137">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="aaf30-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="aaf30-138">Tipi noti di contratto di dati</span><span class="sxs-lookup"><span data-stu-id="aaf30-138">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="aaf30-139">\<add></span><span class="sxs-lookup"><span data-stu-id="aaf30-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
