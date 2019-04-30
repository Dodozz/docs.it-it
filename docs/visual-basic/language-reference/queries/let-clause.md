---
title: Clausola Let (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: ff298f001a2d865446436e8099a2fbbef593a00a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054198"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="c9e43-102">Clausola Let (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9e43-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="c9e43-103">Calcola un valore e lo assegna a una nuova variabile all'interno della query.</span><span class="sxs-lookup"><span data-stu-id="c9e43-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9e43-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9e43-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="c9e43-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c9e43-105">Parts</span></span>  
  
|<span data-ttu-id="c9e43-106">Termine</span><span class="sxs-lookup"><span data-stu-id="c9e43-106">Term</span></span>|<span data-ttu-id="c9e43-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="c9e43-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="c9e43-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c9e43-108">Required.</span></span> <span data-ttu-id="c9e43-109">Un alias che può essere utilizzato per fare riferimento ai risultati dell'espressione fornita.</span><span class="sxs-lookup"><span data-stu-id="c9e43-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="c9e43-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c9e43-110">Required.</span></span> <span data-ttu-id="c9e43-111">Un'espressione che verrà valutata e assegnata alla variabile specificata.</span><span class="sxs-lookup"><span data-stu-id="c9e43-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9e43-112">Note</span><span class="sxs-lookup"><span data-stu-id="c9e43-112">Remarks</span></span>  
 <span data-ttu-id="c9e43-113">Il `Let` clausola consente di calcolare i valori per ogni risultato della query e farvi riferimento utilizzando un alias.</span><span class="sxs-lookup"><span data-stu-id="c9e43-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="c9e43-114">L'alias può essere utilizzato in altre clausole, ad esempio il `Where` clausola.</span><span class="sxs-lookup"><span data-stu-id="c9e43-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="c9e43-115">Il `Let` clausola consente di creare un'istruzione di query che è più facile da leggere in quanto è possibile specificare un alias per una clausola dell'espressione inclusa nella query e sostituire l'alias ogni volta che viene utilizzata la clausola dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="c9e43-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="c9e43-116">È possibile includere un numero qualsiasi di `variable` e `expression` assegnazioni nel `Let` clausola.</span><span class="sxs-lookup"><span data-stu-id="c9e43-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="c9e43-117">Separare ogni assegnazione con una virgola (,).</span><span class="sxs-lookup"><span data-stu-id="c9e43-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9e43-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9e43-118">Example</span></span>  
 <span data-ttu-id="c9e43-119">Il codice seguente viene illustrato come utilizzare il `Let` clausola per calcolare un 10% di sconto sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="c9e43-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="c9e43-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9e43-120">See also</span></span>

- [<span data-ttu-id="c9e43-121">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c9e43-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="c9e43-122">Query</span><span class="sxs-lookup"><span data-stu-id="c9e43-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="c9e43-123">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="c9e43-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="c9e43-124">Clausola From</span><span class="sxs-lookup"><span data-stu-id="c9e43-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="c9e43-125">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="c9e43-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
