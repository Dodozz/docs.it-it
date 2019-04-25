---
title: Elemento <connectionManagement> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 4412fe30bfb8dcb3d7576df18cb2a472463d935c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674584"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="6a518-102">\<connectionManagement > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6a518-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="6a518-103">Specifica il numero massimo di connessioni a un host di rete.</span><span class="sxs-lookup"><span data-stu-id="6a518-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="6a518-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6a518-104">\<configuration></span></span>  
<span data-ttu-id="6a518-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6a518-105">\<system.net></span></span>  
<span data-ttu-id="6a518-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="6a518-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a518-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a518-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a518-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6a518-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6a518-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6a518-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a518-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6a518-110">Attributes</span></span>  
 <span data-ttu-id="6a518-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6a518-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6a518-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6a518-112">Child Elements</span></span>  
  
|<span data-ttu-id="6a518-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="6a518-113">**Element**</span></span>|<span data-ttu-id="6a518-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6a518-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6a518-115">add</span><span class="sxs-lookup"><span data-stu-id="6a518-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="6a518-116">Aggiunge un indirizzo IP o nome DNS all'elenco di gestione delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="6a518-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="6a518-117">clear</span><span class="sxs-lookup"><span data-stu-id="6a518-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="6a518-118">Cancella l'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="6a518-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="6a518-119">remove</span><span class="sxs-lookup"><span data-stu-id="6a518-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="6a518-120">Rimuove un indirizzo IP o nome DNS dall'elenco di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="6a518-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a518-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6a518-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6a518-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="6a518-122">**Element**</span></span>|<span data-ttu-id="6a518-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6a518-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6a518-124">system.net</span><span class="sxs-lookup"><span data-stu-id="6a518-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="6a518-125">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a518-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a518-126">Note</span><span class="sxs-lookup"><span data-stu-id="6a518-126">Remarks</span></span>  
 <span data-ttu-id="6a518-127">Il `connectionManagement` elemento definisce il numero massimo di connessioni a un server o un gruppo di server.</span><span class="sxs-lookup"><span data-stu-id="6a518-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6a518-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="6a518-128">Configuration Files</span></span>  
 <span data-ttu-id="6a518-129">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6a518-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a518-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a518-130">Example</span></span>  
 <span data-ttu-id="6a518-131">Nell'esempio seguente consente di configurare un'applicazione di usare quattro connessioni al server `www.contoso.com` e due connessioni a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="6a518-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a518-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a518-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="6a518-133">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="6a518-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
