---
title: "&#39;&lt;nomeMembro&gt; &#39; non può esporre il tipo &#39; &lt;nomeTipo&gt; &#39; all'esterno del progetto mediante &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 39d316aca5ec306de4b1e43e2eb2d1495f5525d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672344"
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a><span data-ttu-id="86bdd-102">&#39;&lt;nomeMembro&gt; &#39; non può esporre il tipo &#39; &lt;nomeTipo&gt; &#39; all'esterno del progetto mediante &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="86bdd-102">&#39;&lt;membername&gt;&#39; cannot expose type &#39;&lt;typename&gt;&#39; outside the project through &lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;</span></span>
<span data-ttu-id="86bdd-103">Una variabile, parametro di routine o restituito dalla funzione viene esposto all'esterno del relativo contenitore, ma viene dichiarato come un tipo che non deve essere esposto all'esterno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="86bdd-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="86bdd-104">Lo scheletro di codice seguente viene illustrata una situazione che genera l'errore.</span><span class="sxs-lookup"><span data-stu-id="86bdd-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="86bdd-105">Un tipo dichiarato `Protected`, `Friend`, `Protected Friend`, o `Private` deve avere accesso all'esterno del contesto di dichiarazione limitato.</span><span class="sxs-lookup"><span data-stu-id="86bdd-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="86bdd-106">Per utilizzarlo come i dati di tipo di una variabile con meno restrizioni accesso vanificherebbe lo scopo.</span><span class="sxs-lookup"><span data-stu-id="86bdd-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="86bdd-107">Nel codice precedente, `exposedVar` viene `Public` e consente di esporre `privateClass` al codice che non dovrebbe avere accesso a esso.</span><span class="sxs-lookup"><span data-stu-id="86bdd-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="86bdd-108">**ID errore:** BC30909</span><span class="sxs-lookup"><span data-stu-id="86bdd-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86bdd-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="86bdd-109">To correct this error</span></span>  
  
-   <span data-ttu-id="86bdd-110">Modifica il livello di accesso della variabile, parametro di routine o funzione, tornare a essere restrittivi almeno quanto il livello di accesso del relativo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="86bdd-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86bdd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86bdd-111">See also</span></span>
- [<span data-ttu-id="86bdd-112">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="86bdd-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
