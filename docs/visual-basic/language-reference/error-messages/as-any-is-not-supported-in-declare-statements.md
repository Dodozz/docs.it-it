---
title: "'As Any' non è supportato nelle istruzioni 'Declare'"
ms.date: 07/20/2015
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords:
- BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
ms.openlocfilehash: 3593f238c72cbcce911c72e42552d6a75188b628
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935330"
---
# <a name="as-any-is-not-supported-in-declare-statements"></a>'As Any' non è supportato nelle istruzioni 'Declare'
Il `Any` tipo di dati è stato usato con `Declare` istruzioni in Visual Basic 6.0 e versioni precedenti per consentire l'uso di argomenti che può contenere qualsiasi tipo di dati. Visual Basic supporta l'overload, tuttavia e la imposta come in questo caso il `Any` obsoleto del tipo di dati.  
  
 **ID errore:** BC30828  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Dichiarare i parametri del tipo specifico da usare; Per esempio.  
  
     [!code-vb[VbVbalrStatements#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#95)]  
  
2. Usare la <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributo per specificare `As Any` quando `Void*` è previsto per la routine chiamata.  
  
     [!code-vb[VbVbalrStatements#96](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class5.vb#96)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Procedura dettagliata: Chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Creazione di prototipi nel codice gestito](../../../framework/interop/creating-prototypes-in-managed-code.md)
