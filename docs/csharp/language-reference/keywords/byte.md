---
title: byte - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: fe2ef272c77b1af3a5b5a7f5bf3efb4836edcf23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691528"
---
# <a name="byte-c-reference"></a>byte (Riferimenti per C#)

`byte` identifica un tipo integrale che archivia valori come indicato nella tabella seguente.  
  
|Tipo|Intervallo|Dimensione|Tipo .NET|  
|----------|-----------|----------|-------------------------|  
|`byte`|Da 0 a 255|Intero senza segno a 8 bit|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Valori letterali  

 È possibile dichiarare e inizializzare una variabile `byte` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `byte`, vale a dire se è minore di <xref:System.Byte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Byte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 201 rappresentati some valori letterali decimali, esadecimali o binari vengono convertiti in modo implicito da valori [int](../../../csharp/language-reference/keywords/int.md) a valori `byte`.    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario. I valori letterali decimali non hanno prefissi.

A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità. 
 - C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.
 - C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale. In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.

Di seguito sono riportati alcuni esempi.

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a>Conversioni  
 È disponibile una conversione implicita predefinita da `byte` a [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Non è possibile convertire in modo implicito i tipi numerici non letterali di dimensioni di archiviazione maggiori di `byte`. Per altre informazioni sulle dimensioni di archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md). Considerare, ad esempio, le due variabili `byte` seguenti, `x` e `y`:  
  
```csharp  
byte x = 10, y = 20;  
```  
  
 L'istruzione di assegnazione seguente genererà un errore di compilazione, poiché l'espressione aritmetica a destra dell'operatore di assegnazione restituisce `int` per impostazione predefinita.  
  
```csharp  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 Per risolvere il problema, usare un cast:  
  
```csharp  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 È possibile tuttavia usare le istruzioni seguenti dove la variabile di destinazione ha dimensioni uguali o superiori di archiviazione:  
  
```csharp  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Non è disponibile nessuna conversione implicita dai tipi a virgola mobile a `byte`. Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:  
  
```csharp  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 Quando si chiamano metodi di overload, è necessario usare un cast. Considerare, ad esempio, i metodi seguenti di overload che usano i parametri `byte` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 L'uso del cast `byte` garantisce che verrà chiamato il tipo corretto, ad esempio:  
  
```csharp  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).  
  
 Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Byte>
- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
- [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md)
- [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
