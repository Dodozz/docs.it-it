---
title: <oidEntry> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: c686d2b99ad66aec753a356b09fa3c7151193808
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219343"
---
# <a name="oidentry-element"></a><span data-ttu-id="f03f8-102">\<oidEntry > elemento</span><span class="sxs-lookup"><span data-stu-id="f03f8-102">\<oidEntry> Element</span></span>
<span data-ttu-id="f03f8-103">Esegue il mapping di un identificatore di oggetto (OID) ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="f03f8-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="f03f8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f03f8-104">\<configuration></span></span>  
<span data-ttu-id="f03f8-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="f03f8-105">\<mscorlib></span></span>  
<span data-ttu-id="f03f8-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="f03f8-106">\<cryptographySettings></span></span>  
<span data-ttu-id="f03f8-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="f03f8-107">\<oidMap></span></span>  
<span data-ttu-id="f03f8-108">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="f03f8-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03f8-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f03f8-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f03f8-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f03f8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f03f8-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f03f8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f03f8-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f03f8-112">Attributes</span></span>  
  
|<span data-ttu-id="f03f8-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="f03f8-113">Attribute</span></span>|<span data-ttu-id="f03f8-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f03f8-114">Description</span></span>|  
|---------------|-----------------|  
|**<span data-ttu-id="f03f8-115">OID</span><span class="sxs-lookup"><span data-stu-id="f03f8-115">OID</span></span>**|<span data-ttu-id="f03f8-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f03f8-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f03f8-117">Specifica il valore OID ASN.1 corrispondente all'algoritmo implementato dalla classe.</span><span class="sxs-lookup"><span data-stu-id="f03f8-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|**<span data-ttu-id="f03f8-118">name</span><span class="sxs-lookup"><span data-stu-id="f03f8-118">name</span></span>**|<span data-ttu-id="f03f8-119">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f03f8-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="f03f8-120">Specifica il valore per il **name** attributo il [ \<nameEntry >](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.</span><span class="sxs-lookup"><span data-stu-id="f03f8-120">Specifies the value for the **name** attribute in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f03f8-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f03f8-121">Child Elements</span></span>  
 <span data-ttu-id="f03f8-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f03f8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f03f8-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f03f8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f03f8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f03f8-124">Element</span></span>|<span data-ttu-id="f03f8-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f03f8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f03f8-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f03f8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f03f8-127">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f03f8-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="f03f8-128">Contiene il `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="f03f8-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="f03f8-129">Contiene mapping di identificatore (OID) ASN.1 oggetto alle classi.</span><span class="sxs-lookup"><span data-stu-id="f03f8-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f03f8-130">Note</span><span class="sxs-lookup"><span data-stu-id="f03f8-130">Remarks</span></span>  
 <span data-ttu-id="f03f8-131">Gli identificatori di oggetto ASN.1 identificano gli algoritmi in alcuni formati di crittografia.</span><span class="sxs-lookup"><span data-stu-id="f03f8-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="f03f8-132">Eseguire il mapping ai nomi descrittivi per gli algoritmi che si desidera identificare gli identificatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="f03f8-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f03f8-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="f03f8-133">Example</span></span>  
 <span data-ttu-id="f03f8-134">Nell'esempio seguente viene illustrato come utilizzare il  **\<oidEntry >** elemento per eseguire il mapping di un identificatore di oggetto per l'algoritmo hash RIPEMD-160 a un'implementazione dell'algoritmo di hash.</span><span class="sxs-lookup"><span data-stu-id="f03f8-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f03f8-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f03f8-135">See also</span></span>

- [<span data-ttu-id="f03f8-136">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f03f8-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f03f8-137">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="f03f8-137">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="f03f8-138">servizi crittografici</span><span class="sxs-lookup"><span data-stu-id="f03f8-138">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="f03f8-139">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="f03f8-139">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="f03f8-140">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="f03f8-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
