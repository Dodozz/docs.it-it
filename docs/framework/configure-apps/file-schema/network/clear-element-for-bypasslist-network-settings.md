---
title: '&lt;Cancella&gt; (elemento) per bypasslist (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: 5c26857496d52f9fb98ef76a72cb72fe8d852349
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201413"
---
# <a name="ltcleargt-element-for-bypasslist-network-settings"></a><span data-ttu-id="cb701-102">&lt;Cancella&gt; (elemento) per bypasslist (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="cb701-102">&lt;clear&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="cb701-103">Cancella l'elenco proxy da ignorare.</span><span class="sxs-lookup"><span data-stu-id="cb701-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="cb701-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cb701-104">\<configuration></span></span>  
<span data-ttu-id="cb701-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="cb701-105">\<system.net></span></span>  
<span data-ttu-id="cb701-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="cb701-106">\<defaultProxy></span></span>  
<span data-ttu-id="cb701-107">\<BypassList ></span><span class="sxs-lookup"><span data-stu-id="cb701-107">\<bypasslist></span></span>  
<span data-ttu-id="cb701-108">\<clear ></span><span class="sxs-lookup"><span data-stu-id="cb701-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb701-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb701-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb701-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cb701-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cb701-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cb701-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb701-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cb701-112">Attributes</span></span>  
 <span data-ttu-id="cb701-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cb701-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cb701-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cb701-114">Child Elements</span></span>  
 <span data-ttu-id="cb701-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cb701-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb701-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cb701-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cb701-117">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cb701-117">**Element**</span></span>|<span data-ttu-id="cb701-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cb701-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cb701-119">BypassList</span><span class="sxs-lookup"><span data-stu-id="cb701-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="cb701-120">Fornisce un set di espressioni regolari che descrivono gli indirizzi che non usano un proxy.</span><span class="sxs-lookup"><span data-stu-id="cb701-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb701-121">Note</span><span class="sxs-lookup"><span data-stu-id="cb701-121">Remarks</span></span>  
 <span data-ttu-id="cb701-122">Il `clear` elemento cancella tutte le voci dell'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="cb701-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cb701-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="cb701-123">Configuration Files</span></span>  
 <span data-ttu-id="cb701-124">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cb701-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb701-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb701-125">Example</span></span>  
 <span data-ttu-id="cb701-126">Nell'esempio seguente cancella l'elenco di esclusione e quindi aggiunge due indirizzi all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="cb701-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="cb701-127">Il primo consente di ignorare il proxy per tutti i server nel dominio contoso.com. il secondo consente di ignorare il proxy per tutti i server il cui indirizzo IP inizia con 192.168.</span><span class="sxs-lookup"><span data-stu-id="cb701-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="cb701-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb701-128">See Also</span></span>  
- <xref:System.Net.WebProxy?displayProperty=nameWithType>  
- [<span data-ttu-id="cb701-129">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="cb701-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
