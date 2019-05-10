---
title: 'Procedura: Eseguire query per istanze non persistenti'
ms.date: 03/30/2017
ms.assetid: 294019b1-c1a7-4b81-a14f-b47c106cd723
ms.openlocfilehash: cbc3ec59bc0fbd8c39d351c248a664dc9231044c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584939"
---
# <a name="how-to-query-for-non-persisted-instances"></a>Procedura: Eseguire query per istanze non persistenti
Quando viene creata una nuova istanza di un servizio e per tale servizio è definito il comportamento dell'archivio di istanze del flusso di lavoro SQL, l'host del servizio crea una voce iniziale per tale istanza del servizio nell'archivio di istanze. Successivamente, quando l'istanza del servizio viene salvata in modo permanente per la prima volta, il comportamento dell'archivio di istanze del flusso di lavoro SQL archivia lo stato dell'istanza corrente insieme ai dati aggiuntivi richiesti per le operazioni di attivazione, recupero e controllo.  
  
 Se un'istanza non viene salvata in modo permanente dopo la creazione della voce iniziale per tale istanza, si dice che l'istanza del servizio è nello stato non persistente. In tutte le istanze persistenti del servizio è possibile eseguire query e controlli, che non possono invece essere eseguiti in tutte le istanze non persistenti. Se un'istanza non persistente è sospesa a causa di un'eccezione non gestita, su di essa è possibile eseguire query, ma non controlli.  
  
 Le istanze del servizio durevoli che non sono ancora salvate in modo permanente rimangono in uno stato non persistente negli scenari seguenti:  
  
- L'host del servizio si arresta in modo anomalo prima che l'istanza venga salvata in modo permanente per la prima volta. La voce iniziale per l'istanza rimane nell'archivio di istanze. L'istanza non è recuperabile. In caso di arrivo di un messaggio correlato, l'istanza diventa nuovamente attiva.  
  
- Si verifica un'eccezione non gestita dell'istanza prima che questa venga salvata in modo permanente per la prima volta. Si presentano gli scenari seguenti  
  
    - Se il valore della **UnhandledExceptionAction** è impostata su **abbandonare**, le informazioni sulla distribuzione di servizio vengono scritte nell'archivio di istanze e l'istanza viene scaricata dalla memoria. L'istanza rimane nello stato non persistente nel database di persistenza.  
  
    - Se il valore della **UnhandledExceptionAction** è impostata su **AbandonAndSuspsend**, le informazioni sulla distribuzione di servizio vengono scritte nel database di persistenza e lo stato dell'istanza è impostato su  **Sospeso**. L'istanza non può essere ripresa, annullata o terminata. L'host del servizio non può caricare l'istanza perché non è ancora stata salvata in modo permanente e, pertanto, la voce del database per l'istanza non è completa.  
  
    - Se il valore del **UnhandledExceptionAction** è impostata su **Annulla** oppure **Terminate**, le informazioni di distribuzione del servizio vengono scritte nell'archivio di istanze e il stato dell'istanza è impostato su **Completed**.  
  
 Nelle sezioni seguenti vengono fornite query di esempio per trovare istanze non persistenti nel database di persistenza SQL ed eliminare tali istanze dal database.  
  
## <a name="to-find-all-instances-not-persisted-yet"></a>Per trovare tutte le istanze non ancora salvate in modo permanente  
 La query SQL seguente restituisce l'ID e l'ora di creazione per tutte le istanze che non sono ancora state salvate in modo permanente nel database di persistenza.  
  
```  
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0;  
```  
  
## <a name="to-find-all-instances-not-persisted-yet-and-also-not-loaded"></a>Per trovare tutte le istanze non ancora salvate in modo permanente e non caricate  
 La query SQL seguente restituisce l'ID e l'ora di creazione per tutte le istanze che non sono state salvate in modo permanente e che non sono state caricate.  
  
```  
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and CurrentMachine is NULL;  
```  
  
## <a name="to-find-all-suspended-instances-not-persisted-yet"></a>Per trovare tutte le istanze sospese non ancora salvate in modo permanente  
 La query SQL seguente restituisce ID, ora di creazione, motivo della sospensione e nome di eccezione della sospensione per tutte le istanze non salvate in modo permanente e in stato sospeso.  
  
```  
select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and IsSuspended = 1;  
```  
  
## <a name="to-delete-non-persisted-instances-from-the-persistence-database"></a>Per eliminare istanze non persistenti dal database di persistenza  
 È necessario cercare periodicamente le istanze non persistenti nell'archivio di istanze e rimuoverle se si ha la certezza che non riceveranno messaggi correlati. Ad esempio, se l'istanza è presente nel database da diversi mesi e si è a conoscenza che il flusso di lavoro ha in genere una durata di alcuni giorni, è possibile presupporre con sicurezza che si tratta di un'istanza non inizializzata che si era arrestata in modo anomalo.  
  
 In generale, è possibile eliminare istanze non persistenti che non sono sospese né caricate. È consigliabile non eliminare **tutti** le istanze non persistenti perché questo set include le istanze sono appena state create ma non sono ancora persistenti. È necessario eliminare solo istanze non persistenti rimaste nell'archivio perché l'host del servizio flusso di lavoro che ha attivato il caricamento dell'istanza ha causato un'eccezione o l'istanza stessa ha causato un'eccezione.  
  
> [!WARNING]
>  L'eliminazione di istanze non persistenti dall'archivio di istanze riduce le dimensioni dell'archivio e può migliorare le prestazioni delle operazioni di archiviazione.
