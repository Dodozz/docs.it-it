---
title: Istruzione Module (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: a30b037b5a918f9b760ff0ab5b704dceb280d33f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980217"
---
# <a name="module-statement"></a>Istruzione Module
Dichiara il nome di un modulo e introduce la definizione delle variabili, proprietà, eventi e le procedure che comprende il modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Parti  
 `attributelist`  
 Facoltativo. Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Facoltativo. Può essere uno dei seguenti:  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Obbligatorio. Nome di questo modulo. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Facoltativo. Istruzioni che definiscono le variabili, proprietà, eventi, procedure e i tipi annidati di questo modulo.  
  
 `End Module`  
 Termina il `Module` definizione.  
  
## <a name="remarks"></a>Note  
 Oggetto `Module` istruzione definisce un tipo di riferimento disponibile in tutto lo spazio dei nomi. Oggetto *module* (talvolta chiamato un *modulo standard*) è simile a una classe, ma con alcune importanti differenze. Ogni modulo dispone esattamente di un'istanza e non devono essere creati o assegnati a una variabile. I moduli non supportano l'ereditarietà o implementare interfacce. Si noti che un modulo non è un *tipo* nel senso che è una classe o struttura, ovvero non è possibile dichiarare un elemento di programmazione per avere il tipo di dati di un modulo.  
  
 È possibile usare `Module` solo a livello di spazio dei nomi. Ciò significa che il *contesto della dichiarazione* per un modulo deve essere un file di origine o lo spazio dei nomi e non può essere una classe, struttura, modulo, interfaccia, routine o blocco. Non è possibile annidare un modulo in un altro modulo o in qualsiasi tipo. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Un modulo ha la stessa durata del programma. Poiché i relativi membri sono tutti `Shared`, hanno anche una durata pari a quella del programma.  
  
 Per impostazione predefinita i moduli [Friend](../../../visual-basic/language-reference/modifiers/friend.md) accesso. È possibile modificare i livelli di accesso con i modificatori di accesso. Per altre informazioni, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Tutti i membri di un modulo sono implicitamente `Shared`.  
  
## <a name="classes-and-modules"></a>Classi e moduli  
 Questi elementi presentano molte analogie, ma esistono alcune importanti differenze.  
  
-   **Terminology.** Le versioni precedenti di Visual Basic riconoscono due tipi di moduli: *classe moduli* (file CLS) e *moduli standard* (file con estensione BAS). La versione corrente chiama questi *classi* e *moduli*, rispettivamente.  
  
-   **Membri condivisi.** È possibile controllare se un membro di una classe è condivisa o membro di istanza.  
  
-   **Orientamento agli oggetti.** Le classi sono orientate a oggetti, ma non sono i moduli. È possibile creare istanze di classi perciò richiedere sola come oggetti. Per altre informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Regole  
  
-   **Modificatori.** Tutti i membri del modulo sono implicitamente [condiviso](../../../visual-basic/language-reference/modifiers/shared.md). Non è possibile usare il `Shared` parola chiave quando si dichiara un membro e non è possibile modificare lo stato condiviso tra i membri.  
  
-   **Ereditarietà.** Un modulo non può ereditare da qualsiasi tipo diverso da <xref:System.Object>, da cui tutti i moduli vengono ereditate. In particolare, un modulo non può ereditare da un altro.  
  
     Non è possibile usare la [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in una definizione di modulo, anche per specificare <xref:System.Object>.  
  
-   **Proprietà predefinita.** È possibile definire le proprietà predefinite in un modulo. Per altre informazioni, vedere [predefinito](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** All'interno di un modulo, è possibile dichiarare ogni membro con il proprio livello di accesso. Per impostazione predefinita i membri del modulo [pubbliche](../../../visual-basic/language-reference/modifiers/public.md) accedere, ad eccezione delle variabili e costanti, quale per impostazione predefinita ai [privati](../../../visual-basic/language-reference/modifiers/private.md) accesso. Quando un modulo, l'accesso è più limitato rispetto a uno dei relativi membri, il livello di accesso del modulo specificato ha la precedenza.  
  
-   **Ambito.** Un modulo incluso nell'ambito dello spazio dei nomi.  
  
     L'ambito di ogni membro del modulo è l'intero modulo. Si noti che vengono sottoposti a tutti i membri *promozione tipo*, in modo che l'ambito da innalzare di livello per lo spazio dei nomi che contiene il modulo. Per altre informazioni, vedere [promozione tipo](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Qualification.** È possibile avere più moduli in un progetto, ed è possibile dichiarare i membri con lo stesso nome in due o più moduli. Tuttavia, è necessario qualificare ogni riferimento a tale membro con il nome del modulo appropriato se il riferimento è esterna al modulo. Per altre informazioni, vedere [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Promozione tipo](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
