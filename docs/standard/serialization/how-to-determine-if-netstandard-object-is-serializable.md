---
title: Come determinare se un oggetto .NET Standard è serializzabile
description: Viene illustrato come determinare se un tipo .NET Standard può essere serializzato in fase di esecuzione.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018757"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Come determinare se un oggetto .NET Standard è serializzabile

.NET Standard è una specifica che definisce i tipi e membri che devono essere presenti nelle specifiche implementazioni .NET conformi a tale versione dello standard. Tuttavia, .NET Standard non definisce se un tipo è serializzabile. I tipi definiti nella libreria .NET Standard non siano contrassegnati con il <xref:System.SerializableAttribute> attributo. Al contrario, le implementazioni di .NET specifiche, ad esempio .NET Framework e .NET Core, sono gratuite determinare se un determinato tipo è serializzabile. 

Se è stata sviluppata una libreria destinata a .NET Standard, la libreria può essere utilizzata da qualsiasi implementazione di .NET che supporta .NET Standard. Ciò significa che è possibile sapere in anticipo se un determinato tipo è serializzabile. è solo possibile determinare se è serializzabile in fase di esecuzione.

È possibile determinare se un oggetto serializzabile in fase di esecuzione eseguendo il recupero del valore dei <xref:System.Type.IsSerializable> proprietà di un <xref:System.Type> oggetto che rappresenta il tipo dell'oggetto. Nell'esempio seguente fornisce un'implementazione. Definisce un `IsSerializable(Object)` metodo di estensione che indica se qualsiasi <xref:System.Object> istanza può essere serializzata.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

È quindi possibile passare qualsiasi oggetto al metodo per determinare se può essere serializzato e deserializzato nell'implementazione .NET corrente, come illustrato nell'esempio seguente:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>Vedere anche

- [Serializzazione binaria](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
