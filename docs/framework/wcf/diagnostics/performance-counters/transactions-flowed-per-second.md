---
title: Transazioni propagate al secondo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927192"
---
# <a name="transactions-flowed-per-second"></a>Transazioni propagate al secondo
Nome contatore:  Transazioni propagate al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di transazioni propagate a questa operazione in un secondo. Questo contatore viene incrementato ogni volta che è presente un ID di transazione in un messaggio inviato all'operazione.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
