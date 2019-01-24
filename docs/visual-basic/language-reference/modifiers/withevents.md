---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: e1a6cecdf724603b8f4617fe4e8b5ef2c0acdeff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624561"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="9c06a-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c06a-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="9c06a-103">Specifica che una o più variabili membro dichiarate fanno riferimento a un'istanza di una classe che può generare eventi.</span><span class="sxs-lookup"><span data-stu-id="9c06a-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c06a-104">Note</span><span class="sxs-lookup"><span data-stu-id="9c06a-104">Remarks</span></span>  
 <span data-ttu-id="9c06a-105">Quando una variabile viene definita tramite `WithEvents`, è possibile specificare in modo dichiarativo in cui un metodo gestisce gli eventi della variabile usando la `Handles` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="9c06a-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="9c06a-106">È possibile usare `WithEvents` solo a livello di classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="9c06a-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="9c06a-107">Ciò significa che il contesto della dichiarazione per un `WithEvents` variabile deve essere una classe o un modulo e non può essere un file di origine, lo spazio dei nomi, struttura o procedura.</span><span class="sxs-lookup"><span data-stu-id="9c06a-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="9c06a-108">Non è possibile usare `WithEvents` su un membro della struttura.</span><span class="sxs-lookup"><span data-stu-id="9c06a-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="9c06a-109">È possibile dichiarare solo singole variabili, ovvero non matrici, ovvero con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="9c06a-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9c06a-110">Regole</span><span class="sxs-lookup"><span data-stu-id="9c06a-110">Rules</span></span>  
  
-   <span data-ttu-id="9c06a-111">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="9c06a-111">**Element Types.**</span></span> <span data-ttu-id="9c06a-112">È necessario dichiarare `WithEvents` variabili come variabili oggetto in modo che accettino le istanze di classe.</span><span class="sxs-lookup"><span data-stu-id="9c06a-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="9c06a-113">Tuttavia, non è possibile dichiarare come `Object`.</span><span class="sxs-lookup"><span data-stu-id="9c06a-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="9c06a-114">È necessario dichiararli come la classe specifica in grado di generare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="9c06a-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="9c06a-115">Il `WithEvents` modificatore può essere usato in questo contesto: [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="9c06a-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c06a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c06a-116">See also</span></span>
- [<span data-ttu-id="9c06a-117">Handles</span><span class="sxs-lookup"><span data-stu-id="9c06a-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="9c06a-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9c06a-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="9c06a-119">Eventi</span><span class="sxs-lookup"><span data-stu-id="9c06a-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
