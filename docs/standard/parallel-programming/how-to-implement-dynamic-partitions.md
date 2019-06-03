---
title: 'Procedura: Implementare partizioni dinamiche'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5719c6afc1c5efc6138f0a4931d1725a6f20909a
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66424045"
---
# <a name="how-to-implement-dynamic-partitions"></a>Procedura: Implementare partizioni dinamiche

L'esempio seguente mostra come implementare un oggetto <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> personalizzato che implementa il partizionamento dinamico e che può essere usato da determinati overload <xref:System.Threading.Tasks.Parallel.ForEach%2A> e da PLINQ.  
  
## <a name="example"></a>Esempio

Ogni volta che una partizione chiama <xref:System.Collections.IEnumerator.MoveNext%2A> nell'enumeratore, l'enumeratore fornisce la partizione con un elemento dell'elenco. Nel caso di PLINQ e di <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partizione è un'istanza <xref:System.Threading.Tasks.Task>. Poiché le richieste vengono eseguite contemporaneamente su più thread, l'accesso all'indice corrente è sincronizzato.  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

Questo è un esempio di partizionamento in blocchi, con ogni blocco costituito da un elemento. Fornendo più elementi per volta, è possibile ridurre il conflitto sul blocco e ottenere in teoria prestazioni più veloci. A un certo punto, tuttavia, blocchi più grandi potrebbero richiedere logica di bilanciamento del carico aggiuntiva per mantenere occupati tutti i thread fino al completamento del lavoro.  
  
## <a name="see-also"></a>Vedere anche

* [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
* [Procedura: Implementare un partitioner per il partizionamento statico](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
