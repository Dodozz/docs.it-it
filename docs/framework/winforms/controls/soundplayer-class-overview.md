---
title: Cenni preliminari sulla classe SoundPlayer
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 3ff23cbfa78b803d4526e7a7c389fd5d458a967c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972003"
---
# <a name="soundplayer-class-overview"></a>Cenni preliminari sulla classe SoundPlayer
La classe <xref:System.Media.SoundPlayer> consente di includere facilmente suoni nelle applicazioni.  
  
 Il <xref:System.Media.SoundPlayer> classe consente di riprodurre file audio in formato WAV, da una risorsa o da percorsi UNC o HTTP. Inoltre, il <xref:System.Media.SoundPlayer> classe consente di caricare o riprodurre suoni in modo asincrono.  
  
 È anche possibile usare la classe<xref:System.Media.SystemSounds> per riprodurre suoni del sistema comuni, compresi i segnali acustici.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Proprietà, metodi ed eventi usati comunemente  
  
|Nome|Descrizione|  
|----------|-----------------|  
|Proprietà <xref:System.Media.SoundPlayer.SoundLocation%2A>|Percorso del file o l'indirizzo Web del suono. I valori accettabili sono UNC o HTTP.|  
|Proprietà <xref:System.Media.SoundPlayer.LoadTimeout%2A>|Numero di millisecondi di attesa per caricare un suono prima genera un'eccezione. Il valore predefinito è 10 secondi.|  
|Proprietà <xref:System.Media.SoundPlayer.IsLoadCompleted%2A>|Valore booleano che indica se l'audio è stato caricato.|  
|Metodo <xref:System.Media.SoundPlayer.Load%2A>|Carica un suono in modo sincrono.|  
|Metodo <xref:System.Media.SoundPlayer.LoadAsync%2A>|Inizia a caricare in modo asincrono un suono. Una volta completato il caricamento, viene generato il <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> evento.|  
|Metodo <xref:System.Media.SoundPlayer.Play%2A>|Riproduce il suono specificato nella <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> proprietà in un nuovo thread.|  
|Metodo <xref:System.Media.SoundPlayer.PlaySync%2A>|Riproduce il suono specificato nella <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> proprietà nel thread corrente.|  
|Metodo <xref:System.Media.SoundPlayer.Stop%2A>|Arresta un suono.|  
|Evento<xref:System.Media.SoundPlayer.LoadCompleted> |Generato dopo il tentativo di caricamento di un suono.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
