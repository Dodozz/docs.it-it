---
title: Scelta di un filtro
ms.date: 03/30/2017
ms.assetid: 67ab5af9-b9d9-4300-b3b1-41abb5a1fd10
ms.openlocfilehash: f634363a3f8b69b38fd4d313c42de4d742d94acc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514193"
---
# <a name="choosing-a-filter"></a>Scelta di un filtro
Quando si configura il servizio di routing, è importante selezionare i filtri messaggi corretti e configurarli per consentire l'individuazione di corrispondenze esatte con i messaggi ricevuti. Se i filtri selezionati non sono sufficientemente precisi o non sono configurati correttamente, i messaggi vengono indirizzati in modo non corretto. Se i filtri sono troppo restrittivi, è possibile che non vengano individuate route valide disponibili per alcuni messaggi.  
  
## <a name="filter-types"></a>Tipo di filtro  
 Se si selezionano filtri utilizzati dal servizio di routing, è importante comprenderne il funzionamento ed essere a conoscenza delle informazioni disponibili all'interno dei messaggi in ingresso. Se ad esempio tutti i messaggi vengono ricevuti sullo stesso endpoint, i filtri Address e EndpointName non sono utili perché tutti i messaggi corrispondono a questi filtri.  
  
### <a name="action"></a>Operazione  
 Il filtro Action controlla la proprietà <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A>. Se il contenuto dell'intestazione Action nel messaggio corrisponde al valore dei dati specificato nella configurazione del filtro, viene restituito `true`. L'esempio seguente definisce una `FilterElement` che utilizza il filtro Action per individuare i messaggi con un'intestazione action che contiene un valore di `http://namespace/contract/operation/`.
  
```xml  
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/" />  
```  
  
```csharp  
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });  
```  
  
 Questo filtro deve essere utilizzato per il routing dei messaggi contenenti un'intestazione Action univoca.  
  
### <a name="endpointaddress"></a>EndpointAddress  
 Il filtro EndpointAddress controlla il valore EndpointAddress indicante l'indirizzo di ricezione del messaggio. Se l'indirizzo a cui arriva il messaggio corrisponde esattamente all'indirizzo specificato nella configurazione del filtro, quest'ultimo restituisce `true`. L'esempio seguente definisce una `FilterElement` che utilizza il filtro dell'indirizzo per individuare i messaggi indirizzati a "http://\<nome host > / vdir/s.svc/b".  
  
```xml  
<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b" />  
```  
  
```csharp  
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
```  
  
> [!NOTE]
>  È importante notare che la parte del nome host di un indirizzo può differire a seconda che il client utilizzi il nome di dominio completo, il nome NetBIOS, l'indirizzo IP o un altro nome. Poiché valori diversi possono fare riferimento allo stesso host, il comportamento predefinito per questo confronto non prevede l'utilizzo della parte del nome host dell'indirizzo per individuare le corrispondenze.  
>   
>  È possibile modificare questo comportamento per consentire la valutazione del nome host nel confronto quando si configura il servizio di routing a livello di codice.  
  
 È consigliabile utilizzare questo filtro quando i messaggi in ingresso vengono indirizzati a un indirizzo univoco.  
  
### <a name="endpointaddressprefix"></a>EndpointAddressPrefix  
 Il filtro EndpointAddressPrefix è analogo al filtro EndpointAddress. Il filtro EndpointAddressPrefix controlla il valore EndpointAddress indicante l'indirizzo di ricezione del messaggio. Tuttavia, il filtro EndpointAddressPrefix viene utilizzato come un carattere jolly che individua le corrispondenze con gli indirizzi che iniziano con il valore specificato nella configurazione del filtro. L'esempio seguente definisce una `FilterElement` che utilizza il filtro EndpointAddressPrefix per individuare i messaggi indirizzati a `http://<hostname>/vdir*`.  
  
```xml  
<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/vdir" />  
```  
  
```csharp  
PrefixEndpointAddressMessageFilter prefix1 = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
```  
  
> [!NOTE]
>  È importante notare che la parte del nome host di un indirizzo può differire a seconda che il client utilizzi il nome di dominio completo, il nome NetBIOS, l'indirizzo IP o un altro nome. Poiché valori diversi possono fare riferimento allo stesso host, il comportamento predefinito per questo confronto non prevede l'utilizzo della parte del nome host dell'indirizzo per individuare le corrispondenze.  
  
 È consigliabile utilizzare questo filtro per il routing dei messaggi in ingresso che condividono un prefisso di indirizzo comune.  
  
### <a name="and"></a>AND  
 Il filtro AND non applica direttamente il filtro in base a un valore all'interno di un messaggio, ma consente di combinare due altri filtri per creare una condizione `AND` in cui entrambi i filtri devono corrispondere al messaggio affinché venga restituito `true`. In questo modo è possibile creare filtri complessi che prevedono la corrispondenza dei messaggi con tutti i sottofiltri. Nell'esempio seguente vengono definiti un filtro indirizzo e un filtro Action, quindi viene definito un filtro AND che valuta un messaggio in base sia al filtro indirizzo sia a quello azione. Se entrambi i filtri corrispondono, il filtro AND restituisce `true`.  
  
```xml  
<filter name="address1" filterType="AddressPrefix" filterData="http://host/vdir"/>  
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/"/>  
<filter name="and1" filterType="And" filter1="address1" filter2="action1" />  
```  
  
```csharp  
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });  
StrictAndMessageFilter and1=new StrictAndMessageFilter(address1, action1);  
```  
  
 È consigliabile utilizzare questo filtro quando è necessario combinare la logica di più filtri per determinare quando si verifica una corrispondenza. Se ad esempio si dispone di più destinazioni che devono ricevere solo determinate combinazioni di azioni e messaggi a specifici indirizzi, è possibile utilizzare un filtro AND per combinare i filtri indirizzo e azione necessari.  
  
