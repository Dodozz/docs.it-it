---
title: Criteri di ricerca personalizzati
ms.date: 03/30/2017
ms.assetid: b2723929-8829-424d-8015-a37ba2ab4f68
ms.openlocfilehash: 7409539c823243a783cacd4e04d6fab225b606cc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650193"
---
# <a name="custom-find-criteria"></a>Criteri di ricerca personalizzati
In questo esempio viene illustrato come creare una corrispondenza degli ambiti personalizzata utilizzando la logica e come implementare un servizio di individuazione personalizzato. I client utilizzano la funzionalità di corrispondenza degli ambiti personalizzata per rifinire ed eseguire l'ulteriore compilazione sulla funzionalità di individuazione fornita dal sistema di WCF Discovery. Lo scenario analizzato in questo esempio è il seguente:  
  
1. Un client esegue la ricerca di un servizio calcolatrice.  
  
2. Per rifinirne la ricerca, il client deve utilizzare una regola per la corrispondenza degli ambiti personalizzata.  
  
3. In base a questa regola, un servizio risponde al client se il relativo endpoint corrisponde a uno qualsiasi degli ambiti specificati dal client.  
  
## <a name="demonstrates"></a>Dimostrazione  
  
- Creazione di un servizio di individuazione personalizzato.  
  
- Implementazione di una corrispondenza degli ambiti personalizzata mediante un algoritmo.  
  
## <a name="discussion"></a>Discussione  
 Il client esegue la ricerca per il tipo "OR" criteri di corrispondenza. Un servizio risponde se gli ambiti sui relativi endpoint corrispondono a uno qualsiasi degli ambiti forniti dal client. In questo caso, il client esegue la ricerca di un servizio calcolatrice che dispone di uno qualsiasi degli ambiti riportati nell'elenco seguente:  
  
1. `net.tcp://Microsoft.Samples.Discovery/RedmondLocation`  
  
2. `net.tcp://Microsoft.Samples.Discovery/SeattleLocation`  
  
3. `net.tcp://Microsoft.Samples.Discovery/PortlandLocation`  
  
 A tale scopo, il client indica ai servizi di utilizzare una regola per la corrispondenza degli ambiti personalizzata passando una corrispondenza degli ambiti personalizzata tramite URI. Per facilitare la corrispondenza degli ambiti personalizzata, il servizio deve utilizzare un servizio di individuazione personalizzato in grado di comprendere la regola per la corrispondenza degli ambiti personalizzata e di implementare la logica corrispondente associata.  
  
 Nel progetto client aprire il file Program.cs. Si noti che il campo `ScopeMatchBy` dell'oggetto `FindCriteria` è impostato su un URI specifico. Questo identificatore viene inviato al servizio. Se il servizio non è in grado di comprendere questa regola, la richiesta di ricerca del client verrà ignorata.  
  
 Aprire il progetto del servizio. Per implementare il servizio di individuazione personalizzato vengono utilizzati i tre file seguenti:  
  
1. **AsyncResult.cs**: Si tratta dell'implementazione del `AsyncResult` richiesta dai metodi di individuazione.  
  
2. **CustomDiscoveryService.cs**: Questo file implementa il servizio di individuazione personalizzato. L'implementazione estende la classe <xref:System.ServiceModel.Discovery.DiscoveryService> ed esegue l'override dei metodi necessari. Si noti l'implementazione del metodo <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A>. Il metodo esegue un controllo per determinare se la corrispondenza degli ambiti personalizzata definita da una regola è stata specificata dal client. Si tratta dello stesso URI personalizzato specificato dal client in precedenza. Se la regola personalizzata viene specificata, verrà seguito il percorso del codice che implementa la logica di corrispondenza "OR".  
  
     Questa logica personalizzata passa attraverso tutti gli ambiti in ognuno degli endpoint di cui dispone il servizio. Se uno degli ambiti dell'endpoint corrisponde a uno qualsiasi degli ambiti forniti dal client, il servizio di individuazione aggiungerà tale endpoint alla risposta restituita al client.  
  
3. **CustomDiscoveryExtension.cs**: L'ultimo passaggio nell'implementazione del servizio di individuazione consiste nel connettere questa implementazione personalizzato Individuazione servizio all'host del servizio. La classe di supporto utilizzata in questo caso è `CustomDiscoveryExtension`. Questa classe estende la classe <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension>. È necessario che l'utente esegua l'override del metodo <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension.GetDiscoveryService%2A>. In questo caso, il metodo restituisce un'istanza del servizio di individuazione personalizzato creato in precedenza. `PublishedEndpoints` è un oggetto <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> che contiene tutti gli endpoint dell'applicazione che vengono aggiunti a <xref:System.ServiceModel.ServiceHost>. Il servizio di individuazione personalizzato utilizza questo oggetto per popolare l'elenco interno. Un utente ha la possibilità di aggiungere altri metadati dell'endpoint.  
  
 Aprire infine Program.cs. Si noti che <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> e `CustomDiscoveryExtension` vengono entrambi aggiunti all'host. Dopo avere eseguito questa operazione e aver fatto in modo che l'host disponga di un endpoint sul quale ricevere messaggi di individuazione, l'applicazione potrà utilizzare il servizio di individuazione personalizzato.  
  
 Si osservi che il client è in grado di trovare il servizio senza conoscerne l'indirizzo.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Aprire la soluzione contenente il progetto.  
  
2. Compilare il progetto.  
  
3. Eseguire l'applicazione del servizio.  
  
4. Eseguire l'applicazione client.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\CustomFindCriteria`
