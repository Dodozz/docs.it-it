---
title: Evento &#39; &lt;eventname1&gt; &#39; non è possibile implementare l'evento &#39; &lt;eventname2&gt; &#39; sull'interfaccia &#39; &lt;interfaccia&gt; &#39; perché i tipi delegati &#39; &lt;delegate1&gt; &#39; e &#39; &lt;delegate2&gt; &#39; non corrispondono
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 024e260f12d3497d64f26e59521f016ad439ebb6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638211"
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a>Evento &#39; &lt;eventname1&gt; &#39; non è possibile implementare l'evento &#39; &lt;eventname2&gt; &#39; sull'interfaccia &#39; &lt;interfaccia&gt; &#39; perché i tipi delegati &#39; &lt;delegate1&gt; &#39; e &#39; &lt;delegate2&gt; &#39; non corrispondono
Visual Basic non può implementare un evento perché il tipo di delegato dell'evento non corrisponde al tipo delegato dell'evento nell'interfaccia. Questo errore può insorgere quando si definiscono più eventi in un'interfaccia e si prova a implementarli assieme con lo stesso evento. Un evento può implementare due o più eventi solo se tutti gli eventi implementati vengono dichiarati usando la sintassi `As` e se tutti specificano lo stesso tipo delegato.  
  
 **ID errore:** BC31423  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Implementare gli eventi separatamente.  
  
     -oppure-  
  
-   Definire gli eventi nell'interfaccia utilizzando il `As` sintassi e specificare lo stesso tipo di delegato.  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
