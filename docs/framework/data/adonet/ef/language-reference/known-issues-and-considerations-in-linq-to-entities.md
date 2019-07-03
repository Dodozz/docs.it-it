---
title: Problemi noti e considerazioni in LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: e84319c60534c3ecf154c3f58973bcc429a73842
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539828"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a>Problemi noti e considerazioni in LINQ to Entities
Questa sezione vengono fornite informazioni sui problemi noti con LINQ alle query di entità.  
  
- [Query LINQ che non possono essere memorizzati nella cache](#LINQQueriesThatAreNotCached)  
  
- [Perdita di informazioni di ordinamento](#OrderingInfoLost)  
  
- [Interi senza segno non è supportati](#UnsignedIntsUnsupported)  
  
- [Errori di conversione tipo](#TypeConversionErrors)  
  
- [Riferimento alle variabili Non scalari non supportate](#RefNonScalarClosures)  
  
- [Query nidificata potrebbe non riuscire con SQL Server 2000](#NestedQueriesSQL2000)  
  
- [Proiezione di un tipo anonimo](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a>Query LINQ che non possono essere memorizzate nella cache  
 A partire da .NET Framework 4.5, le query LINQ to Entities vengono memorizzate nella cache automaticamente. Tuttavia, le query LINQ to Entities che applicano l'operatore `Enumerable.Contains` alle raccolte in memoria non vengono memorizzate automaticamente nella cache. Inoltre, la parametrizzazione delle raccolte in memoria nelle query LINQ compilate non è consentita.  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a>Perdita delle informazioni di ordinamento  
 La proiezione di colonne in un tipo anonimo comporta la perdita delle informazioni di ordinamento in alcune query eseguite su un database di [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] con un livello di compatibilità impostato su "80".  Questo avviene quando un nome di colonna nell'elenco di ordinamento corrisponde a un nome di colonna nel selettore, come illustrato nell'esempio seguente:  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a>Mancato supporto degli Unsigned Integer  
 Specificare un tipo unsigned integer in una query LINQ to Entities non è supportata perché il [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] non supporta interi senza segno. Se si specifica un unsigned integer, un <xref:System.ArgumentException> verrà generata l'eccezione durante la conversione di espressioni di query, come illustrato nell'esempio seguente. In questo esempio viene eseguita una query per un ordine con ID 48000.  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a>Errori di conversione dei tipi  
 In Visual Basic quando una proprietà è mappata a una colonna di tipo bit SQL Server con un valore 1 usando la funzione `CByte`, viene generato un evento <xref:System.Data.SqlClient.SqlException> con un messaggio di errore di overflow aritmetico. Nell'esempio seguente viene eseguita una query sulla colonna `Product.MakeFlag` nel database di esempio AdventureWorks e viene generata un'eccezione quando viene eseguita un'iterazione dei risultati della query.  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a>Riferimento a variabili non scalari non supportato  
 Il riferimento in una query a variabili non scalari, ad esempio un'entità, non è supportato. Durante l'esecuzione di una query di questo tipo, viene generata un'eccezione <xref:System.NotSupportedException>, seguita dal messaggio "Impossibile creare un valore di costante di tipo `EntityType`. In questo contesto solo supportati solo i tipi primitivi ('ad esempio Int32, String e GUID')".  
  
> [!NOTE]
>  Il riferimento a una raccolta di variabili scalari supportato.  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a>Errori di esecuzione di query annidate con SQL Server 2000  
 Con SQL Server 2000, è possibile che le query LINQ to Entities non vengano eseguite correttamente se producono query Transact-SQL annidate con tre o più livelli di profondità.  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a>Proiezione in un tipo anonimo  
 Se si definisce il percorso iniziale della query per includere gli oggetti correlati tramite il metodo <xref:System.Data.Objects.ObjectQuery%601.Include%2A> su <xref:System.Data.Objects.ObjectQuery%601> e si usa quindi LINQ per proiettare gli oggetti restituiti in un tipo anonimo, gli oggetti specificati nel metodo di inclusione non vengono inclusi nei risultati della query.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 Per ottenere oggetti correlati, non proiettare i tipi restituiti in un tipo anonimo.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
