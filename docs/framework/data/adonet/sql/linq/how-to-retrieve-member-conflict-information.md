---
title: 'Procedura: Recuperare informazioni sui conflitti tra membri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: fae1513e7a7ead98318d907b220b7510758c9ffe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037603"
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="49ec9-102">Procedura: Recuperare informazioni sui conflitti tra membri</span><span class="sxs-lookup"><span data-stu-id="49ec9-102">How to: Retrieve Member Conflict Information</span></span>
<span data-ttu-id="49ec9-103">È possibile usare la classe <xref:System.Data.Linq.MemberChangeConflict> per recuperare informazioni sui singoli membri in conflitto.</span><span class="sxs-lookup"><span data-stu-id="49ec9-103">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="49ec9-104">In questo stesso contesto è possibile provvedere alla gestione personalizzata del conflitto per qualsiasi membro.</span><span class="sxs-lookup"><span data-stu-id="49ec9-104">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="49ec9-105">Per altre informazioni, vedere [la concorrenza ottimistica: Panoramica](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="49ec9-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ec9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="49ec9-106">Example</span></span>  
 <span data-ttu-id="49ec9-107">Il codice riportato di seguito consente di scorrere gli oggetti <xref:System.Data.Linq.ObjectChangeConflict></span><span class="sxs-lookup"><span data-stu-id="49ec9-107">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="49ec9-108">quindi, per ogni oggetto, di scorrere gli oggetti <xref:System.Data.Linq.MemberChangeConflict>.</span><span class="sxs-lookup"><span data-stu-id="49ec9-108">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49ec9-109">Includere <xref:System.Reflection> in modo da fornire informazioni su <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.</span><span class="sxs-lookup"><span data-stu-id="49ec9-109">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="49ec9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49ec9-110">See also</span></span>

- [<span data-ttu-id="49ec9-111">Procedura: Gestire i conflitti di modifiche</span><span class="sxs-lookup"><span data-stu-id="49ec9-111">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
