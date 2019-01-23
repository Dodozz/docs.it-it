---
title: '* (Moltiplicazione) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
ms.openlocfilehash: 68544823d2279b76920e057829fc61a469d39730
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493859"
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="3533c-102">\* (moltiplicazione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3533c-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="3533c-103">Moltiplica due espressioni.</span><span class="sxs-lookup"><span data-stu-id="3533c-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3533c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3533c-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3533c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3533c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3533c-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="3533c-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="3533c-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="3533c-107">Result Types</span></span>  
 <span data-ttu-id="3533c-108">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="3533c-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="3533c-109">Per altre informazioni sulla promozione implicita del tipo, vedere [sistema di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="3533c-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3533c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="3533c-110">Example</span></span>  
 <span data-ttu-id="3533c-111">Nella query Entity SQL seguente viene usato l'operatore aritmetico \* per moltiplicare due numeri.</span><span class="sxs-lookup"><span data-stu-id="3533c-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="3533c-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3533c-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3533c-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3533c-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="3533c-114">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3533c-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="3533c-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3533c-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="3533c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3533c-116">See also</span></span>
- [<span data-ttu-id="3533c-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3533c-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
