---
title: Registrazione di informazioni relative all'applicazione (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: 3202bdb2c4274e6d3127537b7cae661ba6e63a35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052508"
---
# <a name="logging-information-from-the-application-visual-basic"></a>Registrazione di informazioni relative all'applicazione (Visual Basic)
Questa sezione contiene argomenti che descrivono come registrare le informazioni provenienti dall'applicazione usando l'oggetto `My.Application.Log` o `My.Log`. Viene anche spiegato come estendere le funzionalità di registrazione dell'applicazione.  
  
 L'oggetto `Log` fornisce i metodi per scrivere le informazioni sui listener di log dell'applicazione, mentre la proprietà avanzata `TraceSource` dell'oggetto `Log` fornisce informazioni di configurazione dettagliate. L'oggetto `Log` può essere configurato dal file di configurazione dell'applicazione.  
  
 L'oggetto `My.Log` è disponibile solo per le applicazioni ASP.NET. Per le applicazioni client, usare `My.Application.Log`. Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## <a name="tasks"></a>Attività  
  
|A|Vedere|  
|--------|---------|  
|Scrivere le informazioni sugli eventi nei log dell'applicazione.|[Procedura: Scrivere messaggi di log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|Scrivere le informazioni sulle eccezioni nei log dell'applicazione.|[Procedura: Registrare eccezioni](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|Scrivere le informazioni di traccia nei log dell'applicazione all'avvio e alla chiusura dell'applicazione.|[Procedura: Registrare messaggi all'avvio o all'arresto dell'applicazione](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Configurare `My.Application.Log` per scrivere le informazioni in un file di testo.|[Procedura: Scrivere informazioni sugli eventi in un file di testo](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|Configurare `My.Application.Log` per scrivere le informazioni in un log eventi.|[Procedura: Scrivere nel registro eventi di un'applicazione](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|Modificare la posizione in cui `My.Application.Log` scrive le informazioni.|[Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|Determinare la posizione in cui `My.Application.Log` scrive le informazioni.|[Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|Creare un listener di log personalizzato per `My.Application.Log`.|[Procedura dettagliata: Creazione di listener di log personalizzati](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|Filtrare l'output dei log `My.Application.Log`.|[Procedura dettagliata: Filtro dell'output di My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Risoluzione dei problemi: Listener di log](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
