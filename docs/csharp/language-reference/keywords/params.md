---
title: Parola chiave params - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 772c8da879eeccbe484c631a47de7fe8a32ec8d2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633575"
---
# <a name="params-c-reference"></a>params (Riferimenti per C#)

Usando la parola chiave `params`, è possibile specificare un [parametro di metodo](method-parameters.md) che usa un numero variabile di argomenti.

È possibile inviare un elenco di argomenti separato da virgole del tipo specificato nella dichiarazione di parametri o una matrice di argomenti del tipo specificato. È anche possibile non inviare alcun argomento. Se non vengono inviati argomenti, la lunghezza dell'elenco `params` è zero.

In una dichiarazione di metodo non è possibile aggiungere altri parametri dopo la parola chiave `params` ed è consentito l'uso di una sola parola chiave `params`.

Il tipo dichiarato del parametro `params` deve essere una matrice unidimensionale, come illustrato nell'esempio seguente. In caso contrario, si verifica l'errore del compilatore [CS0225](../../misc/cs0225.md).

## <a name="example"></a>Esempio

Nell'esempio seguente vengono illustrati i vari modi in cui è possibile inviare argomenti al parametro `params`.

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Parametri dei metodi](method-parameters.md)
