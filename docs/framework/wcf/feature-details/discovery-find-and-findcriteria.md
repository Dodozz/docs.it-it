---
title: Ricerca di individuazione e FindCriteria
ms.date: 03/30/2017
ms.assetid: 99016fa4-1778-495b-b4cc-0e22fbec42c6
ms.openlocfilehash: 097027026afa6099f85dee1485fa3a451bb8fefd
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912691"
---
# <a name="discovery-find-and-findcriteria"></a>Ricerca di individuazione e FindCriteria
Un'operazione di ricerca dell'individuazione viene inizializzata da un client per individuare uno o più servizi ed è una delle azioni principali nell'ambito dell'individuazione. L'esecuzione di una ricerca invia un messaggio WS-Discovery Probe sulla rete. I servizi che corrispondono ai criteri specificati inviano una risposta con i messaggi WS-Discovery ProbeMatch. Per altre informazioni sui messaggi di individuazione, vedere la [specifica WS-Discovery](https://go.microsoft.com/fwlink/?LinkID=122347).  
  
## <a name="discoveryclient"></a>DiscoveryClient  
 La classe <xref:System.ServiceModel.Discovery.DiscoveryClient> fornisce il meccanismo necessario per eseguire operazioni di ricerca e agevola l'esecuzione delle operazioni del client di individuazione. Contiene un metodo <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> che esegue una ricerca sincrona (bloccante) scoperta e un metodo <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> che viene inizializzato con una ricerca asincrona non bloccante. Entrambi i metodi utilizzano un parametro <xref:System.ServiceModel.Discovery.FindCriteria> e forniscono risultati all'utente tramite un oggetto <xref:System.ServiceModel.Discovery.FindResponse>.  
  
## <a name="findcriteria"></a>FindCriteria  
 <xref:System.ServiceModel.Discovery.FindCriteria> dispone di varie proprietà, raggruppabili in criteri di ricerca, che specificano i servizi ricercati e cercano criteri di terminazione (durata della ricerca). Un elemento <xref:System.ServiceModel.Discovery.FindCriteria> può contenere più criteri di ricerca. Per impostazione predefinita, il servizio deve individuare corrispondenze per tutti i componenti. In caso contrario, non viene considerato un servizio corrispondente. Se si desidera cercare servizi che corrispondono solo a determinati criteri, è possibile implementare la logica di ricerca personalizzata nel servizio oppure utilizzare più query.  
  
 I criteri di ricerca includono:  
  
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement> - Facoltativo. Nome del contratto del servizio cercato e criteri in genere utilizzati in fase di ricerca di un servizio. Se viene specificato più di un nome di contratto, verrà inviata una risposta solo dagli endpoint del servizio corrispondenti a TUTTI i contratti. Si noti che in WCF un endpoint può supportare un solo contratto.  
  
- <xref:System.ServiceModel.Discovery.Configuration.ScopeElement> - Facoltativo. Gli ambiti sono URI assoluti utilizzati per suddividere in categorie singoli endpoint servizio. Potrebbe risultare opportuno utilizzare questo ambito negli scenari in cui più endpoint espongono lo stesso contratto e si desidera un metodo di ricerca di un subset degli endpoint. Se viene specificato più di un ambito, verrà inviata una risposta solo dagli endpoint del servizio corrispondenti a TUTTI gli ambiti.  
  
- <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchBy%2A> - Specifica l'algoritmo di corrispondenza da utilizzare per individuare la corrispondenza tra l'ambito nel messaggio del Probe e quello dell'endpoint. Sono supportate cinque regole di corrispondenza degli ambiti:  
  
    - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByExact?displayProperty=nameWithType> esegue un confronto di base tra le stringhe con distinzione tra maiuscole e minuscole.  
  
    - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix?displayProperty=nameWithType> corrispondenze dai segmenti separati da "/". Cercando `http://contoso/building1` corrisponde a un servizio con ambito `http://contoso/building/floor1`. Si noti che non corrispondono `http://contoso/building100` perché gli ultimi due segmenti non corrispondono.  
  
    - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByLdap?displayProperty=nameWithType> individua la corrispondenza degli ambiti in base ai segmenti utilizzando un URL LDAP.  
  
    - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByUuid?displayProperty=nameWithType> individua la corrispondenza esatta degli ambiti utilizzando una stringa UUID.  
  
    - <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByNone?displayProperty=nameWithType> individua la corrispondenza con i soli servizi che non specificano un ambito.  
  
     Se non si specifica una regola di corrispondenza degli ambiti, verrà utilizzato <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix>.  
  
 I criteri di terminazione includono:  
  
1. <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> - Tempo massimo di attesa di risposte dai servizi in una rete. La durata predefinita è 20 secondi.  
  
2. <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> - Numero massimo di risposte da attendere. Se le risposte <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> vengono ricevute prima della scadenza specificata dalla proprietà <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>, l'operazione di ricerca termina.  
  
## <a name="findresponse"></a>FindResponse  
 <xref:System.ServiceModel.Discovery.FindResponse> dispone di una proprietà della raccolta <xref:System.ServiceModel.Discovery.FindResponse.Endpoints%2A> che contiene qualsiasi replica inviata da servizi corrispondenti sulla rete. Se nessun servizio invia una risposta, la raccolta è vuota. Se uno o più servizi inviano una risposta, ogni replica viene archiviata in un oggetto <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> che contiene l'indirizzo, il contratto e alcune informazioni aggiuntive sul servizio.  
  
 Nell'esempio seguente viene mostrato come eseguire un'operazione di ricerca nel codice.  
  
```  
// Create DiscoveryClient  
DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
// Create FindCriteria  
FindCriteria findCriteria = new FindCriteria(typeof(IPrinterService));  
findCriteria.Scopes.Add(new Uri("http://www.contoso.com/building1/floor1"));  
findCriteria.Duration = TimeSpan.FromSeconds(10);   
  
// Find ICalculatorService endpoints              
FindResponse findResponse = discoveryClient.Find(findCriteria);  
  
Console.WriteLine("Found {0} ICalculatorService endpoint(s).", findResponse.Endpoints.Count)  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di WCF Discovery](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Utilizzo del canale client di individuazione](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
- [Individuazione con ambiti](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)
- [Funzionalità di base](../../../../docs/framework/wcf/samples/basic-sample.md)
