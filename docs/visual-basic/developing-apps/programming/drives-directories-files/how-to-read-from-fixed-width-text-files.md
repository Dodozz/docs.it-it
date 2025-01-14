---
title: 'Procedura: Leggere da file di testo a larghezza fissa in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
ms.openlocfilehash: 1df1c84e6eaf90b737b51e5512638e4a15de6866
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623444"
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a>Procedura: Leggere da file di testo a larghezza fissa in Visual Basic
L'oggetto `TextFieldParser` consente di analizzare in modo facile ed efficace i file di testo strutturati, ad esempio i log.  
  
 La proprietà `TextFieldType` definisce se il file analizzato è un file delimitato o un file con campi di testo a larghezza fissa. In un file di testo a larghezza fissa il campo alla fine può avere una larghezza variabile. Per specificare che il campo alla fine deve avere una larghezza variabile, definirlo in modo che abbia una larghezza minore o uguale a zero.  
  
### <a name="to-parse-a-fixed-width-text-file"></a>Per analizzare un file di testo a larghezza fissa  
  
1. Creare un nuovo oggetto `TextFieldParser`. Il codice riportato di seguito crea l'oggetto `TextFieldParser` denominato `Reader` e apre il file `test.log`.  
  
     [!code-vb[VbFileIORead#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#9)]  
  
2. Definire la proprietà `TextFieldType` come `FixedWidth`, impostandone la larghezza e il formato. Il codice seguente definisce le colonne di testo: la prima ha una larghezza di 5 caratteri, la seconda di 10 e la terza di 11, mentre la quarta ha una larghezza variabile.  
  
     [!code-vb[VbFileIORead#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#10)]  
  
3. Eseguire il ciclo attraverso i campi nel file. Se sono presenti righe danneggiate, segnalare un errore e continuare l'analisi.  
  
     [!code-vb[VbFileIORead#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#11)]  
  
4. Chiudere i blocchi `While` e `Using` con `End While` ed `End Using`.  
  
     [!code-vb[VbFileIORead#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#12)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene letto il file `test.log`.  
  
 [!code-vb[VbFileIORead#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#13)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Impossibile analizzare la riga usando il formato specificato (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). Il messaggio di eccezione specifica la riga che ha generato l'eccezione, mentre alla proprietà <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> viene assegnato il testo contenuto nella riga.  
  
- File specificato inesistente (<xref:System.IO.FileNotFoundException>).  
  
- Un contesto di attendibilità parziale in cui gli utenti non dispongono di autorizzazioni sufficienti per accedere al file (<xref:System.Security.SecurityException>).  
  
- Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).  
  
- L'utente non dispone di autorizzazioni sufficienti per accedere al file (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [Procedura: Leggere da file di testo con valori delimitati da virgole](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [Procedura: Leggere da file di testo con più formati](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [Analisi dei file di testo con l'oggetto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [Procedura dettagliata: Modifica di file e directory in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [Risoluzione dei problemi: Lettura e scrittura nei file di testo](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
