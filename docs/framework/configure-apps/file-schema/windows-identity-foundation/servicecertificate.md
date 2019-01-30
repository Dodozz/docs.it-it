---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 328d074f9edc5ddf871308a7e3d694bf94adea78
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261603"
---
# <a name="servicecertificate"></a><span data-ttu-id="66c13-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="66c13-101">\<serviceCertificate></span></span>
<span data-ttu-id="66c13-102">Configura il certificato X.509 utilizzato per crittografare e decrittografare i token.</span><span class="sxs-lookup"><span data-stu-id="66c13-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="66c13-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="66c13-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="66c13-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="66c13-104">\<federationConfiguration></span></span>  
<span data-ttu-id="66c13-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="66c13-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66c13-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66c13-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66c13-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="66c13-107">Attributes and Elements</span></span>  
 <span data-ttu-id="66c13-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="66c13-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66c13-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="66c13-109">Attributes</span></span>  
 <span data-ttu-id="66c13-110">nessuno</span><span class="sxs-lookup"><span data-stu-id="66c13-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="66c13-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="66c13-111">Child Elements</span></span>  
  
|<span data-ttu-id="66c13-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="66c13-112">Element</span></span>|<span data-ttu-id="66c13-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66c13-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66c13-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="66c13-114">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="66c13-115">Specifica le impostazioni che consentono di trovare e convalidare un certificato X.509 in un archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="66c13-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66c13-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="66c13-116">Parent Elements</span></span>  
  
|<span data-ttu-id="66c13-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="66c13-117">Element</span></span>|<span data-ttu-id="66c13-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66c13-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66c13-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="66c13-119">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="66c13-120">Contiene le impostazioni che consentono di configurare il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e il <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span><span class="sxs-lookup"><span data-stu-id="66c13-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="66c13-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="66c13-121">Example</span></span>  
 <span data-ttu-id="66c13-122">Il codice XML seguente viene illustrato come utilizzare il \<serviceCertificate > elemento.</span><span class="sxs-lookup"><span data-stu-id="66c13-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="66c13-123">Il codice XML viene prelevato il `CustomToken` esempio.</span><span class="sxs-lookup"><span data-stu-id="66c13-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
