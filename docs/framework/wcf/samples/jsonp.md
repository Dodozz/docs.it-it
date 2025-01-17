---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: 37da57a000376f972cd6da9e04be46ddec1b7144
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989885"
---
# <a name="jsonp"></a>JSONP
In questo esempio viene illustrato come supportare JSONP (JSON with Padding) nei servizi WCF REST. JSONP è una convenzione usata per richiamare script tra domini mediante la generazione di tag script nel documento corrente. Il risultato viene restituito in una funzione di callback specificata. JSONP si basa sul concetto che tag quali `<script src="http://..." >` grado di valutare script da ogni dominio e che lo script recuperato da tali tag venga valutato all'interno di un ambito in cui altre funzioni possono essere già definite.

## <a name="demonstrates"></a>Dimostrazione
 Generazione di script tra domini con JSONP.

## <a name="discussion"></a>Discussione
 Nell'esempio è inclusa una pagina Web che aggiunge dinamicamente un blocco di script dopo il rendering della pagina nel browser. Questo blocco di script chiama un servizio WCF REST che dispone di una sola operazione, ovvero `GetCustomer`. Il servizio WCF REST restituisce il nome e l'indirizzo di un cliente incapsulati in un nome di funzione di callback. Quando il servizio WCF REST risponde, la funzione di callback nella pagina Web viene richiamata con i dati del cliente e la funzione di callback visualizza i dati nella pagina Web. L'inserimento del tag script e l'esecuzione della funzione di callback vengono gestite automaticamente dal controllo ScriptManager di AJAX ASP.NET. Il modello di utilizzo è lo stesso di tutti i proxy AJAX ASP.NET, con l'aggiunta di una riga per l'abilitazione di JSONP, come illustrato nel codice seguente:

```csharp
var proxy = new JsonpAjaxService.CustomerService();
proxy.set_enableJsonp(true);
proxy.GetCustomer(onSuccess, onFail, null);
```

 La pagina Web può chiamare il servizio WCF REST perché il servizio sta usando <xref:System.ServiceModel.Description.WebScriptEndpoint> con `crossDomainScriptAccessEnabled` impostato su `true`. Entrambe queste configurazioni vengono eseguite nel file Web. config sotto il \<System. ServiceModel > elemento.

```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

 ScriptManager gestisce l'interazione con il servizio non rivelando la complessità dell'implementazione manuale dell'accesso JSONP. Quando `crossDomainScriptAccessEnabled` è impostata su `true` e il formato della risposta per un'operazione è JSON, l'infrastruttura WCF esamina l'URI della richiesta per un parametro di stringa di query di callback ed esegue il wrapping della risposta JSON con il valore della stringa di query di callback parametro. Nell'esempio la pagina Web chiama il servizio WCF REST con l'URI seguente:

```
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0
```

 Poiché il parametro della stringa di query di callback dispone di un valore `JsonPCallback`, il servizio WCF restituisce la risposta JSONP illustrata nell'esempio seguente.

```
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});
```

 Questa risposta JSONP include i dati del cliente formattati come JSON, di cui è stato eseguito il wrapping con il nome della funzione di callback richiesta dalla pagina Web. ScriptManager eseguirà questo callback usando un tag script per portare a termine la richiesta tra domini, quindi passerà il risultato al gestore onSuccess passato all'operazione GetCustomer del proxy AJAX ASP.NET.

 L'esempio è costituito da due applicazioni web ASP.NET: una contiene solo un servizio WCF e un'altra contiene la pagina Web. aspx, che chiama il servizio. Quando si esegue la soluzione, Visual Studio 2012 ospiterà i due siti Web su porte diverse, che consente di creare un ambiente in cui il servizio e client presenti in domini diversi.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1. Aprire la soluzione per l'esempio relativo a JSONP.  
  
2. Premere F5 per avviare `http://localhost:26648/JSONPClientPage.aspx` nel browser.  
  
3. Si noti che dopo il caricamento della pagina, gli input di testo per "Name" e "Address" vengono popolati dai valori.  Questi valori vengono forniti da una chiamata al servizio WCF dopo che il browser ha completato il rendering della pagina.
