---
title: 'Procedura: Scrivere testo in file in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- writing to files [Visual Basic]
- examples [Visual Basic], text files
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
ms.openlocfilehash: 0ff220bd8a790d9f5480581b847527fb5fbae449
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634389"
---
# <a name="how-to-write-text-to-files-in-visual-basic"></a>Procedura: Scrivere testo in file in Visual Basic
Il metodo <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> può essere usato per scrivere testo nei file. Se il file specificato non esiste, viene creato.  
  
## <a name="procedure"></a>Routine  
  
#### <a name="to-write-text-to-a-file"></a>Per scrivere testo in un file  
  
-   Usare il metodo `WriteAllText` per scrivere testo in un file, specificando il file e il testo da scrivere. In questo esempio la riga `"This is new text."` viene scritta nel file denominato `test.txt`, aggiungendo il nuovo testo al testo eventualmente già esistente nel file.  
  
     [!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]  
  
#### <a name="to-write-a-series-of-strings-to-a-file"></a>Per scrivere una serie di stringhe in un file  
  
-   Scorrere la raccolta di stringhe. Usare il metodo `WriteAllText` per scrivere testo in un file, specificando il file di destinazione e la stringa da aggiungere e impostando `append` su `True`.  
  
     In questo esempio vengono scritti i nomi dei file nella directory `Documents and Settings` in `FileList.txt`, inserendo un ritorno a capo tra ogni nome per una migliore leggibilità.  
  
     [!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il percorso non è valido per uno dei motivi seguenti: è una stringa di lunghezza zero, contiene solo spazi vuoti, contiene caratteri non validi o è il percorso di un dispositivo (inizia con \\\\.\\) (<xref:System.ArgumentException>).  
  
-   Il percorso non è valido in quanto è `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `File` punta a un percorso che non esiste (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).  
  
-   Il file è in uso in un altro processo oppure si verifica un errore di I/O (<xref:System.IO.IOException>).  
  
-   La lunghezza del percorso supera la lunghezza massima definita dal sistema (<xref:System.IO.PathTooLongException>).  
  
-   Il nome di un file o di una directory nel percorso contiene i due punti (:) o ha un formato non valido (<xref:System.NotSupportedException>).  
  
-   L'utente non dispone delle autorizzazioni necessarie per visualizzare il percorso (<xref:System.Security.SecurityException>).  
  
-   Il disco è pieno e la chiamata a `WriteAllText` ha esito negativo (<xref:System.IO.IOException>).  
  
 Se eseguito in un contesto ad attendibilità parziale, il codice potrebbe generare un'eccezione a causa dell'insufficienza di privilegi. Per altre informazioni, vedere [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Nozioni di base sulla sicurezza dell'accesso di codice).  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- [Procedura: Leggere da file di testo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)
