---
title: Denominazione sicura avanzata
ms.date: 03/30/2017
helpviewer_keywords:
- strong-named assemblies
- strong naming [.NET Framework], enhanced
ms.assetid: 6cf17a82-62a1-4f6d-8d5a-d7d06dec2bb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 882b1de4b1fd3b013b6b2825aec5e607a387531b
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377998"
---
# <a name="enhanced-strong-naming"></a>Denominazione sicura avanzata
Una firma con nome sicuro è un meccanismo di identità in .NET Framework per l'identificazione degli assembly. È una firma digitale a chiave pubblica che in genere si usa per verificare l'integrità dei dati passati da un autore (firmatario) a un destinatario (verificatore). Questa firma viene usata come identità univoca per un assembly e garantisce che i riferimenti all'assembly non siano ambigui. L'assembly è firmato come parte del processo di compilazione e quindi verificato quando viene caricato.  
  
 Le firme con nome sicuro consentono di evitare che utenti malintenzionati possano manomettere un assembly e firmarlo nuovamente con la chiave del firmatario originale. Tuttavia, le chiavi con nome sicuro non contengono informazioni affidabili sul server di pubblicazione e non contengono una gerarchia di certificati. Una firma con nome sicuro non garantisce l'affidabilità della persona che ha firmato l'assembly né indica se la persona è un legittimo proprietario della chiave, indica solo che il proprietario della chiave ha firmato l'assembly. Di conseguenza, non è consigliabile usare una firma con nome sicuro come validator di sicurezza per concedere l'attendibilità a codice di terze parti. Microsoft Authenticode è lo strumento consigliato per l'autenticazione di codice.  
  
## <a name="limitations-of-conventional-strong-names"></a>Limitazioni dei nomi sicuri convenzionali  
 La tecnologia di denominazione sicura usata nelle versioni precedenti a .NET Framework 4.5 presenta queste limitazioni:  
  
- Le chiavi sono costantemente sotto attacco e grazie all'uso di tecniche e hardware più evoluti è più semplice dedurre una chiave privata da una chiave pubblica. Per proteggersi dagli attacchi, sono necessarie chiavi di dimensioni maggiori. Le versioni di .NET Framework precedenti a .NET Framework 4.5 offrono la possibilità di accedere con chiavi di qualsiasi dimensione (quella predefinita è 1024 bit), ma firmare un assembly con una nuova chiave interrompe tutti i file binari che fanno riferimento all'identità precedente dell'assembly. È quindi estremamente difficile aggiornare la dimensione di una chiave di firma se si vuole mantenere la compatibilità.  
  
- La firma con nome sicuro supporta solo l'algoritmo SHA-1. Si è scoperto di recente che SHA-1 non è adeguato per le applicazioni che usano l'algoritmo SHA. È quindi necessario un algoritmo più robusto, ad esempio SHA-256 o superiore. È possibile che in futuro SHA-1 non sia più conforme agli standard FIPS e questo può causare problemi agli utenti che scelgono di usare solo software e algoritmi conformi agli standard FIPS.  
  
## <a name="advantages-of-enhanced-strong-names"></a>Vantaggi dei nomi sicuri avanzati  
 I vantaggi principali offerti dai nomi sicuri avanzati sono la compatibilità con nomi sicuri preesistenti e la possibilità di richiedere che un'identità sia equivalente a un'altra:  
  
- Gli sviluppatori che usano assembly firmati preesistenti possono eseguire la migrazione delle proprie identità agli algoritmi SHA-2 conservando la compatibilità con gli assembly che fanno riferimento alle identità precedenti.  
  
- Gli sviluppatori che creano nuovi assembly e non ritengono rilevanti le firme con nome sicuro preesistenti possono usare gli algoritmi SHA-2, più sicuri, e firmare gli assembly come in precedenza.  
  
## <a name="using-enhanced-strong-names"></a>Uso dei nomi sicuri avanzati  
 Le chiavi con nome sicuro sono costituite da una chiave di firma e una chiave di identità. L'assembly è firmato con la chiave di firma e identificato dalla chiave di identità. Nelle versioni precedenti a .NET Framework 4.5 queste due chiavi erano identiche. A partire da .NET Framework 4.5, la chiave di identità rimane la stessa delle versioni precedenti di .NET Framework, ma la chiave di firma è stata migliorata con un algoritmo hash più avanzato. Inoltre, la chiave di firma viene firmata con la chiave di identità per creare una controfirma.  
  
 L'attributo <xref:System.Reflection.AssemblySignatureKeyAttribute> consente ai metadati dell'assembly di usare la chiave pubblica preesistente per l'identità dell'assembly e quindi i vecchi riferimenti all'assembly continuano a funzionare.  L'attributo <xref:System.Reflection.AssemblySignatureKeyAttribute> usa la controfirma per verificare che il proprietario della nuova chiave di firma sia anche il proprietario della chiave di identità precedente.  
  
