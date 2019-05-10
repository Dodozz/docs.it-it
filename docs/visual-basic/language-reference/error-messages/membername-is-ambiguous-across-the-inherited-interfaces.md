---
title: "'<membername>' è ambiguo nelle interfacce ereditate '<interfacename1>' e '<interfacename2>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 71f8cb96c9981bbfc55236ea815fa5f5cb0e8aaf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622667"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="9eb57-102">«\<nomeMembro >' è ambiguo nelle interfacce ereditate\<interfacename1 >' e '\<interfacename2 >»</span><span class="sxs-lookup"><span data-stu-id="9eb57-102">'\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>
<span data-ttu-id="9eb57-103">L'interfaccia eredita più interfacce di due o più membri con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="9eb57-103">The interface inherits two or more members with the same name from multiple interfaces.</span></span>  
  
 <span data-ttu-id="9eb57-104">**ID errore:** BC30685</span><span class="sxs-lookup"><span data-stu-id="9eb57-104">**Error ID:** BC30685</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9eb57-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9eb57-105">To correct this error</span></span>  
  
- <span data-ttu-id="9eb57-106">Il cast del valore per l'interfaccia di base che si desidera utilizzare; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="9eb57-106">Cast the value to the base interface that you want to use; for example:</span></span>  
  
    ```  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9eb57-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9eb57-107">See also</span></span>

- [<span data-ttu-id="9eb57-108">Interfacce</span><span class="sxs-lookup"><span data-stu-id="9eb57-108">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
