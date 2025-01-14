---
title: Introduzione alla piattaforma e agli strumenti Microsoft per le app in contenitori
description: Informazioni sulle offerte di Microsoft per il supporto del ciclo di vita delle applicazioni Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 6907528a5d7ff354a312e7575531b9c608cb479f
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "66195590"
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Introduzione alla piattaforma e agli strumenti Microsoft per le app in contenitori

*Obiettivo: Creare un ciclo di vita dell'applicazione adattabile, di livello aziendale, in contenitori, che aumenti lo sviluppo, le operazioni IT e la gestione della produzione.*

La figura 3-1 mostra gli elementi fondanti del ciclo di vita delle app Docker, classificati per tipo di lavoro svolto da più team (sviluppo di app, processi dell'infrastruttura DevOps e gestione e operazioni IT). In genere nell'organizzazione i profili dell'utente tipo responsabile per ogni area sono diversi. Lo stesso vale per le competenze.

![Strumenti di Microsoft. Per il carico di lavoro di elaborazione/progettazione: Motore di docker per Windows, VS e VS Code, .NET Core, servizio Azure Kubernetes. Per il carico di lavoro di compilazione/test/spedizione: Azure DevOps, Team Foundation Server, Docker CLI, servizio Azure Kubernetes. Per il carico di lavoro di esecuzione/monitoraggio/gestione: Azure Monitor, Azure Portal, Servizio Kubernetes di Azure, Service Fabric, altri agenti di orchestrazione.](./media/image1.png)

**Figura 3-1.** Elementi fondanti del ciclo di vita per applicazioni Docker in contenitori con piattaforma e strumenti Microsoft

Un flusso di lavoro del ciclo di vita per applicazioni Docker in contenitori può essere inizialmente prescrittivo in base alle "scelte di prodotto per impostazione predefinita", permettendo agli sviluppatori di iniziare più rapidamente, ma è fondamentale che al livello sottostante vi sia un framework aperto in modo che il flusso di lavoro sia flessibile e in grado di adattarsi ai diversi contesti di ogni organizzazione o azienda. L'infrastruttura del flusso di lavoro (componenti e prodotti) deve essere sufficientemente flessibile per gestire l'ambiente che avrà ogni azienda in futuro ed essere addirittura in grado di scambiare prodotti di sviluppo o DevOps gli uni con gli altri. La flessibilità, l'apertura e l'ampia scelta di tecnologie nella piattaforma e nell'infrastruttura sono esattamente le priorità di Microsoft per le applicazioni Docker in contenitori, come spiegato nei capitoli seguenti.

La tabella 3-1 mostra che l'obiettivo di Microsoft DevOps per applicazioni Docker in contenitori è definire un flusso di lavoro DevOps aperto che permetta di scegliere quali prodotti usare per ogni fase (Microsoft o terze parti), con un flusso di lavoro semplificato in grado di fornire "prodotti per impostazione predefinita" già connessi. In questo modo, è possibile avviare rapidamente il flusso di lavoro DevOps di livello aziendale per app Docker.

**Tabella 3-1.** Flusso di lavoro DevOps, aperto per qualsiasi tecnologia

| Host | Tecnologie Microsoft | Terze parti - Collegabili ad Azure |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Piattaforma per app Docker   | • Microsoft Visual Studio e Visual Studio Code<br /> • .NET<br /> • Servizio Microsoft Azure Kubernetes (AKS)<br /> • Azure Service Fabric<br /> • Registro Azure Container<br /> | • Qualsiasi editor di codice (ad esempio, Sublime)<br /> • Qualsiasi linguaggio (Node.js, Java, Go e così via)<br /> • Qualsiasi agente di orchestrazione e utilità di pianificazione<br /> • Qualsiasi registro Docker<br /> |
| DevOps per app Docker     | • Azure DevOps Services<br /> • Microsoft Team Foundation Server<br /> • Servizio Azure Kubernetes (AKS)<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion e così via<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI e così via<br /> • Docker Datacenter, Docker Swarm, Mesos DC/OS, Kubernetes e così via in locale<br /> |
| Gestione e monitoraggio  | • Monitoraggio di Azure | • Marathon, Chronos e così via<br />|

La piattaforma e gli strumenti Microsoft per app Docker in contenitori, come definito nella tabella 3-1, includono i componenti seguenti:

- **Piattaforma per lo sviluppo di app Docker** Sviluppo di un servizio o di una raccolta di servizi che costituiscono un'"app". La piattaforma di sviluppo fornisce tutte le attività necessarie agli sviluppatori prima di inserire il codice in un repository di codice condiviso. I servizi di sviluppo, distribuiti come contenitori, sono simili allo sviluppo degli stessi servizi o app senza Docker. È possibile continuare a usare il linguaggio preferito (.NET, Node.js, Go e così via) e l'editor o l'IDE preferito, come Visual Studio o Visual Studio Code. Tuttavia, invece di considerare Docker una destinazione di distribuzione, è necessario sviluppare i servizi nell'ambiente Docker. È necessario eseguire la compilazione, i test e il debug del codice nei contenitori in locale, fornendo l'ambiente di destinazione in fase di sviluppo. Fornendo l'ambiente di destinazione in locale, i contenitori Docker eseguono la configurazione in modo da contribuire notevolmente al miglioramento del ciclo di vita DevOps. Visual Studio e Visual Studio Code includono estensioni per l'integrazione di contenitori Docker nel processo di sviluppo.

- **DevOps per app Docker** Gli sviluppatori che creano applicazioni Docker possono usare [Azure DevOps Services](https://azure.microsoft.com/services/devops/) o qualsiasi altro prodotto di terze parti, come Jenkins, per creare una gestione del ciclo di vita delle applicazioni automatica e completa.

  Con Azure DevOps Services, gli sviluppatori possono creare una soluzione DevOps incentrata su contenitori per un processo rapido e iterativo in grado di gestire il controllo del codice sorgente ovunque (Azure DevOps Services-Git, GitHub, qualsiasi repository Git remoto o Subversion), con integrazione continua, unit test, test di integrazione tra contenitori/servizi, recapito continuo e gestione del rilascio. Gli sviluppatori possono automatizzare il rilascio delle applicazioni Docker nel servizio Azure Kubernetes (AKS), dagli ambienti di sviluppo a quelli di gestione temporanea e produzione.

- **Gestione e monitoraggio** IT può gestire e monitorare le applicazioni di produzione e i servizi in diversi modi, integrando entrambe le prospettive in un'esperienza consolidata.

  - **Portale di Azure** Se si usano agenti di orchestrazione open source, il servizio Azure Kubernetes (AKS), Service Fabric e altri agenti di orchestrazione consentono di configurare e gestire gli ambienti Docker. Se si usa Azure Service Fabric, lo strumento Service Fabric Explorer permette di visualizzare e configurare il cluster.

  - **Strumenti Docker** È possibile gestire le applicazioni contenitore usando strumenti familiari. Non è necessario modificare le procedure di gestione di Docker esistenti per spostare i carichi di lavoro dei contenitori nel cloud. Usare gli strumenti di gestione delle applicazioni con cui si ha già familiarità e connettersi tramite gli endpoint API standard per l'agente di orchestrazione scelto. È anche possibile usare strumenti di terze parti per gestire le applicazioni Docker, come Docker Datacenter o addirittura strumenti Docker dell'interfaccia della riga di comando. 

    Anche se si ha familiarità con i comandi di Linux, è possibile gestire le applicazioni contenitore usando Microsoft Windows e PowerShell con una riga di comando del sottosistema di Linux e i clienti dei prodotti (Docker, Kubernetes...) in esecuzione su questa funzionalità di sottosistema Linux. Nel seguito di questo libro saranno offerte altre informazioni sull'utilizzo di questi strumenti nel sottosistema Linux usando il sistema operativo Microsoft Windows preferito.

  - **Strumenti open source** Poiché il servizio Azure Kubernetes espone gli endpoint API standard per il motore di orchestrazione, gli strumenti più diffusi sono compatibili con il servizio Azure Kubernetes e, nella maggior parte dei casi, funzioneranno immediatamente, includendo visualizzatori, monitoraggio, strumenti della riga di comando e addirittura strumenti futuri non appena vengono resi disponibili.

  - **Monitoraggio di Azure** Si tratta della soluzione di Azure per monitorare ogni aspetto dell'ambiente di produzione. È possibile monitorare le applicazioni Docker di produzione semplicemente configurando l'SDK nei servizi in modo da ottenere dati di registro generati dal sistema dalle applicazioni.

In questo modo, Microsoft offre elementi di base completi per un ciclo di vita delle applicazioni Docker in contenitori end-to-end. Tuttavia, si tratta di *una raccolta di prodotti e tecnologie che consente di selezionare e integrare con strumenti e processi esistenti in base alle preferenze*. La flessibilità di un ampio approccio con tutta la potenza e la completezza delle funzionalità pone Microsoft in una solida posizione per lo sviluppo di applicazioni Docker in contenitori.

>[!div class="step-by-step"]
>[Precedente](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
>[Successivo](../design-develop-containerized-apps/index.md)
