---
title: Clausola Skip While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 3d6caeb1938e8e53e8ec2575f740cd5e49496f62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054419"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="5d427-102">Clausola Skip While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d427-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="5d427-103">Ignora gli elementi in una raccolta finché una condizione specificata è `true` e quindi restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="5d427-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d427-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d427-104">Syntax</span></span>  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="5d427-105">Parti</span><span class="sxs-lookup"><span data-stu-id="5d427-105">Parts</span></span>  
  
|<span data-ttu-id="5d427-106">Termine</span><span class="sxs-lookup"><span data-stu-id="5d427-106">Term</span></span>|<span data-ttu-id="5d427-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="5d427-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="5d427-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5d427-108">Required.</span></span> <span data-ttu-id="5d427-109">Un'espressione che rappresenta una condizione di test per gli elementi.</span><span class="sxs-lookup"><span data-stu-id="5d427-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="5d427-110">L'espressione deve restituire un `Boolean` valore o un equivalente funzionale, ad esempio un `Integer` deve essere valutata come un `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5d427-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d427-111">Note</span><span class="sxs-lookup"><span data-stu-id="5d427-111">Remarks</span></span>  
 <span data-ttu-id="5d427-112">Il `Skip While` clausola ignora gli elementi dall'inizio del risultato della query finché l'oggetto fornito `expression` restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="5d427-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="5d427-113">Dopo aver `expression` restituisce `false`, la query restituisce tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="5d427-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="5d427-114">Il `expression` viene ignorato per i risultati rimanenti.</span><span class="sxs-lookup"><span data-stu-id="5d427-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="5d427-115">Il `Skip While` clausola differisce dal `Where` clausola in quanto il `Where` clausola può essere utilizzata per escludere tutti gli elementi da una query che non soddisfano una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="5d427-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="5d427-116">Il `Skip While` clausola esclude gli elementi solo fino al primo non viene soddisfatta la condizione.</span><span class="sxs-lookup"><span data-stu-id="5d427-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="5d427-117">Il `Skip While` clausola è particolarmente utile quando si lavora con un risultato della query ordinati.</span><span class="sxs-lookup"><span data-stu-id="5d427-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="5d427-118">È possibile ignorare un determinato numero di risultati a partire dall'inizio del risultato della query usando il `Skip` clausola.</span><span class="sxs-lookup"><span data-stu-id="5d427-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d427-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d427-119">Example</span></span>  
 <span data-ttu-id="5d427-120">Il codice seguente viene illustrato come utilizzare il `Skip While` clausola per ignorare i risultati fino a quando non viene trovato il primo cliente dagli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="5d427-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5d427-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d427-121">See also</span></span>

- [<span data-ttu-id="5d427-122">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d427-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5d427-123">Query</span><span class="sxs-lookup"><span data-stu-id="5d427-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="5d427-124">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="5d427-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="5d427-125">Clausola From</span><span class="sxs-lookup"><span data-stu-id="5d427-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="5d427-126">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="5d427-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="5d427-127">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="5d427-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="5d427-128">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="5d427-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
