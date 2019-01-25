---
title: '&lt;oidMap&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 19983e4d17ac2843385685a6b8b247d16f4cc081
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700462"
---
# <a name="ltoidmapgt-element"></a><span data-ttu-id="89119-102">&lt;oidMap&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="89119-102">&lt;oidMap&gt; Element</span></span>
<span data-ttu-id="89119-103">Contiene mapping di identificatore (OID) ASN.1 oggetto alle classi.</span><span class="sxs-lookup"><span data-stu-id="89119-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="89119-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="89119-104">\<configuration></span></span>  
<span data-ttu-id="89119-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="89119-105">\<mscorlib></span></span>  
<span data-ttu-id="89119-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="89119-106">\<cryptographySettings></span></span>  
<span data-ttu-id="89119-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="89119-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89119-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89119-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89119-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="89119-109">Attributes and Elements</span></span>  
 <span data-ttu-id="89119-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="89119-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89119-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="89119-111">Attributes</span></span>  
 <span data-ttu-id="89119-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="89119-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89119-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="89119-113">Child Elements</span></span>  
  
|<span data-ttu-id="89119-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="89119-114">Element</span></span>|<span data-ttu-id="89119-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89119-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89119-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="89119-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="89119-117">Esegue il mapping di OID ASN.1 a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="89119-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89119-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="89119-118">Parent Elements</span></span>  
  
|<span data-ttu-id="89119-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="89119-119">Element</span></span>|<span data-ttu-id="89119-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89119-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="89119-121">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="89119-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="89119-122">Contiene le impostazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="89119-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="89119-123">Contiene il `cryptographySettings` elemento.</span><span class="sxs-lookup"><span data-stu-id="89119-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="89119-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="89119-124">Example</span></span>  
 <span data-ttu-id="89119-125">Nell'esempio seguente viene illustrato come utilizzare il  **\<oidMap >** elemento per contenere il mapping di un OID per l'algoritmo hash RIPEMD-160 a un'implementazione dell'algoritmo di hash.</span><span class="sxs-lookup"><span data-stu-id="89119-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89119-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89119-126">See also</span></span>
- [<span data-ttu-id="89119-127">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="89119-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="89119-128">Schema delle impostazioni di crittografia</span><span class="sxs-lookup"><span data-stu-id="89119-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="89119-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="89119-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="89119-130">Configurazione di classi di crittografia</span><span class="sxs-lookup"><span data-stu-id="89119-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="89119-131">Mapping di identificatori di oggetti ad algoritmi di crittografia</span><span class="sxs-lookup"><span data-stu-id="89119-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
