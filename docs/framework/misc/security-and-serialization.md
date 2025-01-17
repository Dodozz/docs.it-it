---
title: Sicurezza e serializzazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, serialization
- serialization, security
- secure coding, serialization
- security [.NET Framework], serialization
ms.assetid: b921bc94-bd3a-4c91-9ede-2c8d4f78ea9a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c275e7179daf0dfdf2dda8bf364a4682565f28a6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596727"
---
# <a name="security-and-serialization"></a>Sicurezza e serializzazione
Poiché la serializzazione può consentire a un altro codice di visualizzare o modificare i dati dell'istanza di un oggetto che sarebbero altrimenti inaccessibili, è necessaria una speciale autorizzazione per il codice che esegue la serializzazione: <xref:System.Security.Permissions.SecurityPermission> con il flag <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> specificato. In base ai criteri predefiniti, questa autorizzazione non è concessa a codice scaricato da Internet o a codice Intranet, ma solo al codice presente sul computer locale.  
  
 In genere, tutti i campi dell'istanza di un oggetto vengono serializzati e quindi i dati vengono rappresentati nei dati serializzati per l'istanza. Per un codice in grado di interpretare il formato è possibile determinare quali siano i valori dei dati, indipendentemente dall'accessibilità del membro. Analogamente, la deserializzazione estrae i dati dalla rappresentazione serializzata e imposta direttamente lo stato dell'oggetto, sempre indipendentemente dalle regole di accessibilità.  
  
 È consigliabile rendere non serializzabili gli oggetti che possono contenere dati sensibili alla sicurezza, se possibile. Se devono essere serializzabili, è opportuno creare campi specifici per i dati sensibili non serializzabili. Se non è possibile, tenere presente che questi dati verranno esposti a qualsiasi codice autorizzato a eseguire la serializzazione e assicurarsi che nessun malware possa ottenere questa autorizzazione.  
  
 L'interfaccia <xref:System.Runtime.Serialization.ISerializable> può essere usata solo dall'infrastruttura di serializzazione, ma, se non viene protetta, potrebbe diffondere informazioni riservate. Se si fornisce la serializzazione personalizzata implementando **ISerializable**, assicurarsi di prendere le precauzioni seguenti:  
  
- Il metodo <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> deve essere protetto in modo esplicito richiedendo **SecurityPermission** con l'autorizzazione **SerializationFormatter** specificata o assicurandosi che nessuna informazione riservata venga rilasciata con l'output del metodo. Ad esempio:  
  
    ```vb  
    Public Overrides<SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)>  _  
    Sub GetObjectData(info As SerializationInfo, context As StreamingContext)  
    End Sub  
    ```  
  
    ```csharp  
    [SecurityPermissionAttribute(SecurityAction.Demand,SerializationFormatter   
    =true)]  
    public override void GetObjectData(SerializationInfo info,   
    StreamingContext context)  
    {  
    }  
    ```  
  
- Lo speciale costruttore usato per la serializzazione deve anche eseguire la convalida di input approfondita ed essere protetto o privato per salvaguardarsi dal rischio di un uso improprio da parte del malware. È consigliabile che applichi gli stessi controlli e autorizzazioni di sicurezza necessari per ottenere un'istanza di tale classe in qualsiasi altro modo, ad esempio creando la classe esplicitamente oppure indirettamente con alcuni tipi di factory.  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)
