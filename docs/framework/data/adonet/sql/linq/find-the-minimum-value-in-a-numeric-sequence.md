---
title: Trovare il valore minimo in una sequenza numerica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
ms.openlocfilehash: 84002609c550cc2de76f9948bf77f9fd88261f64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038454"
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a>Trovare il valore minimo in una sequenza numerica
Usare l'operatore <xref:System.Linq.Enumerable.Min%2A> affinché venga restituito il valore minimo da una sequenza di valori numerici.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene cercato il prezzo unitario più basso di qualsiasi prodotto.  
  
 Se si esegue questa query sul database di esempio Northwind, l'output sarà: `2.5000`.  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene cercato il costo di trasporto più basso per qualsiasi ordine.  
  
 Se si esegue questa query sul database di esempio Northwind, l'output sarà: `0.0200`.  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato Min per cercare in `Products` gli elementi con il prezzo unitario più basso di ogni categoria. L'output viene disposto per categoria.  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 Se si esegue la query precedente sul database di esempio Northwind, i risultati saranno simili ai seguenti:  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## <a name="see-also"></a>Vedere anche

- [Query di aggregazione](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)
- [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
