---
title: '#error - Riferimenti per C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: b335dfeed23d43938c66f0753590af55ac99b12a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235592"
---
# <a name="error-c-reference"></a><span data-ttu-id="4e883-102">#error (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4e883-102">#error (C# Reference)</span></span>
<span data-ttu-id="4e883-103">`#error` consente di generare l'errore definito dall'utente [CS1029](../compiler-messages/cs1029.md) da una posizione specifica nel codice.</span><span class="sxs-lookup"><span data-stu-id="4e883-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="4e883-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4e883-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="4e883-105">Note</span><span class="sxs-lookup"><span data-stu-id="4e883-105">Remarks</span></span>  
 <span data-ttu-id="4e883-106">La direttiva `#error` viene generalmente usata nelle direttive condizionali.</span><span class="sxs-lookup"><span data-stu-id="4e883-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="4e883-107">È possibile anche generare un avviso definito dall'utente tramite [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="4e883-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e883-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="4e883-108">Example</span></span>  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e883-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e883-109">See Also</span></span>

- [<span data-ttu-id="4e883-110">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4e883-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="4e883-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4e883-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4e883-112">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="4e883-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
