---
title: Trasformazioni dati con LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: d7073fe35d58c9c538afa52911a5555b0002bfcf
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486266"
---
# <a name="data-transformations-with-linq-c"></a>Trasformazioni dati con LINQ (C#)
[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] non riguarda solo il recupero dei dati. È anche un potente strumento per la trasformazione dei dati. Con una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] è possibile usare una sequenza di origine come input e modificarla in molti modi per creare una nuova sequenza di output. È possibile modificare la sequenza senza modificare gli elementi con operazioni di ordinamento e raggruppamento. Ma probabilmente la funzionalità più potente delle query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] è la possibilità di creare nuovi tipi. Questa operazione viene eseguita nella clausola [select](../../../../csharp/language-reference/keywords/select-clause.md). Ad esempio, è possibile effettuare le attività seguenti:  
  
- Unire più sequenze di input in un'unica sequenza di output con un nuovo tipo.  
  
- Creare sequenze di output i cui elementi sono costituiti da una o più proprietà di ogni elemento nella sequenza di origine.  
  
- Creare sequenze di output i cui elementi sono costituiti dai risultati delle operazioni eseguite sui dati di origine.  
  
- Creare sequenze di output in un formato diverso. Ad esempio, è possibile trasformare i dati da righe SQL o file di testo in XML.  
  
 Questi sono solo alcuni esempi. Naturalmente, queste trasformazioni possono essere combinate in modi diversi nella stessa query. Inoltre, la sequenza di output di una query può essere usata come sequenza di input per una nuova query.  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a>Unione di più input in un'unica sequenza di output  
 È possibile usare una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] per creare una sequenza di output che contiene gli elementi di più di una sequenza di input. Nell'esempio seguente viene illustrato come combinare due strutture di dati in memoria, ma è possibile applicare gli stessi principi per combinare dati da origini XML, SQL o DataSet. Si supponga di avere questi tipi di classi:  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 Nell'esempio riportato di seguito è visualizzata la query:  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 Per altre informazioni, vedere [Clausola join](../../../../csharp/language-reference/keywords/join-clause.md) e [Clausola select](../../../../csharp/language-reference/keywords/select-clause.md).  
  
## <a name="selecting-a-subset-of-each-source-element"></a>Selezione di un sottoinsieme di ogni elemento di origine  
 Esistono due modi principali per selezionare un sottoinsieme di ogni elemento nella sequenza di origine:  
  
1. Per selezionare solo un membro dell'elemento di origine, usare l'operazione con punto. Nell'esempio seguente si supponga che un oggetto `Customer` contenga diverse proprietà pubbliche tra cui una stringa denominata `City`. Quando viene eseguita, questa query produce una sequenza di output di stringhe.  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. Per creare gli elementi che contengono più di una proprietà dall'elemento di origine, è possibile usare un inizializzatore di oggetto con un oggetto denominato o un tipo anonimo. Nell'esempio seguente viene illustrato l'uso di un tipo anonimo per incapsulare due proprietà da ogni elemento `Customer`:  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Per altre informazioni, vedere [Inizializzatori di oggetto e di insieme](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) e [Tipi anonimi](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## <a name="transforming-in-memory-objects-into-xml"></a>Trasformazione di oggetti in memoria in XML  
 Le query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] semplificano la trasformazione dei dati tra strutture di dati in memoria, database SQL, set di dati ADO.NET e flussi o documenti XML. Nell'esempio seguente gli oggetti di una struttura di dati in memoria vengono trasformati in elementi XML.  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 Il codice genera il seguente output XML:  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 Per altre informazioni, vedere [Creazione di alberi XML in C# (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md).  
  
## <a name="performing-operations-on-source-elements"></a>Esecuzione di operazioni su elementi di origine  
 Una sequenza di output potrebbe non contenere elementi o proprietà degli elementi della sequenza di origine. L'output potrebbe invece essere una sequenza di valori che viene calcolata usando gli elementi di origine come argomenti di input. La seguente query semplice, quando viene eseguita, restituisce una sequenza di stringhe i cui valori rappresentano un calcolo basato sulla sequenza di origine di elementi di tipo `double`.  
  
> [!NOTE]
>  La chiamata ai metodi nelle espressioni di query non è supportata se la query verrà traslata in un altro dominio. Ad esempio, non è possibile chiamare un normale metodo C# in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] perché SQL Server non offre alcun contesto. Tuttavia, è possibile eseguire il mapping delle stored procedure ai metodi e chiamarli. Per altre informazioni, vedere [Stored procedure](../../../../framework/data/adonet/sql/linq/stored-procedures.md).  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a>Vedere anche

- [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)
- [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md)
- [Espressioni di query LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)
- [Clausola select](../../../../csharp/language-reference/keywords/select-clause.md)
