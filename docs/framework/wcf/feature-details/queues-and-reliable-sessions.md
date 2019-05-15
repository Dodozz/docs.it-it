---
title: Code e sessioni affidabili
ms.date: 03/30/2017
ms.assetid: 7e794d03-141c-45ed-b6b1-6c0e104c1464
ms.openlocfilehash: 7a60e6f92f6875b6fb446d29abc7d858bfdefe73
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557163"
---
# <a name="queues-and-reliable-sessions"></a>Code e sessioni affidabili
Code e sessioni affidabili sono le funzionalità di Windows Communication Foundation (WCF) che implementano la messaggistica affidabile. Gli argomenti contenuti in questa sezione descrivono le funzionalità di messaggistica affidabile di WCF.  
  
 La messaggistica affidabile riguarda il modo in cui un'origine di messaggistica affidabile (definita origine) trasferisce in modo affidabile i messaggi a una destinazione di messaggistica affidabile (definita destinazione).  
  
 Gli aspetti chiave della messaggistica affidabile sono i seguenti:  
  
- Garanzie di trasferimento dei messaggi inviati da un'origine a una destinazione indipendentemente dagli errori di trasporto o di trasferimento dei messaggi.  
  
- Separazione dell'origine e della destinazione, che fornisce funzioni di errore e un recupero indipendente dell'origine e della destinazione, nonché un trasferimento e un recapito affidabili dei messaggi, anche se l'origine o la destinazione non è disponibile.  
  
 La messaggistica affidabile comporta spesso il costo di una latenza elevata. Per latenza si intende il tempo che un messaggio impiega per giungere dall'origine alla destinazione. WCF, di conseguenza, offre i seguenti tipi di messaggistica affidabile:  
  
- [Le sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions.md), che offrono un trasferimento affidabile senza il costo di una latenza elevata  
  
- [Code in WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md), che offrono trasferimenti affidabili e separazione tra l'origine e destinazione.  
  
## <a name="reliable-sessions"></a>Sessioni affidabili  
 Le sessioni affidabili forniscono un trasferimento affidabile end-to-end dei messaggi tra un'origine e una destinazione utilizzando il protocollo WS-ReliableMessaging indipendentemente dal numero o dal tipo di intermediari che separano gli endpoint di messaggistica (origine e destinazione). In questo modo vengono inclusi tutti gli intermediari del trasporto che non utilizzano SOAP (ad esempio proxy HTTP) o gli intermediari che utilizzano SOAP (ad esempio bridge o router basati su SOAP) necessari per il flusso dei messaggi tra gli endpoint. Le sessioni affidabili utilizzano una finestra di trasferimento in memoria per mascherare gli errori a livello di messaggio SOAP e riattivare le connessioni in caso di errori di trasporto.  
  
 Le sessioni affidabili forniscono trasferimenti affidabili dei messaggi con una latenza bassa. Provvedono ai messaggi SOAP su qualsiasi proxy o intermediario, in modo equivalente a TCP per i pacchetti su bridge IP. Per altre informazioni sulle sessioni affidabili, vedere [sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions.md).  
  
## <a name="queues"></a>Code  
 Code in WCF forniscono il trasferimento affidabile dei messaggi e la separazione tra origini e destinazioni al costo di una latenza elevata. WCF in coda la comunicazione si basa sull'accodamento messaggi (noto anche come MSMQ).  
  
 MSMQ viene fornito con Windows come opzione e viene eseguito come servizio NT. Acquisisce i messaggi da trasmettere in una coda di trasmissione per conto dell'origine e li recapita a una coda di destinazione. La coda di destinazione accetta i messaggi per conto della destinazione a cui verranno recapitati in seguito quando la destinazione richiede i messaggi. I gestori code MSMQ implementano un protocollo di trasferimento messaggi affidabile, in modo che i messaggi non vengano persi durante la trasmissione. Il protocollo può essere nativo o un protocollo basato su SOAP, come SRMP (SOAP Reliable Messagging Protocol).  
  
 La separazione, abbinata ai trasferimenti affidabili dei messaggi tra le code, consente alle applicazioni ad accoppiamento debole di comunicare in modo affidabile. A differenza delle sessioni affidabili, non è necessario che l'origine e la destinazione siano in esecuzione contemporaneamente. Questo consente implicitamente scenari in cui le code vengono di fatto utilizzate come un meccanismo di livellamento del carico nei casi in cui non vi è corrispondenza tra il tasso di produzione di messaggi dell'origine e il tasso di utilizzo di messaggi da parte della destinazione. Per altre informazioni sulle code, vedere [code in WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md).  
  
## <a name="see-also"></a>Vedere anche

- [Code in WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [Accodamento in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
- [Sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
- [Panoramica delle sessioni affidabili](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)
