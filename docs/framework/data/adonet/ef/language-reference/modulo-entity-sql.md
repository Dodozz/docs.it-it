---
title: (Modulo) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: e2d2c4cd6fd62cf5785d6b69aa399a74f8d04d30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760480"
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="cfedf-102">(Modulo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cfedf-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="cfedf-103">Restituisce il resto di un'espressione divisa per un'altra.</span><span class="sxs-lookup"><span data-stu-id="cfedf-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfedf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfedf-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="cfedf-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="cfedf-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="cfedf-106">Espressione numerica da dividere.</span><span class="sxs-lookup"><span data-stu-id="cfedf-106">The numeric expression to divide.</span></span> <span data-ttu-id="cfedf-107">`dividend` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="cfedf-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="cfedf-108">Espressione numerica per la quale dividere il dividendo.</span><span class="sxs-lookup"><span data-stu-id="cfedf-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="cfedf-109">`divisor` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="cfedf-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="cfedf-110">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="cfedf-110">Result Types</span></span>  
 <span data-ttu-id="cfedf-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="cfedf-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfedf-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="cfedf-112">Example</span></span>  
 <span data-ttu-id="cfedf-113">Nella query Entity SQL seguente viene usato l'operatore aritmetico % per restituire il resto della divisione di un'espressione per un'altra.</span><span class="sxs-lookup"><span data-stu-id="cfedf-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="cfedf-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="cfedf-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cfedf-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfedf-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="cfedf-116">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="cfedf-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="cfedf-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="cfedf-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfedf-118">See also</span></span>

- [<span data-ttu-id="cfedf-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cfedf-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
