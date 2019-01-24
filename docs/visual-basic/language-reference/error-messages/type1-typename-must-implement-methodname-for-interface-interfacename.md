---
title: "&lt;type1&gt;&#39;&lt;typename&gt; &#39; devono implementare &#39; &lt;methodname&gt; &#39; per l'interfaccia &#39; &lt;interfacename&gt;&#39;"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: ff9ffd50f7f21814d5e4c23fd8df50b12bf746f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642441"
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt;typename&gt; &#39; devono implementare &#39; &lt;methodname&gt; &#39; per l'interfaccia &#39; &lt;interfacename&gt;&#39;
Una classe o struttura dichiara di implementare un'interfaccia, ma non implementa una routine definita dall'interfaccia. Ogni membro dell'interfaccia deve essere implementata.  
  
 **ID errore:** BC30149  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Dichiara una routine con lo stesso nome e firma, come definito nell'interfaccia. Assicurarsi di includere almeno le `End Function` o `End Sub` istruzione.  
  
2.  Aggiungere un `Implements` alla fine della clausola il `Function` o `Sub` istruzione. Ad esempio:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
