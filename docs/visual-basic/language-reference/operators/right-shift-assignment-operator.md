---
title: '>>Operatore = (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: 0ea1e03168da12564f148f525af977f29a43bec8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265285"
---
# <a name="-operator-visual-basic"></a>Operatore >>= (Visual Basic)
Esegue uno scorrimento aritmetico a destra del valore di una variabile o proprietà e assegna il risultato alla variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Variabile o una proprietà di un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obbligatorio. Espressione numerica di un tipo di dati che si amplia in `Integer`.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `>>=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Il `>>=` operatore esegue prima di tutto uno scorrimento aritmetico a destra sul valore della variabile o proprietà. L'operatore assegna il risultato dell'operazione alla variabile o proprietà.  
  
 Aritmetici non sono circolari, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità. In uno scorrimento aritmetico a destra, i bit spostati oltre la posizione del bit più a destra vengono ignorati e il bit più a sinistra viene propagato nelle posizioni dei bit liberate a sinistra. Questo significa che se `variableorproperty` ha un valore negativo, le posizioni vuote sono impostate su uno. Se `variableorproperty` è positivo, oppure se il tipo di dati è un tipo senza segno, le posizioni vuote vengono impostate su zero.  
  
## <a name="overloading"></a>Overload  
 Il [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `>>` operatore influisce sul comportamento del `>>=` operatore. Se il codice usi `>>=` in una classe o struttura che esegue l'overload `>>`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `>>=` operatore per spostare lo schema di bit di un `Integer` variabile di verso destra la quantità specificata e assegna il risultato alla variabile.  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Operatore >>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori di spostamento bit](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
