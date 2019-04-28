---
title: '#If... Then... #Else direttive (Visual Basic)'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
ms.openlocfilehash: 8c0aece749edf144fdd5c8ede9ec7e2e4c96ad54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746741"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="82136-102">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="82136-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="82136-103">Viene compilata in modo condizionale selezionati blocchi di codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="82136-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82136-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82136-104">Syntax</span></span>  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a><span data-ttu-id="82136-105">Parti</span><span class="sxs-lookup"><span data-stu-id="82136-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="82136-106">Obbligatorio per `#If` e `#ElseIf` istruzioni facoltative in un' posizione.</span><span class="sxs-lookup"><span data-stu-id="82136-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="82136-107">Qualsiasi espressione, costituito esclusivamente da uno o più costanti del compilatore condizionale, i valori letterali e gli operatori, che restituisce `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="82136-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="82136-108">Obbligatorio per `#If` istruzione blocco, facoltativo in un' posizione.</span><span class="sxs-lookup"><span data-stu-id="82136-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="82136-109">Righe programma Visual Basic o le direttive del compilatore che vengono compilate se l'espressione associata viene valutata `True`.</span><span class="sxs-lookup"><span data-stu-id="82136-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="82136-110">Termina il `#If` blocco di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="82136-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82136-111">Note</span><span class="sxs-lookup"><span data-stu-id="82136-111">Remarks</span></span>  
 <span data-ttu-id="82136-112">Nell'area di, il comportamento dei `#If...Then...#Else` direttive viene visualizzato lo stesso del `If...Then...Else` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="82136-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="82136-113">Tuttavia, il `#If...Then...#Else` direttive valutano ciò che viene compilato dal compilatore, mentre il `If...Then...Else` le istruzioni vengono valutate le condizioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="82136-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="82136-114">Compilazione condizionale viene in genere utilizzata per la compilazione del programma stesso per le diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="82136-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="82136-115">Viene inoltre usato per impedire il debug del codice venga visualizzato in un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="82136-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="82136-116">Codice escluso durante la compilazione condizionale viene omesso completamente dal file eseguibile finale, in modo che non ha alcun effetto sulla dimensione o delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="82136-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="82136-117">Indipendentemente dal risultato di qualsiasi valutazione, tutte le espressioni vengono valutate usando `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="82136-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="82136-118">Il `Option Compare` istruzione non ha effetto sulle espressioni nelle `#If` e `#ElseIf` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="82136-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82136-119">Nessun formato a riga singola del `#If`, `#Else`, `#ElseIf`, e `#End If` direttive esiste.</span><span class="sxs-lookup"><span data-stu-id="82136-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="82136-120">Nessun altro codice può apparire sulla stessa riga come una delle direttive.</span><span class="sxs-lookup"><span data-stu-id="82136-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="82136-121">Le istruzioni all'interno di un blocco di compilazione condizionale devono includere istruzioni logiche completate.</span><span class="sxs-lookup"><span data-stu-id="82136-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="82136-122">Ad esempio, non è possibile compilare in modo condizionale solo gli attributi di una funzione, ma è possibile dichiarare in modo condizionale la funzione insieme ai relativi attributi:</span><span class="sxs-lookup"><span data-stu-id="82136-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="82136-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="82136-123">Example</span></span>
 <span data-ttu-id="82136-124">Questo esempio viene usato il `#If...Then...#Else` costrutto per determinare se si desidera compilare alcune istruzioni.</span><span class="sxs-lookup"><span data-stu-id="82136-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="82136-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82136-125">See also</span></span>

- [<span data-ttu-id="82136-126">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="82136-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="82136-127">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="82136-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="82136-128">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="82136-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