### <a name="custom"></a>Personalizzato  
 Quando si seleziona il tipo di filtro Custom, è necessario fornire un valore customType contenente il tipo dell'assembly che contiene il **MessageFilter** implementazione da utilizzare per il filtro. Inoltre, filterData deve contenere qualsiasi valore necessario per la valutazione dei messaggi da parte del filtro personalizzato. Nell'esempio seguente viene definito un elemento `FilterElement` che utilizza l'implementazione di MessageFilter `CustomAssembly.MyCustomMsgFilter`.  
  
```xml  
<filter name="custom1" filterType="Custom" customType="CustomAssembly.MyCustomMsgFilter, CustomAssembly" filterData="Custom Data" />  
```  
  
```csharp  
MyCustomMsgFilter custom1=new MyCustomMsgFilter("Custom Data");  
```  
  
 Se è necessario eseguire la logica di corrispondenza personalizzata rispetto a un messaggio che non è coperto dai filtri forniti con [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], è necessario creare un filtro personalizzato che è un'implementazione del **MessageFilter** classe. È ad esempio possibile creare un filtro personalizzato che confronta un campo nel messaggio in ingresso rispetto a un elenco di valori noti specificato nella configurazione del filtro o che esegue l'hashing di un messaggio e quindi esamina il valore per determinare se il filtro deve restituire `true` o `false`.  
  
### <a name="endpointname"></a>EndpointName  
 Il filtro EndpointName controlla il nome dell'endpoint che ha ricevuto il messaggio. L'esempio seguente definisce un `FilterElement` che utilizza il filtro EndpointName per instradare i messaggi ricevuti su "SvcEndpoint".  
  
```xml  
<filter name="name1" filterType="Endpoint" filterData="SvcEndpoint" />  
```  
  
```csharp  
EndpointNameMessageFilter name1 = new EndpointNameMessageFilter("SvcEndpoint");  
```  
  
 Questo filtro è utile quando il servizio di routing espone più endpoint servizio denominati. È ad esempio possibile esporre due endpoint che il servizio di routing utilizza per ricevere messaggi; uno per i clienti prioritari per i quali è necessaria elaborazione in tempo reale dei messaggi, l'altro per la ricezione dei messaggi non dipendenti dal tempo.  
  
 Sebbene sia spesso possibile utilizzare la corrispondenza dell'indirizzo completa per determinare l'endpoint di ricezione di un messaggio, l'utilizzo del nome dell'endpoint risulta più pratico ed è meno soggetto a errori, in particolare quando si configura un servizio di routing con un file di configurazione (in cui i nomi degli endpoint sono un attributo obbligatorio).  
  
### <a name="matchall"></a>MatchAll  
 Il filtro MatchAll corrisponde a tutti i messaggi ricevuti. È utile se è necessario indirizzare sempre tutti i messaggi ricevuti a un endpoint specifico, ad esempio un servizio di registrazione che archivia una copia di tutti i messaggi ricevuti. Nell'esempio seguente viene definito un elemento `FilterElement` che utilizza il filtro MatchAll.  
  
```xml  
<filter name="matchAll1" filterType="MatchAll" />  
```  
  
```csharp  
MatchAllMessageFilter matchAll1 = new MatchAllMessageFilter();  
```  
  
### <a name="xpath"></a>XPath  
 Il filtro XPath consente di specificare una query XPath utilizzata per controllare un elemento specifico all'interno del messaggio. L'applicazione di filtri XPath rappresenta un'opzione particolarmente efficace per consentire il controllo diretto di qualsiasi voce indirizzabile XML nel messaggio, tuttavia richiede una conoscenza specifica della struttura dei messaggi in ricezione. L'esempio seguente definisce un `FilterElement` che utilizza il filtro XPath per controllare il messaggio per un elemento denominato "element" all'interno dello spazio dei nomi fa riferimento il prefisso dello spazio dei nomi "ns".  
  
```xml  
<filter name="xpath1" filterType="XPath" filterData="//ns:element" />  
```  
  
```csharp  
XPathMessageFilter xpath1=new XPathMessageFilter("//ns:element");  
```  
  
 Questo filtro è utile se si è certi che i messaggi in ricezione contengono un determinato valore. Se ad esempio si ospitano due versioni dello stesso servizio e si sa che messaggi indirizzati alla versione più recente del servizio contengono un valore univoco in un'intestazione personalizzata, è possibile creare un filtro che utilizza XPath per passare a questa intestazione e confrontare il valore presente nell'intestazione con un altro specificato nella configurazione del filtro per determinare le corrispondenze.  
  
 Poiché le query XPath spesso contengono spazi dei nomi univoci, che spesso sono valori stringa lunghi o complessi, il filtro XPath consente di utilizzare la tabella degli spazi dei nomi per definire prefissi univoci per gli spazi dei nomi. Per altre informazioni sulla tabella dello spazio dei nomi, vedere [filtri messaggi](../../../../docs/framework/wcf/feature-details/message-filters.md).  
  
 Per altre informazioni sulla progettazione di query XPath, vedere [sintassi di XPath](https://go.microsoft.com/fwlink/?LinkId=164592).  
  
## <a name="see-also"></a>Vedere anche
- [Filtri per messaggi](../../../../docs/framework/wcf/feature-details/message-filters.md)
- [Procedura: Usare i filtri](../../../../docs/framework/wcf/feature-details/how-to-use-filters.md)
