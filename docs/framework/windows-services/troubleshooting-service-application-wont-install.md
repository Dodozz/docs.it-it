---
title: "Risoluzione dei problemi: Impossibile installare l'applicazione di servizio"
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
ms.openlocfilehash: ecbaa3b2fb0e0fc85ed383385368617bf361f497
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289433"
---
# <a name="troubleshooting-service-application-wont-install"></a>Risoluzione dei problemi: Impossibile installare l'applicazione di servizio
Se l'applicazione di servizio non viene installata correttamente, verificare che la proprietà <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> per la classe del servizio sia impostata sullo stesso valore indicato nel programma di installazione per il servizio. Il valore deve essere uguale in entrambe le istanze per ottenere la corretta installazione del servizio.  
  
> [!NOTE]
>  È anche possibile esaminare i log di installazione per ottenere informazioni sul processo di installazione.  
  
 Controllare inoltre se esiste un altro servizio con lo stesso nome già installato. I nomi di servizio devono essere univoci per l'esito positivo dell'installazione.  
  
## <a name="see-also"></a>Vedere anche
- [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
