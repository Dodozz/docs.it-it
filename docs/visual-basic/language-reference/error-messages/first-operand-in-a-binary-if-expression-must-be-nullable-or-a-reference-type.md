---
title: Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: a73a66313e7ca540711838c4d147d6bd163ec8d6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625560"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="922da-102">Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="922da-102">First operand in a binary 'If' expression must be nullable or a reference type</span></span>
<span data-ttu-id="922da-103">Un `If` espressione può avere due o tre argomenti.</span><span class="sxs-lookup"><span data-stu-id="922da-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="922da-104">Quando si inviano solo due argomenti, il primo argomento deve essere un tipo riferimento o un tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="922da-104">When you send only two arguments, the first argument must be a reference type or a nullable type.</span></span> <span data-ttu-id="922da-105">Se il primo argomento restituisce un valore diverso da `Nothing`, viene restituito il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="922da-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="922da-106">Se il primo argomento restituisce `Nothing`, il secondo argomento viene valutato e restituito.</span><span class="sxs-lookup"><span data-stu-id="922da-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="922da-107">Ad esempio, il codice seguente contiene due `If` espressioni, uno con tre argomenti e uno con due argomenti.</span><span class="sxs-lookup"><span data-stu-id="922da-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="922da-108">Le espressioni di calcolare e restituiscono lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="922da-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="922da-109">Questo errore è causato da espressioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="922da-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="922da-110">**ID errore:** BC33107</span><span class="sxs-lookup"><span data-stu-id="922da-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="922da-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="922da-111">To correct this error</span></span>  
  
- <span data-ttu-id="922da-112">Se è possibile modificare il codice in modo che il primo argomento è un tipo che ammette valori null o un tipo riferimento, eseguire la conversione a un argomento di tre `If` expression, o a un `If...Then...Else` istruzione.</span><span class="sxs-lookup"><span data-stu-id="922da-112">If you cannot change the code so that the first argument is a nullable type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="922da-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="922da-113">See also</span></span>

- [<span data-ttu-id="922da-114">Operatore If</span><span class="sxs-lookup"><span data-stu-id="922da-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="922da-115">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="922da-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="922da-116">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="922da-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
