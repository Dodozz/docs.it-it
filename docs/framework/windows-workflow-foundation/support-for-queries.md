---
title: Supporto per le query
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: db3580d0a29353aac027bddd8f040d3085d674af
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665295"
---
# <a name="support-for-queries"></a>Supporto per le query
L'archivio di istanze del flusso di lavoro SQL registra un set di proprietà note nell'archivio. Gli utenti possono eseguire query per le istanze basate su queste proprietà. Nell'elenco seguente sono contenute alcune di queste proprietà note:  
  
- **Nome del sito.** Nome del sito Web che contiene il servizio.  
  
- **Percorso relativo dell'applicazione.** Percorso dell'applicazione relativo al sito Web.  
  
- **Percorso relativo del servizio.** Percorso del servizio relativo all'applicazione.  
  
- **Nome del servizio.** Nome del servizio.  
  
- **Servizio Namespace.** Nome dello spazio dei nomi utilizzato dal servizio.  
  
- **Computer corrente.**  
  
- **Ultimo macchina**. Computer su cui l'istanza del servizio flusso di lavoro è stata eseguita l'ultima volta.  
  
> [!NOTE]
>  Per gli scenari indipendenti che usano l'host del servizio del flusso di lavoro vengono popolate solo le ultime quattro proprietà. Per gli scenari dell'applicazione flusso di lavoro, viene popolata solo l'ultima proprietà.  
  
 L'esecuzione del flusso di lavoro fornisce valori per le prime tre proprietà. L'host del servizio del flusso di lavoro fornisce il valore per il **Suspend Reason** proprietà. La Store di istanza del flusso di lavoro SQL stesso fornisce valori per il **Last Updated Machine** proprietà.  
  
 La funzionalità di archivio di istanze del flusso di lavoro SQL consente anche di specificare le proprietà personalizzate per cui si desidera archiviare i valori nel database di persistenza e che si desidera usare nelle query. Per altre informazioni sulle promozioni personalizzate, vedere [Store estendibilità](store-extensibility.md).  
  
## <a name="views"></a>Visualizzazioni  
 L'archivio di istanze contiene le visualizzazioni seguenti. Visualizzare [Schema di Database di persistenza](persistence-database-schema.md) per altri dettagli.  
  
### <a name="the-instances-view"></a>Visualizzazione Instances  
 La visualizzazione Instances contiene i campi seguenti:  
  
1. **Id**  
  
2. **PendingTimer**  
  
3. **CreationTime**  
  
4. **LastUpdatedTime**  
  
5. **ServiceDeploymentId**  
  
6. **SuspensionExceptionName**  
  
7. **SuspensionReason**  
  
8. **ActiveBookmarks**  
  
9. **CurrentMachine**  
  
10. **LastMachine**  
  
11. **ExecutionStatus**  
  
12. **IsInitialized**  
  
13. **IsSuspended**  
  
14. **IsCompleted**  
  
15. **EncodingOption**  
  
16. **ReadWritePrimitiveDataProperties**  
  
17. **WriteOnlyPrimitiveDataProperties**  
  
18. **ReadWriteComplexDataProperties**  
  
19. **WriteOnlyComplexDataProperties**  
  
### <a name="the-servicedeployments-view"></a>Visualizzazione ServiceDeployments  
 La visualizzazione ServiceDeployments contiene i campi seguenti:  
  
1. **SiteName**  
  
2. **RelativeServicePath**  
  
3. **RelativeApplicationPath**  
  
4. **ServiceName**  
  
5. **ServiceNamespace**  
  
### <a name="the-instancepromotedproperties-view"></a>Visualizzazione InstancePromotedProperties  
 La visualizzazione InstancePromotedProperties contiene i campi seguenti. Per informazioni dettagliate sulle proprietà innalzate di livello, vedere la [Store estendibilità](store-extensibility.md) argomento.  
  
1. **InstanceId**  
  
2. **EncodingOption**  
  
3. **PromotionName**  
  
4. **Valore #** (un intervallo di campi da **Value1** al **Value64**).
