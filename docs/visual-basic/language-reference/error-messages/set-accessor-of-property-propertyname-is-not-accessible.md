---
title: '&#39;Impostare&#39; funzione di accesso della proprietà &#39; &lt;propertyname&gt; &#39; non è accessibile'
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: a543506b06742f3ee9101edbac962e761ddd531d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606569"
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a>&#39;Impostare&#39; funzione di accesso della proprietà &#39; &lt;propertyname&gt; &#39; non è accessibile
Un'istruzione tenta di archiviare il valore di una proprietà quando non ha accesso alla proprietà `Set` procedure.  
  
 Se il [impostare l'istruzione](../../../visual-basic/language-reference/statements/set-statement.md) è contrassegnata con un accesso più restrittivo livello relativo [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), un tentativo di impostare il valore della proprietà potrebbe non riuscire nei casi seguenti:  
  
-   Il `Set` istruzione è contrassegnata [Private](../../../visual-basic/language-reference/modifiers/private.md) e il codice chiamante è di fuori della classe o struttura in cui la proprietà è definita.  
  
-   Il `Set` istruzione è contrassegnata [Protected](../../../visual-basic/language-reference/modifiers/protected.md) e il codice chiamante non nella classe o struttura in cui la proprietà è definita, né in una classe derivata.  
  
-   Il `Set` istruzione è contrassegnata [Friend](../../../visual-basic/language-reference/modifiers/friend.md) e il codice chiamante non è presente nello stesso assembly in cui la proprietà è definita.  
  
 **ID errore:** BC31102  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se si ha il controllo del codice sorgente che definisce la proprietà, si consideri la dichiarazione di `Set` procedure con lo stesso livello di accesso della proprietà stessa.  
  
-   Se non si ha il controllo del codice sorgente che definisce la proprietà o se è necessario limitare il `Set` procedure più la proprietà stessa, provare a spostare l'istruzione che imposta il valore della proprietà in un'area di codice che ha un accesso migliore a livello di accesso di proprietà.  
  
## <a name="see-also"></a>Vedere anche
- [Routine Property](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
