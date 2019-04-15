---
title: 'Procedura: Creare un join del contenuto da file non analoghi (LINQ) (C#)'
ms.date: 06/27/2018
ms.assetid: aa2d12a6-70a9-492f-a6db-b2b850d46811
ms.openlocfilehash: ca340e82e33d9b3ec212f69cb73efafb3c6abc0c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328816"
---
# <a name="how-to-join-content-from-dissimilar-files-linq-c"></a><span data-ttu-id="383ae-102">Procedura: Creare un join del contenuto da file non analoghi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="383ae-102">How to: Join Content from Dissimilar Files (LINQ) (C#)</span></span>

<span data-ttu-id="383ae-103">In questo esempio viene illustrato come eseguire un join di dati da due file con valori delimitati da virgole che condividono un valore comune usato come una chiave corrispondente.</span><span class="sxs-lookup"><span data-stu-id="383ae-103">This example shows how to join data from two comma-delimited files that share a common value that is used as a matching key.</span></span> <span data-ttu-id="383ae-104">Questa tecnica può essere utile se è necessario combinare dati provenienti da due fogli di calcolo, o da un foglio di calcolo e da un file con un altro formato, in un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="383ae-104">This technique can be useful if you have to combine data from two spreadsheets, or from a spreadsheet and from a file that has another format, into a new file.</span></span> <span data-ttu-id="383ae-105">È possibile modificare l'esempio in modo che funzioni con qualsiasi tipo di testo strutturato.</span><span class="sxs-lookup"><span data-stu-id="383ae-105">You can modify the example to work with any kind of structured text.</span></span>  
  
## <a name="to-create-the-data-files"></a><span data-ttu-id="383ae-106">Per creare i file di dati</span><span class="sxs-lookup"><span data-stu-id="383ae-106">To create the data files</span></span>
  
1. <span data-ttu-id="383ae-107">Copiare le righe seguenti in un file denominato *scores.csv* e salvarlo nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="383ae-107">Copy the following lines into a file that is named *scores.csv* and save it to your project folder.</span></span> <span data-ttu-id="383ae-108">Il file rappresenta i dati del foglio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="383ae-108">The file represents spreadsheet data.</span></span> <span data-ttu-id="383ae-109">La colonna 1 è l'ID studente e le colonne da 2 a 5 sono i punteggi dei test.</span><span class="sxs-lookup"><span data-stu-id="383ae-109">Column 1 is the student's ID, and columns 2 through 5 are test scores.</span></span>  
  
    ```  
    111, 97, 92, 81, 60  
    112, 75, 84, 91, 39  
    113, 88, 94, 65, 91  
    114, 97, 89, 85, 82  
    115, 35, 72, 91, 70  
    116, 99, 86, 90, 94  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    119, 68, 79, 88, 92  
    120, 99, 82, 81, 79  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    ```  
  
2. <span data-ttu-id="383ae-110">Copiare le righe seguenti in un file denominato *names.csv* e salvarlo nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="383ae-110">Copy the following lines into a file that is named *names.csv* and save it to your project folder.</span></span> <span data-ttu-id="383ae-111">Il file rappresenta un foglio di calcolo che contiene il cognome, il nome e l'ID degli studenti.</span><span class="sxs-lookup"><span data-stu-id="383ae-111">The file represents a spreadsheet that contains the student's last name, first name, and student ID.</span></span>  
  
    ```  
    Omelchenko,Svetlana,111  
    O'Donnell,Claire,112  
    Mortensen,Sven,113  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Hugo,118  
    Tucker,Lance,119  
    Adams,Terry,120  
    Zabokritski,Eugene,121  
    Tucker,Michael,122  
    ```  
  
## <a name="example"></a><span data-ttu-id="383ae-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="383ae-112">Example</span></span>  

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class JoinStrings  
{  
    static void Main()  
    {  
        // Join content from dissimilar files that contain  
        // related information. File names.csv contains the student  
        // name plus an ID number. File scores.csv contains the ID   
        // and a set of four test scores. The following query joins  
        // the scores to the student names by using ID as a  
        // matching key.  
  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Name:    Last[0],       First[1],  ID[2]  
        //          Omelchenko,    Svetlana,  11  
        // Score:   StudentID[0],  Exam1[1]   Exam2[2],  Exam3[3],  Exam4[4]  
        //          111,           97,        92,        81,        60  
  
        // This query joins two dissimilar spreadsheets based on common ID value.  
        // Multiple from clauses are used instead of a join clause  
        // in order to store results of id.Split.  
        IEnumerable<string> scoreQuery1 =  
            from name in names  
            let nameFields = name.Split(',')  
            from id in scores  
            let scoreFields = id.Split(',')  
            where Convert.ToInt32(nameFields[2]) == Convert.ToInt32(scoreFields[0])
            select nameFields[0] + "," + scoreFields[1] + "," + scoreFields[2]   
                   + "," + scoreFields[3] + "," + scoreFields[4];  
  
        // Pass a query variable to a method and execute it  
        // in the method. The query itself is unchanged.  
        OutputQueryResults(scoreQuery1, "Merge two spreadsheets:");  
  
        // Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    static void OutputQueryResults(IEnumerable<string> query, string message)  
    {  
        Console.WriteLine(System.Environment.NewLine + message);  
        foreach (string item in query)  
        {  
            Console.WriteLine(item);  
        }  
        Console.WriteLine("{0} total names in list", query.Count());  
    }  
}  
/* Output:  
Merge two spreadsheets:
Omelchenko, 97, 92, 81, 60
O'Donnell, 75, 84, 91, 39
Mortensen, 88, 94, 65, 91
Garcia, 97, 89, 85, 82
Garcia, 35, 72, 91, 70
Fakhouri, 99, 86, 90, 94
Feng, 93, 92, 80, 87
Garcia, 92, 90, 83, 78
Tucker, 68, 79, 88, 92
Adams, 99, 82, 81, 79
Zabokritski, 96, 85, 91, 60
Tucker, 94, 92, 91, 91
12 total names in list
 */  
```

## <a name="compiling-the-code"></a><span data-ttu-id="383ae-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="383ae-113">Compiling the code</span></span>

<span data-ttu-id="383ae-114">Creare e compilare un progetto destinato a una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="383ae-114">Create and compile a project that targets one of the following options:</span></span>

- <span data-ttu-id="383ae-115">.NET Framework versione 3.5 con un riferimento a System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="383ae-115">.NET Framework version 3.5 with a reference to System.Core.dll.</span></span>
- <span data-ttu-id="383ae-116">.NET Framework versione 4.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="383ae-116">.NET Framework version 4.0 or higher.</span></span>
- <span data-ttu-id="383ae-117">.NET Core versione 1.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="383ae-117">.NET Core version 1.0 or higher.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="383ae-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="383ae-118">See also</span></span>

- [<span data-ttu-id="383ae-119">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="383ae-119">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="383ae-120">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="383ae-120">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
