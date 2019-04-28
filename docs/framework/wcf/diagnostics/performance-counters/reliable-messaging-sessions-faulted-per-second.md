---
title: Sessioni di messaggistica affidabile con errori per secondo
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: c77d6a5f12dcce15dba94e2f63025a219ebcc6fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916123"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Sessioni di messaggistica affidabile con errori per secondo
Nome contatore: Sessioni di messaggistica affidabile con errori al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di sessioni di messaggistica affidabile con errori per il servizio in un secondo.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
