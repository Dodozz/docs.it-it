---
title: Istruzione Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: bf3eb6476dc1485faeddab475f29e508175d3378
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840406"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="aa1a0-102">Istruzione Erase (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa1a0-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="aa1a0-103">Utilizzato per rilasciare le variabili di matrice e deallocare la memoria usata per i relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="aa1a0-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa1a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa1a0-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="aa1a0-105">Parti</span><span class="sxs-lookup"><span data-stu-id="aa1a0-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="aa1a0-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="aa1a0-106">Required.</span></span> <span data-ttu-id="aa1a0-107">Elenco di variabili di matrice da cancellare.</span><span class="sxs-lookup"><span data-stu-id="aa1a0-107">List of array variables to be erased.</span></span> <span data-ttu-id="aa1a0-108">Nel caso di più variabili, è possibile separarle mediante virgole.</span><span class="sxs-lookup"><span data-stu-id="aa1a0-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa1a0-109">Note</span><span class="sxs-lookup"><span data-stu-id="aa1a0-109">Remarks</span></span>  
 <span data-ttu-id="aa1a0-110">Il `Erase` istruzione può essere specificata solo a livello di routine.</span><span class="sxs-lookup"><span data-stu-id="aa1a0-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="aa1a0-111">Ciò significa che è possibile rilasciare le matrici all'interno di una routine, ma non a livello di classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="aa1a0-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="aa1a0-112">Il `Erase` istruzione equivale all'assegnazione `Nothing` a ogni variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="aa1a0-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa1a0-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa1a0-113">Example</span></span>  
 <span data-ttu-id="aa1a0-114">L'esempio seguente usa il `Erase` istruzione per due matrici di cancellare e liberare la memoria (1000 e 100 elementi, rispettivamente).</span><span class="sxs-lookup"><span data-stu-id="aa1a0-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="aa1a0-115">Il `ReDim` istruzione quindi assegna una nuova istanza della matrice nella matrice tridimensionale.</span><span class="sxs-lookup"><span data-stu-id="aa1a0-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="aa1a0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa1a0-116">See also</span></span>

- [<span data-ttu-id="aa1a0-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="aa1a0-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="aa1a0-118">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="aa1a0-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
