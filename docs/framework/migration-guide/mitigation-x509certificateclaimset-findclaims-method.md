---
title: 'Mitigazione: metodo X509CertificateClaimSet.FindClaims'
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccc24cd494866c087860144f1720988ccfc2dfa8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536438"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="e75be-102">Mitigazione: metodo X509CertificateClaimSet.FindClaims</span><span class="sxs-lookup"><span data-stu-id="e75be-102">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>
<span data-ttu-id="e75be-103">A partire dalle app destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> tenterà di far corrispondere l'argomento `claimType` con tutte le voci DNS nel relativo campo SAN.</span><span class="sxs-lookup"><span data-stu-id="e75be-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)],  the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e75be-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="e75be-104">Impact</span></span>  
 <span data-ttu-id="e75be-105">Questa modifica interessa solo le app destinate a versioni di .NET Framework che iniziano con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e75be-105">This change only affects apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>  
  
 <span data-ttu-id="e75be-106">Per le app destinate a versioni precedenti di .NET Framework, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> cerca di far corrispondere l'argomento `claimType` solo con l'ultima voce DNS.</span><span class="sxs-lookup"><span data-stu-id="e75be-106">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="e75be-107">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="e75be-107">Mitigation</span></span>  
 <span data-ttu-id="e75be-108">Se la modifica è indesiderata, le app destinate a versioni di .NET Framework che iniziano con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] possono rifiutarla esplicitamente aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="e75be-108">If this change is undesirable, apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 <span data-ttu-id="e75be-109">Le app destinate a versioni precedenti di .NET Framework ma in esecuzione su [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versione successiva possono optare per questo comportamento aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="e75be-109">In addition, apps that target previous versions of the .NET Framework but are running under the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e75be-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e75be-110">See also</span></span>
- [<span data-ttu-id="e75be-111">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="e75be-111">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
