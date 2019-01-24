---
title: '- (Divisione) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 42fc5e2a9f9f159a8a60973dbed6540b3188fba6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745234"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="833eb-102">/ (divisione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="833eb-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="833eb-103">Divide un numero per un altro.</span><span class="sxs-lookup"><span data-stu-id="833eb-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="833eb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="833eb-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="833eb-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="833eb-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="833eb-106">Espressione numerica da dividere.</span><span class="sxs-lookup"><span data-stu-id="833eb-106">The numeric expression to divide.</span></span> <span data-ttu-id="833eb-107">`dividend` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="833eb-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="833eb-108">Espressione numerica per la quale dividere il dividendo.</span><span class="sxs-lookup"><span data-stu-id="833eb-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="833eb-109">`divisor` è qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="833eb-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="833eb-110">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="833eb-110">Result Types</span></span>  
 <span data-ttu-id="833eb-111">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="833eb-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="833eb-112">Per altre informazioni sulla promozione implicita del tipo, vedere [sistema di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="833eb-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="833eb-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="833eb-113">Example</span></span>  
 <span data-ttu-id="833eb-114">Le query Entity SQL seguente viene usato l'aritmetico / per dividere un numero per un altro operatore.</span><span class="sxs-lookup"><span data-stu-id="833eb-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="833eb-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="833eb-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="833eb-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="833eb-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="833eb-117">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="833eb-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="833eb-118">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="833eb-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="833eb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="833eb-119">See also</span></span>
- [<span data-ttu-id="833eb-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="833eb-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
