---
title: Uso dei comandi di Windows PowerShell in un oggetto DockerFile per configurare i contenitori di Windows (basati su standard Docker)
description: Informazioni su come usare PowerShell quando si lavora con Docker nei contenitori di Windows
ms.date: 02/15/2019
ms.openlocfilehash: e91d278aef1365a111e8d67ff04092dfc6a44185
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "65641591"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Uso dei comandi di Windows PowerShell in un oggetto DockerFile per configurare i contenitori di Windows (basati su standard Docker)

I [contenitori Windows](/virtualization/windowscontainers/about/index) consentono di convertire applicazioni Windows esistenti in immagini Docker e di distribuirle con gli stessi strumenti che si usano con il resto dell'ecosistema Docker.

Per usare i contenitori Windows è sufficiente scrivere comandi di Windows PowerShell nel DockerFile, come illustrato nell'esempio seguente:

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

In questo caso si usa Windows PowerShell per installare un'immagine di base di Windows Server Core, oltre a IIS.

In modo analogo è possibile usare i comandi di Windows PowerShell anche per configurare componenti aggiuntivi come i classici ASP.NET 4.x, .NET 4.6 o qualsiasi altro software Windows, come illustrato di seguito:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Precedente](visual-studio-tools-for-docker.md)
>[Successivo](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
