---
title: Matrici multidimensionali - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: d5663062815f0c85772aa0e30f5edeac654431b8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242217"
---
# <a name="multidimensional-arrays-c-programming-guide"></a>Matrici multidimensionali (Guida per programmatori C#)

Le matrici possono avere più di una dimensione. La dichiarazione seguente, ad esempio, crea una matrice bidimensionale di quattro righe e due colonne.  
  
 [!code-csharp[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 La dichiarazione seguente crea una matrice a tre dimensioni: 4, 2 e 3.  
  
 [!code-csharp[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>Inizializzazione di una matrice

 È possibile inizializzare la matrice al momento della dichiarazione, come illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 È possibile anche inizializzare la matrice senza specificarne il numero di dimensioni.  
  
 [!code-csharp[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 Se si sceglie di dichiarare una variabile di matrice senza inizializzazione, è necessario usare l'operatore `new` per assegnare una matrice alla variabile. L'utilizzo di `new` è illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 Nell'esempio seguente viene assegnato un valore a un elemento specifico della matrice.  
  
 [!code-csharp[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 Analogamente, nell'esempio seguente viene ottenuto il valore di un elemento specifico della matrice, che viene assegnato alla variabile `elementValue`.  
  
 [!code-csharp[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 Nell'esempio di codice seguente, gli elementi della matrice vengono inizializzati in base ai valori predefiniti (ad eccezione delle matrici di matrici).  
  
 [!code-csharp[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Matrici](../../../csharp/programming-guide/arrays/index.md)  
- [Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [Matrici irregolari](../../../csharp/programming-guide/arrays/jagged-arrays.md)
