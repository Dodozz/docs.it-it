---
title: Conversione di tipi di dati (C#)
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: 918a9fbfc523e62c7b4a5d915c28c00ea781d3e4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64597715"
---
# <a name="converting-data-types-c"></a>Conversione di tipi di dati (C#)
I metodi di conversione modificano il tipo degli oggetti di input.  
  
 Le operazioni di conversione nelle query LINQ sono utili in un'ampia gamma di applicazioni. Ecco alcuni esempi:  
  
- Il metodo <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> può essere usato per nascondere l'implementazione personalizzata di un tipo di un operatore query standard.  
  
- Il metodo <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> può essere usato per abilitare le raccolte senza parametri per l'esecuzione di query LINQ.  
  
- I metodi <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> e <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> possono essere usati per forzare l'esecuzione di una query immediata invece che rinviarla fino a quando la query non viene enumerata.  
  
## <a name="methods"></a>Metodi  
 Nella tabella seguente sono elencati i metodi di operatore query standard che eseguono conversioni di tipi di dati.  
  
 I metodi di conversione nella tabella i cui nomi iniziano con "As" modificano il tipo statico della raccolta di origine ma non lo enumerano. I metodi i cui nomi iniziano con "To" enumerano la raccolta di origine e inseriscono gli elementi nel tipo di raccolta corrispondente.  
  
|Nome metodo|Description|Sintassi di espressione della query C#|Altre informazioni|  
|-----------------|-----------------|---------------------------------|----------------------|  
|AsEnumerable|Restituisce l'input tipizzato come oggetto <xref:System.Collections.Generic.IEnumerable%601>.|Non applicabile.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|AsQueryable|Converte un oggetto <xref:System.Collections.IEnumerable> (generico) in un oggetto <xref:System.Linq.IQueryable> (generico).|Non applicabile.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|Cast|Esegue il cast degli elementi di una raccolta a un tipo specificato.|Usare una variabile di intervallo tipizzata in modo esplicito. Ad esempio:<br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|OfType|Filtra i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.|Non applicabile.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|ToArray|Converte una raccolta in una matrice. Questo metodo forza l'esecuzione di query.|Non applicabile.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|ToDictionary|Inserisce gli elementi in un oggetto <xref:System.Collections.Generic.Dictionary%602> sulla base di una funzione del selettore di chiavi. Questo metodo forza l'esecuzione di query.|Non applicabile.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|ToList|Converte una raccolta in un oggetto <xref:System.Collections.Generic.List%601>. Questo metodo forza l'esecuzione di query.|Non applicabile.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|ToLookup|Inserisce gli elementi in un oggetto <xref:System.Linq.Lookup%602>, un dizionario uno-a-molti, sulla base di una funzione del selettore di chiavi. Questo metodo forza l'esecuzione di query.|Non applicabile.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a>Esempio di sintassi delle espressioni di query  
 L'esempio di codice seguente usa una variabile di intervallo tipizzata in modo esplicito per eseguire il cast di un tipo a un sottotipo prima di accedere a un membro che è disponibile solo nel sottotipo.  
  
```csharp  
class Plant  
{  
    public string Name { get; set; }  
}  
  
class CarnivorousPlant : Plant  
{  
    public string TrapType { get; set; }  
}  
  
static void Cast()  
{  
    Plant[] plants = new Plant[] {  
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },  
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },  
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },  
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }  
    };  
  
    var query = from CarnivorousPlant cPlant in plants  
                where cPlant.TrapType == "Snap Trap"  
                select cPlant;  
  
    foreach (Plant plant in query)  
        Console.WriteLine(plant.Name);  
  
    /* This code produces the following output:  
  
        Venus Fly Trap  
        Waterwheel Plant  
    */  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori di query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Clausola from](../../../../csharp/language-reference/keywords/from-clause.md)
- [Espressioni di query LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)
- [Procedura: Eseguire una query su un ArrayList con LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
