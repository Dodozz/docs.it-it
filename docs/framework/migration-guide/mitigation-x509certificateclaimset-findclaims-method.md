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
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>Mitigazione: metodo X509CertificateClaimSet.FindClaims
A partire dalle app destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> tenterà di far corrispondere l'argomento `claimType` con tutte le voci DNS nel relativo campo SAN.  
  
## <a name="impact"></a>Impatto  
 Questa modifica interessa solo le app destinate a versioni di .NET Framework che iniziano con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 Per le app destinate a versioni precedenti di .NET Framework, il metodo <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> cerca di far corrispondere l'argomento `claimType` solo con l'ultima voce DNS.  
  
## <a name="mitigation"></a>Mitigazione  
 Se la modifica è indesiderata, le app destinate a versioni di .NET Framework che iniziano con [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] possono rifiutarla esplicitamente aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
```  
  
 Le app destinate a versioni precedenti di .NET Framework ma in esecuzione su [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versione successiva possono optare per questo comportamento aggiungendo l'impostazione di configurazione seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>Vedere anche
- [Modifiche di reindirizzamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
