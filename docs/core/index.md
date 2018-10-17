---
title: Guida a .NET Core
description: .NET core è un'implementazione modulare ad alte prestazioni di .NET per la creazione di app di Windows, Mac e Linux. Vedere l'introduzione a .NET Core per iniziare.
author: richlander
ms.author: mairaw
ms.date: 08/01/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 692d49cc940925f629e55cf5cc103522bd3cbb38
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49348975"
---
# <a name="net-core-guide"></a>Guida a .NET Core

[.NET Core](about.md) è una piattaforma [open source](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT) di sviluppo generale gestita da Microsoft e dalla community .NET su [GitHub](https://github.com/dotnet/core). È multipiattaforma, supporta Windows, macOS e Linux e può essere usata in applicazioni per dispositivi, cloud e IoT.

Vedere [Informazioni su .NET Core](about.md) per altre informazioni su .NET Core, inclusi le caratteristiche, i linguaggi e i framework supportati e le principali API.

Per imparare a creare una semplice applicazione .NET Core, vedere le [Esercitazioni di .NET Core](tutorials/index.md). Sono necessari pochi minuti per realizzare ed eseguire la prima app. Se si vuole provare .NET Core nel browser, vedere la guida introduttiva [Numeri in C#](../csharp/quick-starts/numbers-in-csharp.yml).

## <a name="download-net-core-21"></a>Scaricare .NET Core 2.1

Scaricare [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) per provare .NET Core nel computer Windows, macOS o Linux. Visitare [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) se si preferisce usare i contenitori Docker.

Tutte le versioni di .NET Core sono disponibili nella pagina [Download di .NET Core](https://www.microsoft.com/net/download/archives) se si sta cercando un'altra versione di .NET Core.

## <a name="net-core-21"></a>.NET Core 2.1

La versione più recente è [.NET Core 2.1](whats-new/dotnet-core-2-1.md). Le nuove funzionalità includono: strumenti globali, API ad alte prestazioni (ad esempio <xref:System.Span%601?displayProperty=nameWithType>), compilazione JIT a livelli, miglioramenti della [compilazione](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) e [miglioramenti delle prestazioni di runtime](https://blogs.msdn.microsoft.com/dotnet/2018/04/18/performance-improvements-in-net-core-2-1/) e il supporto per Alpine e ARM32.

## <a name="create-your-first-application"></a>Creare la prima applicazione

Dopo aver installato .NET Core SDK, aprire un prompt dei comandi. Digitare i seguenti comandi `dotnet` per creare ed eseguire un'applicazione C#.

```console
dotnet new console
dotnet run
```

È necessario visualizzare il seguente output:

```console
Hello World!
```

## <a name="support"></a>Supporto

.NET Core è [supportato da Microsoft](https://www.microsoft.com/net/support/policy) in Windows, macOS e Linux. Viene aggiornato per sicurezza e qualità diverse volte l'anno, in genere ogni mese.

Le distribuzioni binarie di .NET Core sono compilate e testate in server gestiti da Microsoft in Azure e sono supportate come qualsiasi prodotto Microsoft.

[Red Hat supporta .NET Core](http://redhatloves.net/) in Red Hat Enterprise Linux (RHEL). Red Hat consente di compilare .NET Core dall'origine e rende disponibili le compilazioni nelle [raccolte software di Red Hat](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat e Microsoft collaborano per assicurarsi che .NET Core funzioni correttamente in RHEL.
