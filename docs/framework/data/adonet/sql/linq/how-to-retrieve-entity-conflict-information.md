---
title: 'Procedura: Recuperare informazioni sui conflitti di entità'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: 825ba2a32e7c75e922ca08386b9f6efede7b2693
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154752"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="4e3cd-102">Procedura: Recuperare informazioni sui conflitti di entità</span><span class="sxs-lookup"><span data-stu-id="4e3cd-102">How to: Retrieve Entity Conflict Information</span></span>
<span data-ttu-id="4e3cd-103">È possibile usare oggetti della classe <xref:System.Data.Linq.ObjectChangeConflict> per fornire informazioni sui conflitti rivelati dalle eccezioni <xref:System.Data.Linq.ChangeConflictException>.</span><span class="sxs-lookup"><span data-stu-id="4e3cd-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="4e3cd-104">Per altre informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4e3cd-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e3cd-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e3cd-105">Example</span></span>  
 <span data-ttu-id="4e3cd-106">L'esempio riportato di seguito consente di scorrere un elenco di conflitti accumulati.</span><span class="sxs-lookup"><span data-stu-id="4e3cd-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4e3cd-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e3cd-107">See also</span></span>

- [<span data-ttu-id="4e3cd-108">Procedura: Gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="4e3cd-108">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
