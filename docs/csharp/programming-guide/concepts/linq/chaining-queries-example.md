---
title: Esempio di concatenamento di query (C#)
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: 8685db7461a1ce97c7a9c0045ed842fa4ac1a1f6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486191"
---
# <a name="chaining-queries-example-c"></a>Esempio di concatenamento di query (C#)
In questo esempio, basato sull'esempio precedente, vengono illustrati gli effetti del concatenamento di due query che usano l'esecuzione posticipata e la valutazione lazy.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene introdotto un altro metodo di estensione, `AppendString`, che aggiunge una stringa specificata a ogni stringa della raccolta di origine e quindi restituisce le nuove stringhe.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 Questo esempio produce il seguente output:  
  
```  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 In questo esempio è possibile osservare che i metodi di estensione operano uno alla volta per ogni elemento della raccolta di origine.  
  
 Scopo di questo esempio è dimostrare che, anche se le query che restituiscono le raccolte sono state concatenate, non vengono materializzate raccolte intermedie. Al contrario, ogni elemento viene passato da un metodo lazy al successivo. Il risultato è un footprint di memoria molto più piccolo rispetto a quello di un approccio che prevede di prendere una matrice di stringhe, quindi creare una seconda matrice di stringhe che sono state convertite in maiuscolo e infine creare una terza matrice di stringhe in cui alla fine di ogni stringa è stato aggiunto un punto esclamativo.  
  
 Nell'argomento successivo di questa esercitazione viene illustrata la materializzazione intermedia:  
  
- [Materializzazione intermedia (C#)](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)  
  
## <a name="see-also"></a>Vedere anche

- [Esercitazione: Concatenamento di query (C#)](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
