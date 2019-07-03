---
title: Query in LINQ to Entities
ms.date: 03/30/2017
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
ms.openlocfilehash: 268906f8b79c8baf1ac6e29012b0ae7194b17084
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539436"
---
# <a name="queries-in-linq-to-entities"></a>Query in LINQ to Entities
Una query è un'espressione che recupera dati da un'origine dati. Le query sono in genere espresse in un linguaggio di query specializzato, ad esempio SQL per i database relazionali e XQuery per XML. Gli sviluppatori hanno dovuto pertanto imparare un nuovo linguaggio di query per ogni tipo di origine dati o formato dati usato per le query. LINQ (Language-Integrated Query) offre un modello più semplice e coerente per l'uso di dati in diversi tipi di origini dati e formati di dati. In una query LINQ vengono sempre usati oggetti di programmazione.  
  
 Un'operazione di query LINQ comporta tre azioni: il recupero di una o più origini dati, la creazione della query e l'esecuzione della query.  
  
 È possibile usare LINQ per eseguire query su origini dati che implementano l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>. Le istanze del tipo generico <xref:System.Data.Objects.ObjectQuery%601> classe che implementa l'interfaccia generica <xref:System.Linq.IQueryable%601> interfaccia, fungono da origine dati per LINQ alle query di entità. La classe generica <xref:System.Data.Objects.ObjectQuery%601> rappresenta una query che restituisce una raccolta di zero o più oggetti tipizzati. È anche possibile consentire al compilatore dedurre il tipo di un'entità utilizzando la parola chiave c# `var` (Dim in Visual Basic).  
  
 Nella query è necessario specificare esattamente le informazioni che si desidera recuperare dall'origine dati. Una query può inoltre specificare in che modo ordinare, raggruppare e formattare le informazioni prima che vengano restituite. In LINQ una query viene archiviata in una variabile. Se la query restituisce una sequenza di valori, la variabile di query deve essere un tipo queryable. La variabile di query non esegue azioni né restituisce dati. Viene solo usata per archiviare le informazioni sulla query. Dopo aver creato una query è necessario eseguirla per recuperare eventuali dati.  
  
## <a name="query-syntax"></a>Sintassi della query  
 Le query LINQ to Entities possono essere composte in due sintassi diverse, ovvero la sintassi delle espressioni di query e la sintassi delle query basate su metodo. Sintassi delle espressioni di query sono le novità di c# 3.0 e Visual Basic 9.0 ed è costituito da un set di clausole scritte in una sintassi dichiarativa simile a Transact-SQL o XQuery. Tuttavia, .NET Framework common language runtime (CLR) non è possibile leggere la sintassi delle espressioni di query stessa. Pertanto, in fase di compilazione, le espressioni di query vengono convertite in chiamate al metodo in modo da poter essere usate da CLR. Questi metodi sono noti come il *operatori query standard*. Gli sviluppatori possono scegliere di chiamare direttamente questi metodi usando la relativa sintassi, anziché usare la sintassi delle query. Per altre informazioni, vedere [Sintassi di query e sintassi di metodi in LINQ](~/docs/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
### <a name="query-expression-syntax"></a>Sintassi delle espressioni di query  
 Le espressioni di query vengono scritte in una sintassi di query dichiarativa. Questa sintassi consente a uno sviluppatore di scrivere query in un linguaggio di alto livello formattato in modo simile a Transact-SQL. Tramite la sintassi delle espressioni di query è possibile eseguire anche complesse operazioni di filtro, ordinamento e raggruppamento sulle origini dati usando una quantità minima di codice. Per altre informazioni, [operazioni di Query (Visual Basic) base](~/docs/visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Per esempi che illustrano come usare la sintassi delle espressioni di query, vedere gli argomenti seguenti:  
  
- [Esempi di sintassi di espressione di query: Proiezione](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-projection.md)  
  
- [Esempi di sintassi di espressione di query: Filtering](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-filtering.md)  
  
- [Esempi di sintassi di espressione di query: Ordinamento](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-ordering.md)  
  
- [Esempi di sintassi di espressione di query: Operatori di aggregazione](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-aggregate-operators.md)  
  
- [Esempi di sintassi di espressione di query: Partitioning](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-partitioning.md)  
  
- [Esempi di sintassi di espressione di query: Operatori di join](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-join-operators.md)  
  
- [Esempi di sintassi di espressione di query: Operatori di elemento](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-element-operators.md)  
  
- [Esempi di sintassi di espressione di query: raggruppamento](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-grouping.md)  
  
- [Esempi di sintassi di espressione di query: Esplorazione di relazioni](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-navigating-relationships.md)  
  
### <a name="method-based-query-syntax"></a>Sintassi delle query basate su metodo  
 Un altro modo per comporre LINQ alle query di entità consiste nell'usare le query basate su metodo. La sintassi di query basate su metodo è una sequenza di chiamate dirette ai metodi degli operatori LINQ, come i parametri vengono passate espressioni lambda. Per altre informazioni, vedere [Espressioni lambda](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md). Per esempi che illustrano come usare la sintassi delle query basate su metodo, consultare gli argomenti seguenti:  
  
- [Esempi di sintassi di Query basate sul metodo: Proiezione](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-projection.md)  
  
- [Esempi di sintassi di Query basate sul metodo: Filtering](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-filtering.md)  
  
- [Esempi di sintassi di Query basate sul metodo: Ordinamento](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-ordering.md)  
  
- [Esempi di sintassi di Query basate sul metodo: Operatori di aggregazione](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-aggregate-operators.md)  
  
- [Esempi di sintassi di Query basate sul metodo: Partitioning](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-partitioning.md)  
  
- [Esempi di sintassi di Query basate sul metodo: Conversione](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-conversion.md)  
  
- [Esempi di sintassi di Query basate sul metodo: Operatori di join](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-join-operators.md)  
  
- [Esempi di sintassi di Query basate sul metodo: Operatori di elemento](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-element-operators.md)  
  
- [Esempi di sintassi di Query basate sul metodo: raggruppamento](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-grouping.md)  
  
- [Esempi di sintassi di Query basate sul metodo: Esplorazione di relazioni](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
- [Nozioni di base su LINQ in C#](~/docs/csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Introduzione a LINQ in Visual Basic](~/docs/visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Opzioni di unione di Entity Framework e query compilate](https://go.microsoft.com/fwlink/?LinkId=199591)
