---
title: Sviluppo di applicazioni di servizio Windows
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
ms.openlocfilehash: 79de8adbc0f994653f308882b335da2ffa5f7455
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035922"
---
# <a name="develop-windows-service-apps"></a>Sviluppare app di servizio Windows

Usando Visual Studio o .NET Framework SDK, è possibile creare facilmente servizi mediante la creazione di un'applicazione installata come servizio. Questo tipo di applicazione viene chiamata servizio Windows. Con le funzionalità del framework, è possibile creare servizi, installarli, avviarli, arrestarli e controllarne in altri modi il funzionamento.

> [!NOTE]
> In Visual Studio è possibile creare un servizio in codice gestito in Visual C# o Visual Basic, che può interagire con il codice C++ esistente, se necessario. In alternativa, è possibile creare un servizio Windows in C++ nativo tramite la [Creazione guidata progetto ATL](/cpp/atl/reference/atl-project-wizard).

## <a name="in-this-section"></a>Contenuto della sezione

[Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)

Offre una panoramica sulle applicazioni servizio Windows, sulla durata di un servizio e sulle differenze tra le applicazioni servizio e altri tipi di progetto comuni.

[Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

Offre un esempio di creazione di un servizio in Visual Basic e Visual C#.

[Architettura di programmazione delle applicazioni di servizio](../../../docs/framework/windows-services/service-application-programming-architecture.md)

Illustra gli elementi del linguaggio utilizzati usati programmazione dei servizi.

[Procedura: creare servizi Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)

Descrive il processo di creazione e configurazione dei servizi Windows usando il modello di progetto per servizi Windows.

## <a name="related-sections"></a>Sezioni correlate

<xref:System.ServiceProcess.ServiceBase> - Descrive le funzionalità principali della classe <xref:System.ServiceProcess.ServiceBase>, usata per creare i servizi.

<xref:System.ServiceProcess.ServiceProcessInstaller> - Descrive le funzionalità della classe <xref:System.ServiceProcess.ServiceProcessInstaller>, usata insieme alla classe <xref:System.ServiceProcess.ServiceInstaller> per installare e disinstallare i servizi.

<xref:System.ServiceProcess.ServiceInstaller> - Descrive le funzionalità della classe <xref:System.ServiceProcess.ServiceInstaller>, usata insieme alla classe <xref:System.ServiceProcess.ServiceProcessInstaller> per installare e disinstallare un servizio.

[Creare progetti da modelli](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2) -  Descrive i tipi di progetto usati in questo capitolo e come scegliere tra i vari tipi.
