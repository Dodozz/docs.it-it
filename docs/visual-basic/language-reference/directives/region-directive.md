---
title: '#Direttiva Region (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: db8063cf06ad0735bb4d9290c60548f7ff9af217
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611943"
---
# <a name="region-directive"></a>Direttiva #Region
Comprime e nasconde sezioni di codice in file di Visual Basic.  
  
## <a name="syntax"></a>Sintassi  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`identifier_string`|Obbligatorio. Stringa che funge da titolo di un'area quando viene compressa. Le aree sono compresse per impostazione predefinita.|  
|`#End Region`|Termina il blocco `#Region`.|  
  
## <a name="remarks"></a>Note  
 Usare la direttiva `#Region` per specificare un blocco di codice da espandere o comprimere durante l'uso della funzionalità di struttura dell'editor di Visual Studio Code. È possibile inserire, oppure *annidare*, aree all'interno di altre aree per raggruppare aree simili.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usata la direttiva `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Struttura](/visualstudio/ide/outlining)
- [Procedura: Comprimere e nascondere sezioni di codice](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
