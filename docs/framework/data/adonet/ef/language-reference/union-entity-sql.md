---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: b7818866571fc362e56e8fdea3344f0888f1a2aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679838"
---
# <a name="union-entity-sql"></a><span data-ttu-id="8ee98-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8ee98-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="8ee98-103">Combina i risultati di due o più query in una singola raccolta.</span><span class="sxs-lookup"><span data-stu-id="8ee98-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee98-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ee98-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8ee98-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8ee98-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8ee98-106">Qualsiasi espressione di query valida che restituisce una raccolta da combinare con le espressioni ALL della raccolta deve essere dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="8ee98-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="8ee98-107">UNION</span><span class="sxs-lookup"><span data-stu-id="8ee98-107">UNION</span></span>  
 <span data-ttu-id="8ee98-108">Specifica che più raccolte devono essere combinate e restituite come singola raccolta.</span><span class="sxs-lookup"><span data-stu-id="8ee98-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="8ee98-109">ALL</span><span class="sxs-lookup"><span data-stu-id="8ee98-109">ALL</span></span>  
 <span data-ttu-id="8ee98-110">Specifica che più raccolte devono essere combinate e restituite come singola raccolta, inclusi i duplicati.</span><span class="sxs-lookup"><span data-stu-id="8ee98-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="8ee98-111">Se non viene specificato, i duplicati vengono rimossi dalla raccolta dei risultati.</span><span class="sxs-lookup"><span data-stu-id="8ee98-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ee98-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8ee98-112">Return Value</span></span>  
 <span data-ttu-id="8ee98-113">Raccolta dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="8ee98-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ee98-114">Note</span><span class="sxs-lookup"><span data-stu-id="8ee98-114">Remarks</span></span>  
 <span data-ttu-id="8ee98-115">UNION è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ee98-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="8ee98-116">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="8ee98-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="8ee98-117">Per informazioni sulla priorità per la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori sui set, vedere [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8ee98-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ee98-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ee98-118">Example</span></span>  
 <span data-ttu-id="8ee98-119">Nella query Entity SQL seguente viene usato l'operatore UNION ALL per combinare i risultati di due query in una singola raccolta.</span><span class="sxs-lookup"><span data-stu-id="8ee98-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="8ee98-120">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8ee98-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8ee98-121">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ee98-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8ee98-122">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8ee98-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="8ee98-123">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="8ee98-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="8ee98-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ee98-124">See also</span></span>
- [<span data-ttu-id="8ee98-125">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8ee98-125">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
