---
title: Come inizializzare un dizionario con un inizializzatore di insieme - Guida per programmatori C#
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: bab2c4c996f7780cec572d58eb572a90aeea592a
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267675"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Come inizializzare un dizionario con un inizializzatore di insieme (Guida per programmatori C#)

Un oggetto <xref:System.Collections.Generic.Dictionary%602> contiene una raccolta di coppie chiave-valore. Il relativo metodo <xref:System.Collections.Generic.Dictionary%602.Add*> accetta due parametri, uno per la chiave e uno per il valore. Un modo per inizializzare un oggetto <xref:System.Collections.Generic.Dictionary%602> o qualsiasi raccolta il cui metodo `Add` accetta più parametri, consiste nel racchiudere ogni set di parametri tra parentesi graffe, come illustrato nell'esempio seguente. Un'altra opzione consiste nell'usare un inizializzatore di indice, come mostrato nell'esempio seguente.

## <a name="example"></a>Esempio

Nell'esempio di codice seguente, viene inizializzato un oggetto <xref:System.Collections.Generic.Dictionary%602> con istanze di tipo `StudentName`.  La prima inizializzazione usa il metodo `Add` con due argomenti. Il compilatore genera una chiamata a `Add` per ognuna delle coppie di chiavi `int` e valori `StudentName`. Il secondo usa un metodo di lettura pubblica / indicizzatore di scrittura della classe `Dictionary`:

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

Si noti che vi sono due coppie di parentesi graffe in ogni elemento della raccolta nella prima dichiarazione. Le parentesi più interne racchiudono l'inizializzatore di oggetto per `StudentName`, quelle più esterne racchiudono l'inizializzatore per la coppia chiave/valore che verrà aggiunta a `students` <xref:System.Collections.Generic.Dictionary%602>. Infine, tutto l'inizializzatore di insieme per il dizionario è racchiuso tra parentesi graffe. Durante la seconda inizializzazione, il lato sinistro dell'assegnazione è la chiave e il lato destro è il valore, usando un inizializzatore di oggetto per `StudentName`.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
