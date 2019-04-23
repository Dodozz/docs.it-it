---
title: 'Procedura: Decrittografare gli elementi XML con chiavi simmetriche'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.RijndaelManaged class
- XML encryption
- Rijndael
- decryption
ms.assetid: 6038aff0-f92c-4e29-a618-d793410410d8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c569407bac247e60075834e67fde9327ce6bc4a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334627"
---
# <a name="how-to-decrypt-xml-elements-with-symmetric-keys"></a>Procedura: Decrittografare gli elementi XML con chiavi simmetriche
È possibile usare le classi dello spazio dei nomi <xref:System.Security.Cryptography.Xml> per crittografare un elemento all'interno di un documento XML.  La crittografia XML consente di archiviare o trasportare contenuti XML sensibili, senza preoccuparsi che i dati vengano letti con facilità.  Questo esempio di codice consente di decrittografare un elemento XML usando l'algoritmo Advanced Encryption Standard (AES), noto anche come Rijndael.  
  
 Per informazioni su come crittografare un elemento XML mediante questa procedura, vedere [come: Crittografare gli elementi XML con chiavi simmetriche](../../../docs/standard/security/how-to-encrypt-xml-elements-with-symmetric-keys.md).  
  
 Quando si usa un algoritmo simmetrico come AES per crittografare i dati XML, è necessario usare la stessa chiave per crittografare e decrittografare i dati XML.  L'esempio riportato in questa procedura presuppone che i dati XML crittografati siano stati decrittografati mediante la stessa chiave e che le parti che eseguono le operazioni di crittografia e decrittografia si accordino sull'algoritmo e sulla chiave da usare.  L'esempio non archivia né crittografa la chiave AES nei dati XML crittografati.  
  
 Questo esempio è appropriato per situazioni in cui una singola applicazione deve crittografare i dati in base a una chiave della sessione archiviata in memoria o in base a una chiave di crittografia avanzata derivata da una password.  Per i casi in cui due o più applicazioni devono condividere dati XML crittografati, è consigliabile usare uno schema di crittografia basato su un algoritmo asimmetrico o un certificato X.509.  
  
### <a name="to-decrypt-an-xml-element-with-a-symmetric-key"></a>Per decrittografare un elemento XML con una chiave simmetrica  
  
1. Crittografare un elemento XML con la chiave precedentemente generata mediante le tecniche descritte in [come: Crittografare gli elementi XML con chiavi simmetriche](../../../docs/standard/security/how-to-encrypt-xml-elements-with-symmetric-keys.md).  
  
2. Trovare il <`EncryptedData`> elemento (definito dallo standard della crittografia XML) in un <xref:System.Xml.XmlDocument> dell'oggetto che contiene i dati XML crittografati e creare un nuovo <xref:System.Xml.XmlElement> oggetti per rappresentare l'elemento.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#10)]  
  
3. Creare un oggetto <xref:System.Security.Cryptography.Xml.EncryptedData> caricando i dati XML non elaborati dall'oggetto <xref:System.Xml.XmlElement> creato in precedenza.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#11)]  
  
4. Creare un nuovo oggetto <xref:System.Security.Cryptography.Xml.EncryptedXml> e usarlo per decrittografare i dati XML mediante la stessa chiave usata per la crittografia.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#12)]  
  
5. Sostituire l'elemento crittografato con l'elemento di testo normale appena decrittografato all'interno del documento XML.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#13)]  
  
## <a name="example"></a>Esempio  
 Questo esempio presuppone che sia presente un file denominato `"test.xml"` nella stessa directory del programma compilato  e che `"test.xml"` contenga un elemento `"creditcard"`.  È possibile inserire il codice XML seguente in un file denominato `test.xml` e usarlo con questo esempio.  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Per compilare questo esempio, è necessario includere un riferimento a `System.Security.dll`.  
  
-   Includere gli spazi dei nomi seguenti: <xref:System.Xml>, <xref:System.Security.Cryptography> e <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Non archiviare mai una chiave crittografica in testo non crittografato e non trasferire mai in testo non crittografato una chiave tra computer.  
  
 Dopo aver usato una chiave di crittografia simmetrica, cancellarla dalla memoria impostando ogni byte su zero o chiamando il metodo <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> della classe di crittografia gestita.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Cryptography.Xml>
- [Procedura: Crittografare gli elementi XML con chiavi simmetriche](../../../docs/standard/security/how-to-encrypt-xml-elements-with-symmetric-keys.md)
