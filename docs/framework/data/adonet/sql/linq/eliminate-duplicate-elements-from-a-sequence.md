---
title: Eliminare elementi duplicati da una sequenza
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b224a84-bad5-4843-adcc-14e784d280f5
ms.openlocfilehash: 604307bd179136c9c2b685faa5164f9b5ecabaf9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738170"
---
# <a name="eliminate-duplicate-elements-from-a-sequence"></a>Eliminare elementi duplicati da una sequenza
Per eliminare elementi duplicati da una sequenza, usare l'operatore <xref:System.Linq.Queryable.Distinct%2A>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene usato <xref:System.Linq.Queryable.Distinct%2A> per selezionare una sequenza di città univoche in cui sono presenti clienti.  
  
 [!code-csharp[DLinqQueryExamples#36](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#36)]
 [!code-vb[DLinqQueryExamples#36](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#36)]  
  
## <a name="see-also"></a>Vedere anche
- [Esempi di query](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