### <a name="signing-with-sha-2-without-key-migration"></a>Firma con SHA-2, senza migrazione delle chiavi  
 Eseguire i comandi seguenti da una finestra del prompt dei comandi per firmare un assembly senza eseguire la migrazione di una firma con nome sicuro:  
  
1. Generare la nuova chiave di identità, se necessario.  
  
    ```  
    sn -k IdentityKey.snk  
    ```  
  
2. Estrarre la chiave pubblica di identità e specificare che deve essere usato un algoritmo SHA-2 per la firma con questa chiave.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk sha256  
    ```  
  
3. Ritardare la firma dell'assembly con il file della chiave pubblica di identità.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
4. Firmare di nuovo l'assembly con la coppia di chiavi di identità completa.  
  
    ```  
    sn -Ra MyAssembly.exe IdentityKey.snk  
    ```  
  
### <a name="signing-with-sha-2-with-key-migration"></a>Firma con SHA-2, con migrazione delle chiavi  
 Eseguire i comandi seguenti da una finestra del prompt dei comandi per firmare un assembly con una firma con nome sicuro migrata.  
  
1. Generare una coppia di chiavi di identità e firma, se necessario.  
  
    ```  
    sn -k IdentityKey.snk  
    sn -k SignatureKey.snk  
    ```  
  
2. Estrarre la chiave pubblica di firma e specificare che deve essere usato un algoritmo SHA-2 per la firma con questa chiave.  
  
    ```  
    sn -p SignatureKey.snk SignaturePubKey.snk sha256  
    ```  
  
3. Estrarre la chiave pubblica di identità, che determina l'algoritmo hash che genera una controfirma.  
  
    ```  
    sn -p IdentityKey.snk IdentityPubKey.snk  
    ```  
  
4. Generare i parametri per un attributo <xref:System.Reflection.AssemblySignatureKeyAttribute> e allegare l'attributo all'assembly.  
  
    ```  
    sn -a IdentityPubKey.snk IdentityKey.snk SignaturePubKey.snk  
    ```  

    Si genera un output simile al seguente.

    ```
    Information for key migration attribute.
    (System.Reflection.AssemblySignatureKeyAttribute):
    publicKey=
    002400000c80000094000000060200000024000052534131000400000100010005a3a81ac0a519
    d96244a9c589fc147c7d403e40ccf184fc290bdd06c7339389a76b738e255a2bce1d56c3e7e936
    e4fc87d45adc82ca94c716b50a65d39d373eea033919a613e4341c66863cb2dc622bcb541762b4
    3893434d219d1c43f07e9c83fada2aed400b9f6e44ff05e3ecde6c2827830b8f43f7ac8e3270a3
    4d153cdd

    counterSignature=
    e3cf7c211678c4d1a7b8fb20276c894ab74c29f0b5a34de4d61e63d4a997222f78cdcbfe4c91eb
    e1ddf9f3505a32edcb2a76f34df0450c4f61e376b70fa3cdeb7374b1b8e2078b121e2ee6e8c6a8
    ed661cc35621b4af53ac29c9e41738f199a81240e8fd478c887d1a30729d34e954a97cddce66e3
    ae5fec2c682e57b7442738
    ```

    Questo output può poi essere convertito in AssemblySignatureKeyAttribute.

    ```
    [assembly:System.Reflection.AssemblySignatureKeyAttribute(
    "002400000c80000094000000060200000024000052534131000400000100010005a3a81ac0a519d96244a9c589fc147c7d403e40ccf184fc290bdd06c7339389a76b738e255a2bce1d56c3e7e936e4fc87d45adc82ca94c716b50a65d39d373eea033919a613e4341c66863cb2dc622bcb541762b43893434d219d1c43f07e9c83fada2aed400b9f6e44ff05e3ecde6c2827830b8f43f7ac8e3270a34d153cdd",
    "e3cf7c211678c4d1a7b8fb20276c894ab74c29f0b5a34de4d61e63d4a997222f78cdcbfe4c91ebe1ddf9f3505a32edcb2a76f34df0450c4f61e376b70fa3cdeb7374b1b8e2078b121e2ee6e8c6a8ed661cc35621b4af53ac29c9e41738f199a81240e8fd478c887d1a30729d34e954a97cddce66e3ae5fec2c682e57b7442738"
    )]
    ```
  
5. Ritardare la firma dell'assembly con la chiave pubblica di identità.  
  
    ```  
    csc MyAssembly.cs /keyfile:IdentityPubKey.snk /delaySign+  
    ```  
  
6. Firmare completamente l'assembly con la coppia di chiavi di firma.  
  
    ```  
    sn -Ra MyAssembly.exe SignatureKey.snk  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Creazione e utilizzo degli assembly con nome sicuro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
