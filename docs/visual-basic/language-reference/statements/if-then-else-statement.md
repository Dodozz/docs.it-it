---
title: Istruzione If...Then...Else (Visual Basic) |
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: d91a913d515f36a6b974850bc30079b000a919b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61637754"
---
# <a name="ifthenelse-statement-visual-basic"></a>Istruzione If...Then...Else (Visual Basic) |
Esegue un gruppo di istruzioni in base a determinate condizioni, a seconda del valore di un'espressione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
' Multiline syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  

## <a name="quick-links-to-example-code"></a>Collegamenti rapidi al codice di esempio

Questo articolo include diversi esempi che illustrano utilizzi del `If`... `Then`... `Else` istruzione:

* [Esempio di sintassi a più righe](#multi-line)
* [Esempio di sintassi annidati](#nested)
* [Esempio di sintassi a riga singola](#single-line)

## <a name="parts"></a>Parti  
 `condition`  
 Obbligatorio. espressione. Deve restituire `True` oppure `False`, o a un tipo di dati che è implicitamente convertibile in `Boolean`.  
  
 Se l'espressione è un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variabile che restituisca [Nothing](../../../visual-basic/language-reference/nothing.md), la condizione viene considerata come se l'espressione è `False` e il `Else` blocco viene eseguito.  
  
 `Then`  
 Obbligatorio nella sintassi a riga singola; facoltativo nella sintassi a più righe.  
  
 `statements`  
 Facoltativo. Uno o più istruzioni che seguono `If`... `Then` che vengono eseguite se `condition` restituisce `True`.  
  
 `elseifcondition`  
 Obbligatorio se `ElseIf` è presente. espressione. Deve restituire `True` oppure `False`, o a un tipo di dati che è implicitamente convertibile in `Boolean`.  
  
 `elseifstatements`  
 Facoltativo. Uno o più istruzioni che seguono `ElseIf`... `Then` che vengono eseguite se `elseifcondition` restituisce `True`.  
  
 `elsestatements`  
 Facoltativo. Una o più istruzioni che vengono eseguite se no precedente `condition` oppure `elseifcondition` espressione viene valutata `True`.  
  
 `End If`  
 Termina la versione su più righe di `If`... `Then`... `Else` blocco.  
  
## <a name="remarks"></a>Note  
  
### <a name="multiline-syntax"></a>Sintassi su più righe  
 Quando un `If`... `Then`... `Else` viene rilevata un'istruzione, `condition` viene eseguito il test. Se `condition` viene `True`, le istruzioni che seguono `Then` vengono eseguite. Se `condition` viene `False`, ognuna `ElseIf` istruzione (se presente) viene valutata in ordine. Quando un `True` `elseifcondition` viene trovato, le istruzioni che seguono immediatamente associato `ElseIf` vengono eseguite. Se nessun `elseifcondition` restituisca `True`, o se sono presenti alcun `ElseIf` istruzioni, le istruzioni che seguono `Else` vengono eseguite. Dopo l'esecuzione di istruzioni che seguono `Then`, `ElseIf`, o `Else`, l'esecuzione continua con l'istruzione che segue `End If`.  
  
 Il `ElseIf` e `Else` clausole sono entrambi facoltativi. È possibile specificare qualsiasi numero `ElseIf` clausole come si desidera che un `If`... `Then`... `Else` istruzione, ma non `ElseIf` clausola può apparire dopo un `Else` clausola. `If`... `Then`... `Else` possono essere annidate all'interno di altro.  
  
 Nella sintassi a più righe, il `If` istruzione deve essere l'unica istruzione nella prima riga. Il `ElseIf`, `Else`, e `End If` istruzioni possono essere precedute solo da un'etichetta di riga. Il `If`... `Then`... `Else` blocco deve terminare con un `End If` istruzione.  
  
> [!TIP]
>  Il [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) potrebbe essere più utile quando si valuta una singola espressione che dispone di diversi valori possibili.  
  
### <a name="single-line-syntax"></a>Sintassi a riga singola  
 È possibile usare la sintassi a riga singola per una singola condizione con il codice da eseguire se è true. Tuttavia, la sintassi di più righe offre maggiore flessibilità e struttura ed è più facile da leggere, gestire ed eseguire il debug.  
  
 Di seguito il `Then` parola chiave viene esaminato per determinare se un'istruzione è a linea singola `If`. Se diverso da un commento viene visualizzato dopo `Then` sulla stessa riga, l'istruzione viene considerato come una riga singola `If` istruzione. Se `Then` non è presente, deve essere l'inizio di un'istruzione `If`... `Then`... `Else`.  
  
 Nella sintassi a riga singola, è possibile avere più istruzioni eseguite come risultato di un `If`... `Then` delle decisioni. Tutte le istruzioni devono essere nella stessa riga ed essere separate dai due punti.  

## <a name="multiline-syntax-example"></a>Esempio di sintassi a più righe

<a name="multi-line"></a>
 
 Nell'esempio seguente viene illustrato l'utilizzo della sintassi di più righe di `If`... `Then`... `Else` istruzione.  
  
 [!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Esempio di sintassi annidati

<a name="nested"></a>

 L'esempio seguente contiene nidificata `If`... `Then`... `Else` istruzioni.  
  
 [!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Esempio di sintassi a riga singola
  
<a name="single-line"></a> Nell'esempio seguente viene illustrato l'utilizzo della sintassi a riga singola.  
  
 [!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Istruzione Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Strutture decisionali](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Operatore If](../../../visual-basic/language-reference/operators/if-operator.md)
