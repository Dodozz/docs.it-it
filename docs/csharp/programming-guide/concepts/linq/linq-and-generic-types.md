---
title: LINQ e tipi generici (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
ms.openlocfilehash: 891acd56939a2cff8eb377512a8a516f8a189034
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487436"
---
# <a name="linq-and-generic-types-c"></a>LINQ e tipi generici (C#)
Le query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] si basano sui tipi generici introdotti nella versione 2.0 di .NET Framework. Non è necessaria una conoscenza approfondita dei generics per poter iniziare a scrivere le query. È tuttavia importante comprendere due concetti di base:  
  
1. Quando si crea un'istanza di una classe di raccolte generiche, ad esempio <xref:System.Collections.Generic.List%601>, sostituire "T" con il tipo di oggetti che saranno contenuti nell'elenco. Ad esempio, un elenco di stringhe viene espresso come `List<string>` e un elenco di oggetti `Customer` viene espresso come `List<Customer>`. Un elenco generico è fortemente tipizzato e offre molti vantaggi rispetto alle raccolte che archiviano gli elementi come <xref:System.Object>. Se si tenta di aggiungere un oggetto `Customer` a un oggetto `List<string>`, verrà generato un errore in fase di compilazione. È semplice usare le raccolte generiche poiché non è necessario eseguire il cast dei tipi in fase di esecuzione.  
  
2. <xref:System.Collections.Generic.IEnumerable%601> è l'interfaccia che consente alle classi di raccolte generiche di essere enumerate usando l'istruzione `foreach`. Le classi di raccolte generiche supportano <xref:System.Collections.Generic.IEnumerable%601> nello stesso modo in cui le classi di raccolte non generiche, come <xref:System.Collections.ArrayList>, supportano <xref:System.Collections.IEnumerable>.  
  
 Per altre informazioni sui generics, vedere [Generics](../../../../csharp/programming-guide/generics/index.md).  
  
## <a name="ienumerablet-variables-in-linq-queries"></a>Variabili IEnumerable<T\> nelle query LINQ  
 Le variabili di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sono tipizzate come <xref:System.Collections.Generic.IEnumerable%601> o come un tipo derivato, ad esempio <xref:System.Linq.IQueryable%601>. Nel caso di una variabile di query tipizzata come `IEnumerable<Customer>`, significa semplicemente che la query, quando eseguita, genererà una sequenza di zero o più oggetti `Customer`.  
  
 [!code-csharp[csLINQGettingStarted#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#34)]  
  
 Per altre informazioni, vedere [Relazioni tra i tipi nelle operazioni di query LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a>Gestione delle dichiarazioni di tipo generico tramite il compilatore  
 Se si preferisce, è possibile evitare la sintassi generica usando la parola chiave [var](../../../../csharp/language-reference/keywords/var.md). La parola chiave `var` chiede al compilatore di dedurre il tipo di una variabile di query esaminando l'origine dati specificata nella clausola `from`. Nell'esempio seguente viene generato lo stesso codice compilato dell'esempio precedente:  
  
 [!code-csharp[csLINQGettingStarted#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#35)]  
  
 La parola chiave `var` è utile quando il tipo della variabile è ovvio o quando non è importante specificare in modo esplicito i tipi generici annidati, ad esempio quelli generati dalle query di gruppo. In generale, è consigliabile usare `var` per rendere più difficile la lettura del codice da parte di altri utenti. Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="see-also"></a>Vedere anche

- [Generics](../../../../csharp/programming-guide/generics/index.md)
