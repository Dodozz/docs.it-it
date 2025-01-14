---
title: volatile - Riferimenti per C#
ms.custom: seodec18
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: 7200432780cb5a65bc5420b41c5dbd2e27a2c01f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633085"
---
# <a name="volatile-c-reference"></a>volatile (Riferimenti per C#)

La parola chiave `volatile` indica che un campo potrebbe essere modificato da più thread eseguiti contemporaneamente. Il compilatore, il sistema di runtime e anche l'hardware possono riordinare le letture e le scritture in posizioni di memoria per motivi di prestazioni. I campi dichiarati `volatile` non sono soggetti a queste ottimizzazioni. L'aggiunta del modificatore `volatile` garantisce che tutti thread osserveranno le scritture volatili eseguite da qualsiasi altro thread nell'ordine in cui sono state eseguite. Non c'è garanzia di un singolo ordinamento totale delle scritture volatili come osservato da tutti i thread di esecuzione.

La parola chiave `volatile` può essere applicata ai campi di questi tipi:

- Tipi di riferimento.
- Tipi di puntatore (in un contesto non sicuro). Si noti che sebbene il puntatore in sé possa essere volatile, non può esserlo l'oggetto a cui punta. In altre parole, non è possibile dichiarare un "puntatore a volatile".
- Tipi semplici come `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float` e `bool`.
- Tipo `enum` con uno di questi tipi di base: `byte`, `sbyte`, `short`, `ushort`, `int` o `uint`.
- Parametri di tipo generico noti come tipi di riferimento.
- <xref:System.IntPtr> e <xref:System.UIntPtr>.

Altri tipi, inclusi `double` e `long`, non possono essere contrassegnati come `volatile`, perché non è possibile garantire che le letture e le scritture in campi di questi tipi siano atomiche. Per proteggere l'accesso multithread a questi tipi di campi, usare i membri della classe <xref:System.Threading.Interlocked> o proteggere l'accesso usando l'istruzione [`lock`](lock-statement.md).

La parola chiave `volatile` può essere applicata solo a campi di un oggetto `class` o `struct`. Le variabili locali non possono essere dichiarate `volatile`.

## <a name="example"></a>Esempio

Nell'esempio riportato di seguito viene illustrato come dichiarare `volatile` una variabile di campo pubblico.

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

Nell'esempio seguente viene illustrato come un thread di lavoro o ausiliario può essere creato e usato per eseguire l'elaborazione in parallelo con quella del thread principale. Per altre informazioni sul multithreading, vedere [Threading gestito](../../../standard/threading/index.md).

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

Dopo aver aggiunto il modificatore `volatile` alla dichiarazione di `_shouldStop`, si otterranno sempre gli stessi risultati, analogamente all'estratto mostrato nel codice precedente. Tuttavia, senza il modificatore nel membro `_shouldStop`, il comportamento è imprevedibile. Il metodo `DoWork` può ottimizzare l'accesso ai membri, causando la lettura dei dati non aggiornati. A causa della natura della programmazione multithread, il numero di letture non aggiornate è imprevedibile. Esecuzioni diverse del programma produrranno risultati leggermente diversi.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Specifica del linguaggio C#: parola chiave volatile](../../../../_csharplang/spec/classes.md#volatile-fields)
- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Modificatori](modifiers.md)
- [Istruzione lock](lock-statement.md)
- <xref:System.Threading.Interlocked>
