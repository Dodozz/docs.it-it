---
title: 'Procedura: Aggiungere testo a file di testo in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], appending to files
- I/O [Visual Basic], My.Computer.FileSystem.WriteAllText method
- I/O [Visual Basic], WriteAllText method
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
ms.openlocfilehash: 5fabd0b6894fc5ab7d4bab1979d71b171d2b21c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498216"
---
# <a name="how-to-append-to-text-files-in-visual-basic"></a>Procedura: Aggiungere testo a file di testo in Visual Basic
Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> può essere usato per aggiungere testo a un file di testo specificando che il parametro `append` è impostato su `True`.  
  
### <a name="to-append-to-a-text-file"></a>Per aggiungere testo a file di testo  
  
-   Usare il metodo `WriteAllText` specificando il file di destinazione e la stringa da aggiungere e impostando il parametro `append` su `True`.  
  
     Nell'esempio riportato di seguito la stringa `"This is a test string."` viene scritta nel file denominato `Testfile.txt`.  
  
     [!code-vb[VbFileIOWrite#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-append-to-text-files_1.vb)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `File` punta a un percorso che non esiste (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).  
  
-   Il file è in uso in un altro processo oppure si verifica un errore di I/O (<xref:System.IO.IOException>).  
  
-   La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).  
  
-   Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).  
  
-   L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [Scrittura su file](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
