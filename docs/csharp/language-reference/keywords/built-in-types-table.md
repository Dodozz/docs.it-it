---
title: Tabella dei tipi predefiniti - Riferimenti per C#
ms.custom: seodec18
description: Parole chiave per i tipi C# incorporati
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 4a54059f288a432cbaf904626cabf4f7bcba7209
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424379"
---
# <a name="built-in-types-table-c-reference"></a>Tabella dei tipi incorporati (Riferimenti per C#)

La tabella seguente include le parole chiave per i tipi predefiniti di C#, che rappresentano gli alias dei tipi predefiniti nello spazio dei nomi <xref:System>.  
  
|Tipo C#|Tipo .NET|  
|--------------|-------------------------|  
|[bool](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[byte](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[sbyte](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[char](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[decimal](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[double](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[float](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[int](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[uint](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[long](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[ulong](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[object](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[short](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[ushort](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[string](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a>Osservazioni

Tutti i tipi nella tabella, ad eccezione di `object` e `string`, sono detti tipi semplici.  
  
Le parole chiave per i tipi C# e i relativi alias sono intercambiabili. Ad esempio, è possibile dichiarare una variabile integer, usando le seguenti dichiarazioni:  

```csharp
int x = 123;
System.Int32 y = 123;
```

Usare l'operatore [typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator) per ottenere l'istanza <xref:System.Type?displayProperty=nameWithType> che rappresenta il tipo specificato:

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tipi valore](value-types.md)
- [Tipi riferimento](reference-types.md)
- [Tabella dei valori predefiniti](default-values-table.md)
- [dynamic](dynamic.md)
