---
title: Introduzione alla piattaforma e agli strumenti Microsoft per le app in contenitori
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: fe65e9036c1e0bdf2afe05426c01e75d48f93439
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152338"
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Introduzione alla piattaforma Microsoft e strumenti per le App in contenitori


La figura 3-1 mostra gli elementi fondanti del ciclo di vita delle app Docker, classificati per tipo di lavoro svolto da più team (sviluppo di app, processi dell'infrastruttura DevOps e gestione e operazioni IT). In genere nell'organizzazione i profili dell'utente tipo responsabile per ogni area sono diversi. Lo stesso vale per le competenze.

![](./media/image1.png)

Figura 3-1: Concetti di base del ciclo di vita per applicazioni Docker in contenitori con piattaforma e strumenti Microsoft

Un flusso di lavoro del ciclo di vita per applicazioni Docker in contenitori può essere inizialmente prescrittivo in base alle "scelte di prodotto per impostazione predefinita", permettendo agli sviluppatori di iniziare più rapidamente, ma è fondamentale che al livello sottostante vi sia un framework aperto in modo che il flusso di lavoro sia flessibile e in grado di adattarsi ai diversi contesti di ogni organizzazione o azienda. L'infrastruttura del flusso di lavoro (componenti e prodotti) deve essere sufficientemente flessibile per gestire l'ambiente che avrà ogni azienda in futuro ed essere addirittura in grado di scambiare prodotti di sviluppo o DevOps gli uni con gli altri. La flessibilità, l'apertura e l'ampia scelta di tecnologie nella piattaforma e nell'infrastruttura sono esattamente le priorità di Microsoft per le applicazioni Docker in contenitori, come spiegato nei capitoli seguenti.

La tabella 3-1 mostra che l'obiettivo di Microsoft DevOps per applicazioni Docker in contenitori è definire un flusso di lavoro DevOps aperto che permetta di scegliere quali prodotti usare per ogni fase (Microsoft o terze parti), con un flusso di lavoro semplificato in grado di fornire "prodotti per impostazione predefinita" già connessi. In questo modo, è possibile avviare rapidamente il flusso di lavoro DevOps di livello aziendale per app Docker.

Tabella 3-1: Flusso di lavoro DevOps aperto per qualsiasi tecnologia

| Host | Tecnologie Microsoft | Terze parti - Collegabili ad Azure |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Piattaforma per app Docker   | • Microsoft Visual Studio e Visual Studio Code<br /> • .NET<br /> • Servizio Azure Container di Microsoft Azure<br /> • Azure Service Fabric<br /> • Registro Azure Container<br /> | • Qualsiasi editor di codice (ad esempio, Sublime)<br /> • Qualsiasi linguaggio (Node.js, Java, Go e così via)<br /> • Qualsiasi agente di orchestrazione e utilità di pianificazione<br /> • Qualsiasi registro Docker<br /> |
| DevOps per app Docker     | • Servizi di azure DevOps<br /> • Microsoft Team Foundation Server<br /> • Servizio Azure Container<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion e così via<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI e così via<br /> • Docker Datacenter, Docker Swarm, Mesos DC/OS, Kubernetes e così via in locale<br /> |
| Gestione e monitoraggio  | • Operations Management Suite<br /> • Applications Insights<br /> | • Marathon, Chronos e così via<br />

La piattaforma e gli strumenti Microsoft per app Docker in contenitori, come definito nella tabella 3-1, includono i componenti seguenti:

-   **Piattaforma per lo sviluppo di app Docker** Sviluppo di un servizio o di una raccolta di servizi che costituiscono un'"app". La piattaforma di sviluppo fornisce tutte le attività necessarie agli sviluppatori prima di inserire il codice in un repository di codice condiviso. I servizi di sviluppo, distribuiti come contenitori, sono molto simili allo sviluppo degli stessi servizi o app senza Docker. Continuare a usare il linguaggio preferito (.NET, Node. js, Go e così via) e l'editor preferito o l'IDE come Visual Studio o Visual Studio Code. Tuttavia, invece di considerare Docker una destinazione di distribuzione, è necessario sviluppare i servizi nell'ambiente Docker. È necessario eseguire la compilazione, i test e il debug del codice nei contenitori in locale, fornendo l'ambiente di destinazione in fase di sviluppo. Fornendo l'ambiente di destinazione in locale, i contenitori Docker eseguono la configurazione in modo da contribuire notevolmente al miglioramento del ciclo di vita DevOps. Visual Studio e Visual Studio Code includono estensioni per l'integrazione di contenitori Docker nel processo di sviluppo.

-   **DevOps per App Docker** gli sviluppatori che creano applicazioni Docker possono usare servizi di Azure DevOps o qualsiasi altro prodotto di terze parti, come Jenkins, per la compilazione di una serie completa automatici gestione del ciclo di vita delle applicazioni (ALM).

Con i servizi di Azure DevOps, gli sviluppatori possono creare incentrata su contenitori controllare DevOps per un processo rapido e iterativo che copre del codice sorgente ovunque (servizi DevOps di Azure-Git, GitHub, qualsiasi repository Git remoto o Subversion), integrazione continua (CI) , unit test, tra i test di integrazione di contenitori/servizi, recapito continuo (CD) e la gestione del rilascio (RM). Gli sviluppatori possono automatizzare il rilascio delle applicazioni Docker nel servizio Azure Container, dagli ambienti di sviluppo a quelli di gestione temporanea e produzione.
 
-   Gestione e monitoraggio della produzione da parte dell'IT.

**Gestione** L'IT può gestire le applicazioni e i servizi di produzione in diversi modi:

-   **Portale di Azure** Se si usano agenti di orchestrazione open source, il servizio contenitore di Azure insieme a strumenti di gestione dei cluster come Docker Datacenter e Mesosphere Marathon semplificano la configurazione e la gestione degli ambienti Docker. Se si usa Azure Service Fabric, lo strumento Service Fabric Explorer permette di visualizzare e configurare il cluster.

-   **Strumenti Docker** È possibile gestire le applicazioni contenitore usando strumenti familiari. Non è necessario modificare le procedure di gestione di Docker esistenti per spostare i carichi di lavoro dei contenitori nel cloud. Usare gli strumenti di gestione delle applicazioni con cui si ha già familiarità e connettersi tramite gli endpoint API standard per l'agente di orchestrazione scelto. È anche possibile usare strumenti di terze parti per gestire le applicazioni Docker, come Docker Datacenter o addirittura strumenti Docker dell'interfaccia della riga di comando.

-   **Strumenti open source** Poiché il servizio contenitore di Azure espone gli endpoint API standard per il motore di orchestrazione, gli strumenti più diffusi sono compatibili con il servizio contenitore di Azure e, nella maggior parte dei casi, funzioneranno immediatamente, includendo visualizzatori, monitoraggio, strumenti della riga di comando e addirittura strumenti futuri non appena vengono resi disponibili.

**Monitoraggio** Durante l'esecuzione di ambienti di produzione, è possibile monitorare ogni aspetto usando i componenti seguenti:

-   **Operations Management Suite (OMS)** La "soluzione contenitore OMS" può gestire e monitorare host e contenitori Docker mostrando le informazioni relative alla posizione di contenitori e host di contenitori e ai contenitori in esecuzione o danneggiati, insieme ai log di daemon e contenitori Docker. La soluzione mostra anche le metriche di prestazioni, tra cui CPU, memoria, rete e archiviazione, per il contenitore e gli host per semplificare la risoluzione dei problemi e trovare i contenitori che possono influire negativamente sulle prestazioni nelle vicinanze.

-   **Application Insights** È possibile monitorare le applicazioni Docker di produzione configurando in tutta semplicità l'SDK nei servizi in modo da ottenere dati di telemetria dalle applicazioni.

In questo modo, Microsoft offre elementi di base completi per un ciclo di vita delle applicazioni Docker in contenitori end-to-end. Tuttavia, si tratta di *una raccolta di prodotti e tecnologie che consente selezione e integrazione con strumenti e processi esistenti in base alle preferenze*. La flessibilità di un ampio approccio con tutta la potenza e la completezza delle funzionalità pone Microsoft in una solida posizione per lo sviluppo di applicazioni Docker in contenitori.

>[!div class="step-by-step"]
>[Precedente](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
>[Successivo](../design-develop-containerized-apps/index.md)