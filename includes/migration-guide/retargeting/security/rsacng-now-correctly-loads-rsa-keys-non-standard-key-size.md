---
ms.openlocfilehash: 4892f75e4ae673d9d9cc7e9eeb6fb9b1a73f572e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804281"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a>RSACng ora carica correttamente le chiavi RSA di dimensioni non standard

|   |   |
|---|---|
|Dettagli|Nelle versioni di .NET Framework precedenti alla 4.6.2, i clienti con chiavi di dimensioni non standard per i certificati RSA non possono accedere a queste chiavi tramite i metodi di estensione <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name> e <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=name>.  Viene generata un'eccezione <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> con il messaggio &quot;La dimensione della chiave specificata non è supportata&quot;. Il problema è stato risolto in .NET Framework 4.6.2. In modo analogo, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> e <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> ora funzionano con dimensioni della chiave non standard senza generare eccezioni <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>.|
|Suggerimento|In presenza di logica di gestione delle eccezioni basata sul comportamento precedente in cui viene generata una <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> quando vengono usate dimensioni della chiave non standard, valutare la possibilità di rimuoverla.|
|Ambito|Microsoft Edge|
|Versione|4.6.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType></li></ul>|
