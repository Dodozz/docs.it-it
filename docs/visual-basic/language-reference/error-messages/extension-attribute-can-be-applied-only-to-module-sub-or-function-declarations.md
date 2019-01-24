---
title: '&#39;Estensione di&#39; attributo può essere applicato solo a &#39;modulo&#39;, &#39;Sub&#39;, o &#39;funzione&#39; dichiarazioni'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: fabd602f31a362fe33954253d565e86a065e0a83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718234"
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>&#39;Estensione di&#39; attributo può essere applicato solo a &#39;modulo&#39;, &#39;Sub&#39;, o &#39;funzione&#39; dichiarazioni
L'unico modo per estendere un tipo di dati in Visual Basic consiste nel definire un metodo di estensione all'interno di un modulo standard. Il metodo di estensione può essere un' `Sub` routine o un `Function` procedure. Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione `<Extension()>`, dal <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> dello spazio dei nomi. Facoltativamente, un modulo che contiene un metodo di estensione può essere contrassegnato nello stesso modo. Nessun altro uso dell'attributo di estensione è valido.  
  
 **ID errore:** BC36550  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere l'attributo di estensione.  
  
-   Riprogettare l'estensione di un metodo, definito in un modulo contenitore.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce una `Print` metodo per il `String` tipo di dati.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica degli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)
