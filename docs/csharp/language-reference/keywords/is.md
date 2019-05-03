---
title: is - Riferimenti per C#
ms.custom: seodec18
ms.date: 04/09/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 9fb57caeafde9db5759300d938a85f4abf4d05f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672459"
---
# <a name="is-c-reference"></a>is (Riferimenti per C#)

Controlla se un oggetto è compatibile con un determinato tipo o (a partire da C# 7.0) controlla un'espressione rispetto a un criterio.

## <a name="testing-for-type-compatibility"></a>Verifica della compatibilità del tipo

La parola chiave `is` valuta la compatibilità dei tipi in fase di esecuzione. Determina se un'istanza dell'oggetto o il risultato di un'espressione può essere convertito in un tipo specificato. Presenta la sintassi

```csharp
   expr is type
```

dove *expr* è un'espressione che restituisce un'istanza di un tipo e *type* è il nome del tipo in cui il risultato di *expr* deve essere convertito. L'istruzione `is` è `true` se *expr* è non Null e l'oggetto risultante dalla valutazione dell'espressione può essere convertito in *type*; in caso contrario, restituisce `false`.

Ad esempio, il codice seguente determina se `obj` può essere convertito in un'istanza di tipo `Person`:

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

L'istruzione `is` è true se:

- *expr* è un'istanza dello stesso tipo di *type*.

- *expr* è un'istanza di un tipo che deriva da *type*. In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.

- *expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*. Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione. Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.

- *expr* è un'istanza di un tipo che implementa l'interfaccia *type*.

Nell'esempio seguente viene illustrato che l'espressione `is` restituisce `true` per ognuna di queste conversioni.

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

La parola chiave `is` genera un avviso in fase di compilazione se è noto che l'espressione sarà sempre `true` o `false`. Considera solo le conversioni dei riferimenti, le conversioni boxing e unboxing; non considera le conversioni definite dall'utente o le conversioni definite dagli operatori [implicit](implicit.md) ed [explicit](explicit.md) di un tipo. Nell'esempio seguente vengono generati gli avvisi, poiché il risultato della conversione è noto in fase di compilazione. L'espressione `is` per le conversioni da `int` a `long` e `double` restituisce false, poiché queste conversioni vengono gestite dall'operatore [implicit](implicit.md).

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

`expr` non può essere un metodo anonimo o un'espressione lambda. Può essere una qualsiasi altra espressione che restituisce un valore. Nell'esempio seguente viene usato `is` per valutare il valore restituito di una chiamata al metodo.   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

A partire da C# 7.0, è possibile usare criteri di ricerca con il [criterio del tipo](#type) per scrivere codice più conciso che usa l'istruzione `is`.

## <a name="pattern-matching-with-is"></a>Criteri di ricerca con `is`

A partire da C# 7.0, le istruzioni `is` e [switch](../../../csharp/language-reference/keywords/switch.md) supportano i criteri di ricerca. La parola chiave `is` supporta i criteri seguenti:

- [Criterio del tipo](#type), che verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.

- [Criterio costante](#constant), che verifica se un'espressione restituisce un valore costante specificato.

- [Criterio var](#var), una corrispondenza che ha sempre esito positivo e associa il valore di un'espressione a una nuova variabile locale. 

### <a name="a-nametype-type-pattern"></a><a name="type" />Criterio del tipo

Quando si usa il criterio del tipo per eseguire i criteri di ricerca, `is` verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo. È una semplice estensione dell'istruzione `is` che consente la valutazione e la conversione concisa del tipo. Il formato generale del criterio del tipo è `is`:

```csharp
   expr is type varname 
```

dove *expr* è un'espressione che restituisce un'istanza di un tipo, *type* è il nome del tipo in cui il risultato di *expr* deve essere convertito e *varname* è l'oggetto in cui il risultato di *expr*deve essere convertito se il test `is` è `true`. 

L'espressione `is` è `true` se *expr* non è `null` e una delle condizioni seguenti è true:

- *expr* è un'istanza dello stesso tipo di *type*.

- *expr* è un'istanza di un tipo che deriva da *type*. In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.

- *expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*. Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione. Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.

- *expr* è un'istanza di un tipo che implementa l'interfaccia *type*.

A partire da C# 7.1, *expr* può avere un tipo in fase di compilazione definito da un parametro di tipo generico e dai relativi vincoli. 

Se *expr* è `true` e `is` viene usato con un'istruzione `if`, *varname* viene assegnato e ha un ambito locale solo all'interno dell'istruzione `if`.

Nell'esempio seguente viene usato il criterio del tipo `is` per specificare l'implementazione di un metodo <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> del tipo.

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

Senza criteri di ricerca, questo codice potrebbe essere scritto come segue. L'uso di criteri di ricerca del tipo produce codice più compatto e leggibile eliminando la necessità di verificare se il risultato di una conversione è un `null`.  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

Anche il criterio del tipo `is` produce codice più compatto quando determina il tipo di un tipo di valore. Nell'esempio seguente viene usato il criterio del tipo `is` per determinare se un oggetto è un'istanza `Person` o `Dog` prima di visualizzare il valore di una proprietà appropriata. 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

Il codice equivalente senza criteri di ricerca richiede un'assegnazione separata che include un cast esplicito.

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><a name="constant" /> Criterio costante

Quando si eseguono criteri di ricerca con il criterio costante, `is` verifica se un'espressione è uguale a una costante specificata. In C# 6 e versioni precedenti, il criterio costante è supportato per l'istruzione [switch](switch.md). A partire da C# 7.0 è supportato anche dall'istruzione `is`. La sintassi è la seguente:

```csharp
   expr is constant
```

dove *expr* è l'espressione da valutare e *constant* è il valore da testare. *constant* può essere una delle espressioni costanti seguenti: 

- Un valore letterale.

- Il nome di una variabile `const` dichiarata.

- Una costante di enumerazione.

L'espressione costante viene valutata nel modo seguente:

- Se *expr* e *constant* sono tipi integrali, l'operatore di uguaglianza C# determina se l'espressione restituisce `true` (ovvero, se `expr == constant`).

- In caso contrario, il valore dell'espressione è determinato da una chiamata al metodo [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) statico.  

Nell'esempio seguente vengono combinati i criteri di tipo e costante per verificare se un oggetto è un'istanza `Dice` e, in tal caso, per determinare se il valore di un tiro di dadi è 6.

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

Verifica che `null` possa essere eseguito usando il criterio costante. La parola chiave `null` è supportata dall'istruzione `is`. La sintassi è la seguente:

```csharp 
   expr is null
```

L'esempio seguente illustra un confronto di controlli `null`:

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <a name="var" /> Criterio var </a>

Il criterio `var` è applicabile a qualsiasi tipo o valore. Il valore di *expr* viene sempre assegnato a una variabile locale dello stesso tipo del tipo della fase di compilazione di *expr*. Il risultato dell'espressione `is` è sempre `true`. La sintassi è la seguente:

```csharp 
   expr is var varname
```

Nell'esempio seguente viene usato il criterio var per assegnare un'espressione a una variabile denominata `obj`. Viene quindi visualizzato il valore e il tipo di `obj`.

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
- [typeof](../../../csharp/language-reference/keywords/typeof.md)
- [as](../../../csharp/language-reference/keywords/as.md)
- [Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md)
