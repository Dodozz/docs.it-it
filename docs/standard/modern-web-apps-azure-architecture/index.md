---
title: Progettare applicazioni Web moderne con ASP.NET Core e Azure
description: Una guida che offre linee guida end-to-end sulla compilazione di applicazioni Web monolitiche usando ASP.NET Core e Azure.
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 0b29a407ae18f3ce0c7499c75ee3c888296102c2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639315"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a>Progettare applicazioni Web moderne con ASP.NET Core e Azure

![Immagine della copertina della guida Progettare applicazioni Web moderne.](./media/index/web-application-guide-cover-image.png)

PUBBLICATO DA

Microsoft Developer Division, team dei prodotti .NET e Visual Studio

Una divisione di Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2019 Microsoft Corporation

Tutti i diritti sono riservati. Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.

Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore. I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.

Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi. Nessuna associazione o connessione reale è intenzionale o può essere presupposta.

Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo https://www.microsoft.com sono marchi delle società del gruppo Microsoft.

Mac e macOS sono marchi registrati di Apple Inc.

Il logo Docker con la balena è un marchio registrato di Docker, Inc. Usato su autorizzazione.

Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.

Autore:

> **Steve "ardalis" Smith** - Software Architect e Trainer - [Ardalis.com](https://ardalis.com)

Editor:

> **Maira Wenzel**

## <a name="introduction"></a>Introduzione

.NET Core e ASP.NET Core offrono diversi vantaggi rispetto allo sviluppo .NET tradizionale. È consigliabile usare .NET Core per le applicazioni server se alcuni o tutti gli aspetti seguenti sono importanti per il successo dell'applicazione:

- Supporto multipiattaforma.

- Uso di microservizi.

- Uso di contenitori Docker.

- Requisiti di scalabilità e prestazioni elevate.

- Controllo delle versioni side-by-side di .NET in base all'applicazione nello stesso server.

Le applicazioni .NET tradizionali possono supportare e supportano molti di questi requisiti, ma ASP.NET Core e .NET Core sono stati ottimizzati per offrire supporto migliorato per gli scenari elencati sopra.

Sempre più organizzazioni scelgono di ospitare le proprie applicazioni Web nel cloud usando servizi come Microsoft Azure. Prendere in considerazione di ospitare l'applicazione nel cloud se gli aspetti seguenti sono importanti per l'applicazione o l'organizzazione:

- Riduzione dell'investimento nei costi del data center (hardware, software, spazio, utilità, gestione dei server e così via).

- Prezzi flessibili (pagamento in base all'utilizzo, non per la capacità inattiva).

- Affidabilità estrema.

- Mobilità delle app migliorata, con semplice modifica di come e dove distribuire l'app.

- Capacità flessibile, con ridimensionamento in base alle effettive esigenze.

La compilazione di applicazioni Web con ASP.NET Core, ospitato in Azure, offre molti vantaggi competitivi rispetto alle alternative tradizionali. ASP.NET Core è ottimizzato per procedure di sviluppo di applicazioni Web moderne e scenari di hosting sul cloud. In questa guida viene descritto come progettare applicazioni ASP.NET Core per sfruttare al meglio i vantaggi di queste funzionalità.

## <a name="purpose"></a>Scopo

Questa guida offre linee guida end-to-end sulla compilazione di applicazioni Web *monolitiche* usando ASP.NET Core e Azure. In questo contesto "monolitico" si riferisce al fatto che queste applicazioni vengono distribuite come una singola unità, non come una raccolta di applicazioni e servizi che interagiscono tra loro.

Questa guida è complementare per i ["_Microservizi .NET. Architettura per le applicazioni .NET incluse in contenitori_"](../microservices-architecture/index.md) incentrata principalmente su Docker, microservizi e distribuzione di contenitori per ospitare applicazioni aziendali.

### <a name="net-microservices-architecture-for-containerized-net-applications"></a>Microservizi .NET. Architettura per le applicazioni .NET incluse in contenitori

- **eBook**  
  <https://aka.ms/MicroservicesEbook>
- **Applicazione di esempio**  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a>Destinatari della guida

I destinatari di questa guida sono prevalentemente sviluppatori, responsabili dello sviluppo e progettisti di architetture interessati alla compilazione di applicazioni Web moderne con tecnologie e servizi Microsoft nel cloud.

Un'altra parte minore dei destinatari di questa guida è costituita da responsabili delle decisioni tecniche che hanno già familiarità con ASP.NET o Azure e vogliono ottenere informazioni sull'opportunità o meno di eseguire l'aggiornamento ad ASP.NET Core per progetti nuovi o esistenti.

## <a name="how-you-can-use-this-guide"></a>Come usare questa guida

Questa guida è stata condensata in un documento relativamente piccolo, incentrato sulla compilazione di applicazioni Web con tecnologie .NET moderne e Microsoft Azure. Per questo motivo, può essere letta interamente per ottenere nozioni di base per la comprensione di tali applicazioni e delle considerazioni tecniche associate. La guida, insieme all'applicazione di esempio, può essere usata anche come punto di partenza o riferimento. Usare l'applicazione di esempio associata come modello per le applicazioni oppure per determinare come organizzare le parti che compongono l'applicazione. Tornare ai principi e alla trattazione di questa guida riguardo ad architettura, opzioni tecnologiche e considerazioni sulle decisioni per soppesare queste scelte per l'applicazione.

È possibile inoltrare questa guida al team per aiutarlo ad acquisire una comprensione di base di queste considerazioni e opportunità. Facendo sì che tutti usino un insieme comune di termini e di principi sottostanti, si garantisce l'applicazione coerente di modelli e procedure architetturali.

## <a name="references"></a>Riferimenti

- **Scelta di .NET Core o .NET Framework per le app server**  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[avanti](modern-web-applications-characteristics.md)
