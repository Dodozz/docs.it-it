---
title: Codifica di oggetti binari con il codificatore ByteStream
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: 09a919e11971f81bc76dca0e45a7eb0e70ef749e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626936"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a>Codifica di oggetti binari con il codificatore ByteStream
Invio e ricezione di dati binari non elaborati con Windows Communication Foundation (WCF) viene configurato usando <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.  
  
## <a name="byte-stream-message-encoder-architecture"></a>Architettura del codificatore di messaggi del flusso di byte  
 Il codificatore di messaggi binario utilizzato da WCF non dispone di funzionalità per l'elaborazione, la convalida o che identifica i dati binari sottostanti nel messaggio. Il pacchetto dei dati viene codificato in XML, inviato, ricevuto e decodificato. Il codificatore elabora i dati dopo essere passati al trasporto e prima che il messaggio venga inviato alla coda di messaggi. A livello funzionale, il codificatore binario esegue il wrapping dei dati del messaggio negli elementi `<binary>` per l'invio e rimuove gli elementi in seguito alla ricezione del messaggio.  
  
## <a name="using-the-byte-stream-message-encoder"></a>Utilizzo del codificatore di messaggi del flusso di byte  
 Nell'esempio seguente viene mostrato un contratto di servizio che implementa il codificatore di messaggi del flusso di byte.  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 Nell'esempio riportato di seguito viene illustrato il servizio richiamato.  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 In caso di utilizzo di un servizio che implementa un'infrastruttura di messaggi (ad esempio, un router), il messaggio viene elaborato senza controllo, convalida o interazione con il messaggio, come mostrato nell'esempio seguente.  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a>Scenari  
 Il codificatore del flusso di byte è utile negli scenari seguenti.  
  
- Trasferimento di un'immagine JPEG tra computer mediante WCF. In questo scenario l'immagine arriva tramite il trasporto da un'origine esterna e i dati inviati saranno i byte non elaborati che costituiscono l'immagine. Un servizio riceverà i dati binari e visualizzerà l'immagine.  
  
- Lettura delle informazioni al di fuori di una coda di messaggi ed elaborazione delle informazioni. Il messaggio verrà letto da un gestore delle code di messaggi e verrà passato al canale della coda di messaggi per essere gestito. Il canale della coda di messaggi fungerà da gestore delle code nello stack di canali WCF.  
  
 In caso di invio di un messaggio tramite un canale della coda di messaggi, il mittente non avrà alcun controllo sui byte ricevuti dal gestore delle code. Se il processo di ricezione non è in grado di leggere i byte non elaborati, il messaggio verrà ricevuto in un formato non corretto e non verrà elaborato. Si presuppone che il processo di ricezione sia in grado di convertire i byte ricevuti in un formato utilizzabile.
