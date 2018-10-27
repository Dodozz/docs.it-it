---
title: '&lt;specifiedPickupDirectory&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: d39fdf910aaec1d0a53d68fa7c6715ec344e734d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194631"
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a><span data-ttu-id="24451-102">&lt;specifiedPickupDirectory&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="24451-102">&lt;specifiedPickupDirectory&gt; Element (Network Settings)</span></span>
<span data-ttu-id="24451-103">Configura la directory locale per un server SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="24451-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="24451-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="24451-104">\<configuration></span></span>  
<span data-ttu-id="24451-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="24451-105">\<system.net></span></span>  
<span data-ttu-id="24451-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="24451-106">\<mailSettings></span></span>  
<span data-ttu-id="24451-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="24451-107">\<smtp></span></span>  
<span data-ttu-id="24451-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="24451-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24451-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24451-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24451-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="24451-110">Attributes and Elements</span></span>  
 <span data-ttu-id="24451-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="24451-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24451-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="24451-112">Attributes</span></span>  
  
|<span data-ttu-id="24451-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="24451-113">Attribute</span></span>|<span data-ttu-id="24451-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24451-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="24451-115">La directory in cui le applicazioni salvano i messaggio di posta elettronica per l'elaborazione successiva con il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="24451-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24451-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="24451-116">Child Elements</span></span>  
 <span data-ttu-id="24451-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="24451-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24451-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="24451-118">Parent Elements</span></span>  
  
|<span data-ttu-id="24451-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="24451-119">Element</span></span>|<span data-ttu-id="24451-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24451-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24451-121">\<SMTP > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="24451-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="24451-122">Consente di configurare le opzioni di invio della posta elettronica SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="24451-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24451-123">Note</span><span class="sxs-lookup"><span data-stu-id="24451-123">Remarks</span></span>  
 <span data-ttu-id="24451-124">Con l'attributo `specifiedPickupDirectory` viene impostata la directory in cui nelle applicazioni vengono salvati i messaggi di posta elettronica da elaborare mediante il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="24451-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24451-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="24451-125">Example</span></span>  
 <span data-ttu-id="24451-126">Nell'esempio seguente specifica c:\maildrop come la directory di prelievo della posta.</span><span class="sxs-lookup"><span data-stu-id="24451-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="24451-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24451-127">See Also</span></span>  
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>  
- [<span data-ttu-id="24451-128">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="24451-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
