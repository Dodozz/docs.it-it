---
title: 'Procedura: Eseguire una query per trovare caratteri in una stringa (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 0c577fc2dc2ae07574580f819a6fb51336107dfb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665630"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a>Procedura: Eseguire una query per trovare caratteri in una stringa (LINQ) (C#)
Poiché la classe <xref:System.String> implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>, è possibile eseguire una query su qualsiasi stringa come una sequenza di caratteri. Tuttavia, questo uso di LINQ non è comune. Per le operazioni con criteri di ricerca complessi, usare la classe <xref:System.Text.RegularExpressions.Regex>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita una query su una stringa per determinare il numero di cifre che contiene. Si noti che, dopo la prima esecuzione, la query viene "riutilizzata". Ciò è possibile perché la query stessa non archivia i risultati effettivi.  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Creare un progetto che usi .NET Framework versione 3.5 o successiva con un riferimento a System.Core.dll e alle direttive `using` per gli spazi dei nomi System.Linq e System.IO.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ e stringhe (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
- [Procedura: Combinare query LINQ con espressioni regolari (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
