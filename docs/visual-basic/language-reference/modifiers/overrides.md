---
title: Overrides (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: dbcd0625cdbcd06affc495ca29972c6c183c10f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582099"
---
# <a name="overrides-visual-basic"></a>Overrides (Visual Basic)
Specifica che una proprietà o una routine esegue l'override di una proprietà o una routine con nome identico ereditata da una classe base.  
  
## <a name="remarks"></a>Note  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** È possibile usare `Overrides` solo in un'istruzione per la dichiarazione di proprietà o routine.  
  
-   **Modificatori combinati.** Non è possibile specificare `Overrides` insieme a `Shadows` o `Shared` nella stessa dichiarazione. Poiché un elemento che esegue l'override può essere implicitamente sottoposto a override, non è possibile combinare `Overridable` e `Overrides`.  
  
-   **Corrispondenza delle firme.** La firma di questa dichiarazione deve corrispondere esattamente il *firma* della proprietà o routine sottoposta a override. In altre parole, gli elenchi di parametri devono presentare lo stesso numero di parametri, nel medesimo ordine, e contenere gli stessi tipi di dati.  
  
     Oltre alla firma, la dichiarazione che esegue l'override deve anche corrispondere esattamente a quanto segue.  
  
    -   Livello di accesso  
  
    -   Tipo restituito, se disponibile  
  
-   **Firme generiche.** Nel caso di una routine generica la firma include il numero di parametri di tipo. La dichiarazione che esegue l'override, quindi, deve corrispondere alla versione della classe base anche in relazione a tali caratteristiche.  
  
-   **Corrispondenze aggiuntive.** Oltre a corrispondere alla firma della versione della classe base, la dichiarazione deve presentare anche le corrispondenze seguenti:  
  
    -   Modificatore a livello di accesso (ad esempio [pubblica](../../../visual-basic/language-reference/modifiers/public.md))  
  
    -   Meccanismo di passaggio di ogni parametro ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))  
  
    -   Elenchi di vincoli su ogni parametro di tipo di una routine generica  
  
-   **Shadowing e override.** Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali. Per altre informazioni, vedere [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Se si usa `Overrides`, il compilatore aggiunge implicitamente `Overloads` in modo che le API della libreria funzionino più facilmente con C#.  
  
 Il modificatore `Overrides` può essere usato nei contesti seguenti:  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)
