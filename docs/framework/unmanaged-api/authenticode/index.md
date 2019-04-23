---
title: Authenticode (riferimenti alle API non gestite)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408219307015d5c39cb581b3884ed9810f4c0566
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216353"
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (riferimenti alle API non gestite)
Supporta il modulo di creazione e verifica delle licenze Authenticode XrML.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Funzione _AxlGetIssuerPublicKeyHash](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 Recupera l'hash SHA-1 della chiave pubblica associata alla chiave privata usata per firmare il certificato specificato.  
  
 [Funzione _AxlPublicKeyBlobToPublicKeyToken](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 Calcola il token di chiave pubblica con nome sicuro da un formato CSP PUBLICKEYBLOB.  
  
 [Funzione _AxlRSAKeyValueToPublicKeyToken](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 Converte un elemento Modulus e un elemento Exponent in un token di chiave pubblica con nome sicuro.  
  
 [Funzione CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 Libera le risorse allocate per la struttura AXL_AUTHENTICODE_SIGNER_INFO.  
  
 [Funzione CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 Libera le risorse allocate per la struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO.  
  
 [Funzione CertTimestampAuthenticodeLicense](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 Aggiunge un timestamp a una licenza Authenticode XrML creata da CertCreateAuthenticodeLicense.  
  
 [Funzione CertVerifyAuthenticodeLicense](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 Verifica la validità di una licenza Authenticode XrML.  
  
 [Struttura AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 Definisce le informazioni su chi ha apposto la firma Authenticode.  
  
 [Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 Definisce le informazioni su chi ha apposto il timestamp Authenticode.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite](../../../../docs/framework/unmanaged-api/index.md)
