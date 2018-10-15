---
title: '&lt;Cancella&gt; (elemento) per connectionManagement (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7802a64716f8bde278fe3f8ed8214f6ac01eadbc
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316519"
---
# <a name="ltcleargt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="ef484-102">&lt;Cancella&gt; (elemento) per connectionManagement (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ef484-102">&lt;clear&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="ef484-103">Cancella l'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="ef484-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="ef484-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ef484-104">\<configuration></span></span>  
<span data-ttu-id="ef484-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ef484-105">\<system.net></span></span>  
<span data-ttu-id="ef484-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="ef484-106">\<connectionManagement></span></span>  
<span data-ttu-id="ef484-107">\<clear ></span><span class="sxs-lookup"><span data-stu-id="ef484-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef484-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef484-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef484-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef484-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ef484-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef484-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef484-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ef484-111">Attributes</span></span>  
 <span data-ttu-id="ef484-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ef484-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef484-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef484-113">Child Elements</span></span>  
 <span data-ttu-id="ef484-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ef484-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef484-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef484-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ef484-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ef484-116">**Element**</span></span>|<span data-ttu-id="ef484-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ef484-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ef484-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="ef484-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="ef484-119">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="ef484-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef484-120">Note</span><span class="sxs-lookup"><span data-stu-id="ef484-120">Remarks</span></span>  
 <span data-ttu-id="ef484-121">Il `clear` elemento cancella tutte le voci dall'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="ef484-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ef484-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ef484-122">Configuration Files</span></span>  
 <span data-ttu-id="ef484-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ef484-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef484-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef484-124">Example</span></span>  
 <span data-ttu-id="ef484-125">Nell'esempio seguente cancella l'elenco di gestione connessione e vengono aggiunte nuove voci di gestione connessione per il server `www.contoso.com` e tutti gli altri host di rete.</span><span class="sxs-lookup"><span data-stu-id="ef484-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef484-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef484-126">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="ef484-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ef484-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
