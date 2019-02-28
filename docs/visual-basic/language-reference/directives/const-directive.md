---
title: '#Const (direttiva) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: fb937a5a9d4688730085829350cb20172db50e97
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967048"
---
# <a name="const-directive"></a><span data-ttu-id="ed7c9-102">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="ed7c9-102">#Const Directive</span></span>
<span data-ttu-id="ed7c9-103">Definisce le costanti del compilatore condizionale per Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed7c9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed7c9-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ed7c9-105">Parti</span><span class="sxs-lookup"><span data-stu-id="ed7c9-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="ed7c9-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-106">Required.</span></span> <span data-ttu-id="ed7c9-107">Nome della costante da definire.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="ed7c9-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-108">Required.</span></span> <span data-ttu-id="ed7c9-109">Valore letterale, altra costante di compilazione condizionale o qualsiasi combinazione che include uno o tutti gli operatori aritmetici o logici, tranne `Is`.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed7c9-110">Note</span><span class="sxs-lookup"><span data-stu-id="ed7c9-110">Remarks</span></span>  
 <span data-ttu-id="ed7c9-111">Costanti del compilatore condizionale sono sempre private per il file in cui vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="ed7c9-112">Non è possibile creare le costanti del compilatore pubblico usando il `#Const` direttiva; è possibile creare solo nell'interfaccia utente o con il `/define` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="ed7c9-113">È possibile utilizzare solo costanti del compilatore condizionale e i valori letterali in `expression`.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="ed7c9-114">Utilizzo di una costante di standard definita con `Const` provoca un errore.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="ed7c9-115">Al contrario, è possibile utilizzare costanti definite con la `#Const` parola chiave solo per la compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="ed7c9-116">Costanti può anche essere indefinito, nel qual caso hanno un valore di `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed7c9-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed7c9-117">Example</span></span>  
 <span data-ttu-id="ed7c9-118">In questo esempio viene usata la direttiva `#Const`.</span><span class="sxs-lookup"><span data-stu-id="ed7c9-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ed7c9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed7c9-119">See also</span></span>
- [<span data-ttu-id="ed7c9-120">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed7c9-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
- [<span data-ttu-id="ed7c9-121">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="ed7c9-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="ed7c9-122">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="ed7c9-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="ed7c9-123">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="ed7c9-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="ed7c9-124">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="ed7c9-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
