---
title: Aggiornare le interfacce in modo sicuro con i membri dell'interfaccia predefiniti in C#
description: Questa esercitazione avanzata esplora come sia possibile aggiungere in modo sicuro nuove funzionalità alle definizioni di interfaccia esistenti senza interrompere tutte le classi e gli struct che implementano tale interfaccia.
ms.date: 05/06/2019
ms.custom: mvc
ms.openlocfilehash: 2daa40ead5902454c6d45390233e1491fe6d369b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877911"
---
# <a name="tutorial-update-interfaces-with-default-interface-members-in-c-80"></a>Esercitazione: Aggiornare le interfacce con i membri di interfaccia predefiniti in C# 8.0

A partire da C# 8.0 su .NET Core 3.0 è possibile definire un'implementazione quando si dichiara un membro di un'interfaccia. Lo scenario più comune consiste nell'aggiunta sicura di membri a un'interfaccia già rilasciata e usata da innumerevoli client.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
> * Estendere le interfacce in modo sicuro aggiungendo metodi con implementazioni.
> * Creare implementazioni con parametri per una maggiore flessibilità.
> * Abilitare gli implementatori per fornire un'implementazione più specifica sotto forma di override.

## <a name="prerequisites"></a>Prerequisiti

Sarà necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore di anteprima di C# 8.0. Il compilatore di anteprima di C# 8.0 è disponibile a partire [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o dalla versione più recente del [SDK dell'anteprima di .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0). I membri di interfaccia predefiniti sono disponibili a partire dall'anteprima 4 di .NET Core 3.0.

## <a name="scenario-overview"></a>Panoramica dello scenario

Questa esercitazione inizia con la versione 1 di una raccolta di relazioni con i clienti. L'applicazione di base è disponibile nel [repository di esempi in GitHub](https://github.com/dotnet/samples/tree/master/csharp/tutorials/default-interface-members-versions/starter/customer-relationship). L'azienda che ha realizzato questa raccolta intende farla adottare dai clienti con le applicazioni esistenti. Agli utenti della raccolta vengono fornite definizioni di interfaccia minime da implementare. Ecco la definizione di interfaccia per un cliente:

[!code-csharp[InitialCustomerInterface](~/samples/csharp/tutorials/default-interface-members-versions/starter/customer-relationship/ICustomer.cs?name=SnippetICustomerVersion1)]

Viene definita una seconda interfaccia che rappresenta un ordine:

[!code-csharp[InitialOrderInterface](~/samples/csharp/tutorials/default-interface-members-versions/starter/customer-relationship/IOrder.cs?name=SnippetIorderVersion1)]

Da queste interfacce il team potrebbe realizzare una raccolta per consentire agli utenti di creare un'esperienza migliore per i clienti. L'obiettivo è consolidare le relazioni con i clienti esistenti e migliorare quelle con i nuovi clienti.

Ora è il momento di aggiornare la raccolta per la versione successiva. Una delle funzionalità richieste è la definizione di uno sconto fedeltà per i clienti con molti ordini. Questo nuovo sconto fedeltà viene applicato ogni volta che un cliente effettua un ordine. Lo sconto specifico è una proprietà di ogni singolo cliente. Ogni implementazione di ICustomer può impostare ruoli diversi per lo sconto fedeltà. 

Il modo più naturale per aggiungere questa funzionalità consiste nell'ottimizzare l'interfaccia `ICustomer` con un metodo per applicare qualsiasi sconto fedeltà. Questo suggerimento di progettazione genera preoccupazione tra gli sviluppatori esperti perché si ritiene che, una volta rilasciate, le interfacce non siano più modificabili a meno di generare errori. In C# 8.0 sono state aggiunte *implementazioni di interfaccia predefinite* per l'aggiornamento delle interfacce. Gli autori della raccolta possono aggiungere nuovi membri all'interfaccia a cui applicare un'implementazione predefinita.

Le implementazioni di interfaccia predefinite consentono agli sviluppatori di aggiornare un'interfaccia, ma possono comunque essere sottoposte a override da qualsiasi implementatore. Gli utenti della raccolta possono accettare l'implementazione predefinita come modifica che non causa interruzioni. Se le regole business sono diverse, possono eseguire l'override.

## <a name="upgrade-with-default-interface-members"></a>Aggiornare con membri di interfaccia predefiniti

Il team concorda sull'implementazione predefinita più probabile: uno sconto fedeltà per i clienti.

L'aggiornamento dovrà fornire la funzionalità per impostare due proprietà: il numero di ordini necessario per avere diritto allo sconto e la percentuale dello sconto. Questo scenario è perfetto per i membri di interfaccia predefiniti. È possibile aggiungere un metodo all'interfaccia ICustomer e fornire l'implementazione più probabile. Tutte le implementazioni esistenti e quelle nuove possono usare l'implementazione predefinita o una personalizzata.

