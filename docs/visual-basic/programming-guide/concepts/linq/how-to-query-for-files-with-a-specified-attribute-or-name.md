---
title: 'Procedura: Eseguire una query per i file con un attributo specificato o un nome (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b26026a3-3f43-448f-a582-259997af6be0
ms.openlocfilehash: 5ad3ec0c18d142e8db3eddce8902b023ff00ca4d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733151"
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-visual-basic"></a><span data-ttu-id="f5a64-102">Procedura: Eseguire una query per i file con un attributo specificato o un nome (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5a64-102">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>
<span data-ttu-id="f5a64-103">In questo esempio viene illustrato come trovare tutti i file con un'estensione del nome specificata, come ad esempio "txt", in un albero di directory specificato.</span><span class="sxs-lookup"><span data-stu-id="f5a64-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="f5a64-104">Viene anche illustrato come restituire il file più recente o meno recente nell'albero in base all'ora di creazione.</span><span class="sxs-lookup"><span data-stu-id="f5a64-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5a64-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5a64-105">Example</span></span>  
  
```vb  
Module FindFileByExtension  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' This query will produce the full path for all .txt files  
        ' under the specified folder including subfolders.  
        ' It orders the list according to the file name.  
        Dim fileQuery = From file In fileList _  
                        Where file.Extension = ".txt" _  
                        Order By file.Name _  
                        Select file  
  
        For Each file In fileQuery  
            Console.WriteLine(file.FullName)  
        Next  
  
        ' Create and execute a new query by using  
        ' the previous query as a starting point.  
        ' fileQuery is not executed again until the  
        ' call to Last  
        Dim fileQuery2 = From file In fileQuery _  
                         Order By file.CreationTime _  
                         Select file.Name, file.CreationTime  
  
        ' Execute the query  
        Dim newestFile = fileQuery2.Last  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}", _  
                newestFile.Name, newestFile.CreationTime)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f5a64-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f5a64-106">Compiling the Code</span></span>  
 <span data-ttu-id="f5a64-107">Creare un progetto destinato a .NET Framework versione 3.5 o versione successiva con un riferimento alla DLL e una `Imports` istruzione dello spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="f5a64-107">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a64-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5a64-108">See also</span></span>
- [<span data-ttu-id="f5a64-109">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5a64-109">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- <span data-ttu-id="f5a64-110">[LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) (LINQ e directory file (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="f5a64-110">[LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
