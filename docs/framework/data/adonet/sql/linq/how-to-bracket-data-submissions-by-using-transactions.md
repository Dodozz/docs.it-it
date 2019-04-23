---
title: 'Procedura: Racchiudere tra parentesi quadre gli invii di dati usando transazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 3e58c6f2849ed9714b3356662dae313ab9d11696
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134004"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="fbbe9-102">Procedura: Racchiudere tra parentesi quadre gli invii di dati usando transazioni</span><span class="sxs-lookup"><span data-stu-id="fbbe9-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="fbbe9-103">È possibile usare <xref:System.Transactions.TransactionScope> per raggruppare gli invii al database.</span><span class="sxs-lookup"><span data-stu-id="fbbe9-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="fbbe9-104">Per altre informazioni, vedere [supporto delle transazioni](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="fbbe9-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbbe9-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbbe9-105">Example</span></span>  
 <span data-ttu-id="fbbe9-106">Nel codice seguente l'invio al database viene incluso in <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="fbbe9-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="fbbe9-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbbe9-107">See also</span></span>

- [<span data-ttu-id="fbbe9-108">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="fbbe9-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="fbbe9-109">Creazione e invio di modifiche dei dati</span><span class="sxs-lookup"><span data-stu-id="fbbe9-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="fbbe9-110">Supporto delle transazioni</span><span class="sxs-lookup"><span data-stu-id="fbbe9-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