Prima di tutto aggiungere il nuovo metodo all'implementazione:

[!code-csharp[InitialOrderInterface](~/samples/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/ICustomer.cs?name=SnippetLoyaltyDiscountVersionOne)]

L'autore della raccolta scrive un primo test per verificare l'implementazione:

[!code-csharp[TestDefaultImplementation](~/samples/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/Program.cs?name=SnippetTestDefaultImplementation)]

Si noti la parte seguente del test:

[!code-csharp[TestDefaultImplementation](~/samples/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/Program.cs?name=SnippetHighlightCast)]

Il cast da `SampleCustomer` a `ICustomer` è necessario. La classe `SampleCustomer` non deve necessariamente fornire un'implementazione per `ComputeLoyaltyDiscount`, perché viene fornita dall'interfaccia `ICustomer`. Tuttavia, la classe `SampleCustomer` non eredita i membri dalle relative interfacce. Questa regola non è cambiata. Per chiamare qualsiasi metodo dichiarato e implementato nell'interfaccia, la variabile deve essere il tipo dell'interfaccia, in questo esempio `ICustomer`.

## <a name="provide-parameterization"></a>Fornire la parametrizzazione

Anche se si tratta di un buon inizio, l'implementazione predefinita è troppo restrittiva. Molti utenti di questo sistema potrebbero scegliere soglie diverse per il numero di acquisti, una durata diversa dell'iscrizione o una percentuale di sconto diversa. È possibile fornire un'esperienza di aggiornamento migliore per più clienti offrendo la possibilità di impostare questi parametri. A questo scopo, aggiungere un metodo statico che imposta questi tre parametri che controllano l'implementazione predefinita:

[!code-csharp[VersionTwoImplementation](~/samples/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/ICustomer.cs?name=SnippetLoyaltyDiscountVersionTwo)]

In questo piccolo frammento di codice sono visibili molte nuove funzionalità del linguaggio. Le interfacce possono ora includere membri statici, tra cui campi e metodi. Sono inoltre abilitati diversi modificatori di accesso. I campi aggiuntivi sono privati, mentre il nuovo metodo è pubblico. Per i membri dell'interfaccia è consentito qualsiasi modificatore.

Per le applicazioni in cui si usa la formula generale per calcolare lo sconto fedeltà, ma con parametri diversi, non è necessario fornire un'implementazione personalizzata perché è possibile impostare gli argomenti tramite un metodo statico. Il codice seguente imposta ad esempio un "apprezzamento del cliente" che premia qualsiasi cliente che si sia iscritto da più di un mese:

[!code-csharp[SetLoyaltyThresholds](~/samples/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/Program.cs?name=SnippetSetLoyaltyThresholds)]

## <a name="extend-the-default-implementation"></a>Estendere l'implementazione predefinita

Il codice aggiunto finora offre un'implementazione utile per gli scenari in cui gli utenti vogliono qualcosa di simile all'implementazione predefinita o per fornire un set non correlato di regole. Per una funzionalità finale, verrà eseguito il refactoring del codice per abilitare scenari in cui gli utenti potrebbero scegliere di sviluppare ulteriormente l'implementazione predefinita. 

Si supponga ad esempio che una startup voglia attirare nuovi clienti. Offre uno sconto del 50% sul primo ordine di un nuovo cliente. Altrimenti, i clienti esistenti ottengono lo sconto standard. L'autore della raccolta deve trasferire l'implementazione predefinita in un metodo `protected static` in modo che qualsiasi classe che implementi questa interfaccia possa riutilizzare il codice nella propria implementazione. L'implementazione predefinita del membro di interfaccia chiama anche questo metodo predefinito:

[!code-csharp[VersionTwoImplementation](~/samples/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/ICustomer.cs?name=SnippetFinalVersion)]

In un'implementazione di una classe che implementa questa interfaccia, l'override può chiamare il metodo helper statico ed estendere questa logica per fornire lo sconto "nuovo cliente":

[!code-csharp[VersionTwoImplementation](~/samples/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/SampleCustomer.cs?name=SnippetOverrideAndExtend)]

L'intero codice completato è disponibile nel [repository di esempi in GitHub]. È anche possibile ottenere l'applicazione di base nel [repository di esempi in GitHub](https://github.com/dotnet/samples/tree/master/csharp/tutorials/default-interface-members-versions/finished/customer-relationship).

Queste nuove funzionalità implicano che le interfacce possono essere aggiornate in modo sicuro quando è disponibile un'implementazione predefinita ragionevole per questi nuovi membri. Progettare con attenzione le interfacce per esprimere singole idee funzionali che possono essere implementate da più classi. In questo modo è più facile aggiornare le definizioni di queste interfacce quando vengono individuati nuovi requisiti per la stessa idea funzionale.
