---
title: Expression Trees
description: Informazioni sugli alberi delle espressioni in .NET Core e su come usarli per rappresentare il codice sotto forma di strutture che è possibile esaminare, modificare ed eseguire.
ms.date: 06/20/2016
ms.assetid: aceb4719-0d5a-4b19-b01f-b51063bcc54f
ms.openlocfilehash: 56509f1eb0f2bdca8a8f3a51df958d42e95af6f4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50190736"
---
# <a name="expression-trees"></a>Expression Trees

Se si è usato LINQ, si ha esperienza con una ricca libreria in cui i tipi `Func` fanno parte del set di API. (Se non si ha familiarità con LINQ, è consigliabile prima leggere l'[esercitazione LINQ](linq/index.md) e l'esercitazione sulle [espressioni lambda](lambda-expressions.md).) Gli *alberi delle espressioni* offrono maggiore interazione con gli argomenti che sono funzioni.

Scrivere gli argomenti della funzione, in genere usando le espressioni lambda, quando si creano query LINQ. In una tipica query LINQ, tali argomenti delle funzioni vengono trasformati in un delegato che viene creato dal compilatore. 

Quando si vuole usare una maggiore interazione, è necessario usare gli *alberi delle espressioni*.
Gli alberi delle espressioni rappresentano il codice come una struttura che è possibile esaminare, modificare o eseguire. Questi strumenti offrono la possibilità di modificare il codice in fase di esecuzione. È possibile scrivere codice che esamina gli algoritmi in esecuzione o inserisce nuove funzionalità. Negli scenari più avanzati, è possibile modificare gli algoritmi in esecuzione e anche convertire espressioni C# in un altro formato per l'esecuzione in un altro ambiente.

Si è probabilmente già scritto codice che usa gli alberi delle espressioni. Le API LINQ di Entity Framework accettano gli alberi delle espressioni come argomenti per il criterio di espressione di query LINQ.
Ciò consente a [Entity Framework](/ef/) di convertire la query scritta in C# in SQL che viene eseguito nel motore di database. Un altro esempio è [Moq](https://github.com/Moq/moq), che è un framework di simulazione tra i più diffusi per .NET.

Le sezioni rimanenti di questa esercitazione illustreranno che cosa sono gli alberi delle espressioni, esamineranno le classi di framework che supportano gli alberi delle espressioni e spiegheranno come lavorare con gli alberi delle espressioni. Si apprenderà come leggere gli alberi delle espressioni, come creare alberi delle espressioni, come creare alberi delle espressioni modificati e come eseguire il codice rappresentato dagli alberi delle espressioni. Al termine, sarà possibile usare queste strutture per creare algoritmi adattivi completi.

1. [Nozioni di base sugli alberi delle espressioni](expression-trees-explained.md)

    Informazioni sulla struttura e sui concetti correlati agli *alberi delle espressioni*.
    
2. [Tipi di framework che supportano alberi delle espressioni](expression-classes.md)
    
    Informazioni sulle strutture e le classi che definiscono e modificano gli alberi delle espressioni.
    
3. [Esecuzione di espressioni](expression-trees-execution.md)

    Informazioni su come convertire un albero delle espressioni rappresentato come un'espressione lambda in un delegato ed eseguire il delegato risultante.

4. [Interpretazione di espressioni](expression-trees-interpreting.md)

    Informazioni su come attraversare ed esaminare gli *alberi delle espressioni* per comprendere quale codice rappresenta l'albero delle espressioni.

5. [Creazione di espressioni](expression-trees-building.md)

    Informazioni su come costruire i nodi per un albero delle espressioni e creare alberi delle espressioni.

6. [Conversione di espressioni](expression-trees-translating.md)

    Informazioni su come creare una copia modificata di un albero delle espressioni o convertire un albero delle espressioni in un formato diverso.

7. [Conclusioni](expression-trees-summary.md)

    Esaminare le informazioni sugli alberi delle espressioni.
    
