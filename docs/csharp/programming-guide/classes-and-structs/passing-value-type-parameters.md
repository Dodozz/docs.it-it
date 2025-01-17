---
title: Passaggio di parametri di tipo di valore - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
ms.openlocfilehash: ba693948bce91fa80f0c6cd73f2d5fc537e5f900
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423744"
---
# <a name="passing-value-type-parameters-c-programming-guide"></a>Passaggio di parametri di tipo di valore (Guida per programmatori C#)
Una variabile [di tipo valore](../../../csharp/language-reference/keywords/value-types.md) contiene direttamente i dati, mentre una variabile [di tipo riferimento](../../../csharp/language-reference/keywords/reference-types.md) contiene un riferimento ai dati. Quando si passa una variabile di tipo valore a un metodo per valore, si passa una copia della variabile al metodo. Tutte le modifiche al parametro apportate all'interno del metodo non hanno alcun effetto sui dati originali archiviati nella variabile di argomento. Se si vuole che il metodo chiamato modifichi il valore dell'argomento, è necessario passarlo per riferimento usando la parola chiave [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md). È inoltre possibile usare la parola chiave [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) per passare un parametro di valore per riferimento per evitare la copia, garantendo che il valore non verrà modificato. Per semplicità, negli esempi seguenti viene usato `ref`.  
  
## <a name="passing-value-types-by-value"></a>Passaggio di tipi di valore per valore  
 Nell'esempio seguente viene illustrato il passaggio di parametri di tipo valore per valore. La variabile `n` viene passata al metodo `SquareIt` per valore. Tutte le modifiche apportate all'interno del metodo non hanno alcun effetto sul valore originale della variabile.  
  
 [!code-csharp[csProgGuideParameters#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#3)]  
  
 La variabile `n` è un tipo valore. Contiene i propri dati, il valore `5`. Quando si richiama `SquareIt`, il contenuto di `n` viene copiato nel parametro `x`, che viene elevato al quadrato all'interno del metodo. In `Main`, tuttavia, il valore di `n` dopo la chiamata del metodo `SquareIt` rimane invariato. La modifica apportata all'interno del metodo ha effetto soltanto sulla variabile locale `x`.  
  
## <a name="passing-value-types-by-reference"></a>Passaggio di tipi di valore per riferimento  
 L'esempio seguente è identico a quello precedente, tranne per il fatto che l'argomento viene passato come parametro `ref`. Il valore dell'argomento sottostante, `n`, viene modificato quando si modifica `x` nel metodo.  
  
 [!code-csharp[csProgGuideParameters#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#4)]  
  
 Nell'esempio seguente non viene passato il valore di `n`, ma un riferimento a `n`. Il parametro `x` non è di tipo [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) ma è un riferimento a un valore `int`, in questo caso un riferimento a `n`. Di conseguenza, quando `x` viene elevato al quadrato all'interno del metodo, il valore effettivamente elevato al quadrato è quello a cui `x` fa riferimento, ovvero `n`.  
  
## <a name="swapping-value-types"></a>Scambio di tipi di valore  
 Un esempio comune di modifica dei valori degli argomenti è un metodo swap, dove si passano due variabili al metodo e il metodo scambia i relativi contenuti. È necessario passare argomenti al metodo swap per riferimento. In caso contrario, vengono scambiate le copie locali dei parametri all'interno del metodo e al metodo che esegue la chiamata non viene apportata alcuna modifica. L'esempio seguente scambia i valori integer.  
  
 [!code-csharp[csProgGuideParameters#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#5)]  
  
 Quando si chiama il metodo `SwapByRef`, usare nella chiamata la parole chiave `ref`, come mostrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideParameters#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Passaggio di parametri](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)
- [Passaggio di parametri di tipo di riferimento](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)
