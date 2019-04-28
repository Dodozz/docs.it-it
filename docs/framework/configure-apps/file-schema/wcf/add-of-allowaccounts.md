---
title: <add> di <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 1c6764b37b2aa5349b8ccf63e6b7c2bc580b69b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701138"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="94056-102">\<aggiungere > di \<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="94056-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="94056-103">Specifica un account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="94056-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="94056-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="94056-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94056-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94056-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94056-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="94056-106">Attributes and Elements</span></span>  
 <span data-ttu-id="94056-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="94056-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94056-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="94056-108">Attributes</span></span>  
  
|<span data-ttu-id="94056-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="94056-109">Attribute</span></span>|<span data-ttu-id="94056-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94056-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94056-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="94056-111">securityIdentifier</span></span>|<span data-ttu-id="94056-112">Stringa che specifica un identificatore univoco usato per identificare un account utente.</span><span class="sxs-lookup"><span data-stu-id="94056-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="94056-113">I valori predefiniti sono LocalSystem, Administrators, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="94056-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94056-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="94056-114">Child Elements</span></span>  
 <span data-ttu-id="94056-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="94056-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="94056-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="94056-116">Parent Elements</span></span>  
  
|<span data-ttu-id="94056-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="94056-117">Element</span></span>|<span data-ttu-id="94056-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94056-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94056-119">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="94056-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="94056-120">Una raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione.</span><span class="sxs-lookup"><span data-stu-id="94056-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94056-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="94056-121">Example</span></span>  
 <span data-ttu-id="94056-122">Nell'esempio di configurazione seguente i cinque identificatori predefiniti per gli account utente vengono aggiunti a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="94056-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="94056-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94056-123">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
