---
title: Protocolli di messaggistica
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: a5292914cfebc79bf8a9af1c852dd8feec99eba4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948122"
---
# <a name="messaging-protocols"></a>Protocolli di messaggistica

Lo stack di canale Windows Communication Foundation (WCF) utilizza i canali di codifica e di trasporto per trasformare rappresentazioni interne dei messaggi in formato di trasmissione e inviarlo tramite un determinato trasporto. Il trasporto più comunemente utilizzato per garantire l'interoperabilità dei servizi Web è il protocollo HTTP, mentre le codifiche utilizzate dai servizi Web sono in genere SOAP 1.1 basato su XML, SOAP 1.2 e il protocollo MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi).

In questo argomento vengono descritti i dettagli di implementazione WCF per i protocolli seguenti usati da <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.

Specifica o documento:

- [HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)
- [Associazione SOAP 1,1 HTTP](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), sezione 7
- [Associazione SOAP 1,2 HTTP](https://www.w3.org/TR/soap12-part2) sezione 7

In questo argomento vengono descritti i dettagli di implementazione di WCF per i seguenti protocolli <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> e <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> impiegare.

Specifica o documento:

- [XML](https://www.w3.org/TR/REC-xml)
- [SOAP 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)
- [SOAP 1.2 Core](https://www.w3.org/TR/soap12-part1/)
- [WS-Addressing 2004/08](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)
- [W3C Web Services Addressing 1.0 - Core](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509)
- [W3C Web Services Addressing 1.0 - SOAP Binding](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509)
- [W3C Web Services Addressing 1.0 - WSDL Binding](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)
- [W3C Web Services Addressing 1.0 - Metadata](https://www.w3.org/TR/ws-addr-metadata/)
- [Associazione WSDL SOAP1.1](https://www.w3.org/TR/wsdl/)
- [Associazione WSDL SOAP1.2](https://www.w3.org/Submission/wsdl11soap12/)

In questo argomento vengono descritti i dettagli di implementazione di WCF per i seguenti protocolli <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> impiega.

Specifica o documento:

- [XOP](https://www.w3.org/TR/xop10/)
- [MTOM SOAP 1.2 di associazione](https://www.w3.org/TR/soap12-mtom/)
- [Associazione MTOM SOAP 1.1](https://www.w3.org/Submission/soap11mtom10/)
- [Asserzione di WS-Policy MTOM](https://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/)

In questo argomento vengono utilizzati i seguenti spazi dei nomi XML e i relativi prefissi associati:

| Prefisso | URI (Uniform Resource Identifier) dello spazio dei nomi |
|------------|---------------------------------------------------|
| s11 | `http://schemas.xmlsoap.org/soap/envelope` |
| s12 |`http://www.w3.org/2003/05/soap-envelope` |
| wsa |`http://www.w3.org/2004/08/addressing` |
| wsam |`http://www.w3.org/2007/05/addressing/metadata` |
| wsap |`http://schemas.xmlsoap.org/ws/2004/09/policy/addressing` |
| wsa10 |`http://www.w3.org/2005/08/addressing` |
| wsaw10 |`http://www.w3.org/2006/05/addressing/wsdl` |
| xop |`http://www.w3.org/2004/08/xop/include` |
| xmime |`http://www.w3.org/2004/06/xmlmime`<br /><br /> `http://www.w3.org/2005/05/xmlmime` |
| dp |`http://schemas.microsoft.com/net/2006/06/duplex` |

## <a name="soap-11-and-soap-12"></a>SOAP 1.1 e SOAP 1.2

### <a name="envelope-and-processing-model"></a>Modello di elaborazione della envelope
WCF implementa l'elaborazione di envelope di SOAP 1.1 seguendo Basic Profile 1.1 (BP11) e Basic Profile 1.0 (SSBP10). L'elaborazione della SOAP 1.2 envelope viene implementata attenendosi alla specifica SOAP12-Part1.

Questa sezione illustra alcune scelte di implementazione da WCF in relazione alle specifiche BP11 e SOAP12-Part1.

#### <a name="mandatory-header-processing"></a>Elaborazione obbligatoria delle intestazioni
WCF segue le regole per l'elaborazione di intestazioni contrassegnate `mustUnderstand` descritto nelle specifiche SOAP 1.1 e SOAP 1.2, con le variazioni seguenti.

Un messaggio che viene inserito lo stack dei canali WCF viene elaborato da canali specifici configurati in base agli elementi di associazione associata, ad esempio, codifica del messaggio di testo, sicurezza, messaggistica affidabile e le transazioni. Ogni canale riconosce le intestazioni dallo spazio dei nomi associato e le contrassegna come riconosciute. Dopo l'inserimento di un messaggio nel dispatcher, il formattatore dell'operazione legge le intestazioni previste dal contratto di messaggio/operazione corrispondente e le contrassegna come riconosciute. Quindi, il dispatcher verifica se esistono intestazioni non riconosciute ma la cui intestazione `mustUnderstand` richiede il riconoscimento e, in tal caso, genera un'eccezione. I messaggi che contengono intestazioni `mustUnderstand` indirizzate al destinatario non vengono elaborati dal codice dell'applicazione di destinazione.

Questo tipo di elaborazione a livelli consente la separazione fra i livelli di infrastruttura e livelli di applicazione del nodo SOAP:

- B1111: Le intestazioni non riconosciute vengono rilevate dopo che il messaggio viene elaborato dallo stack dei canali WCF dell'infrastruttura, ma prima che venga elaborato dall'applicazione

     Il valore dell'intestazione `mustUnderstand` differisce tra SOAP 1.1 e SOAP 1.2. Basic Profile 1.1 richiede che il valore di `mustUnderstand` sia 0 o 1 per i messaggi SOAP 1.1. La specifica di SOAP 1.2, oltre ai valori 0 e 1, prevede inoltre i valori `false` e `true`. Tuttavia, tale specifica consiglia di applicare una rappresentazione canonica dei valori `xs:boolean`, ovvero `false` e `true`.

- B1112: Generato da WCF `mustUnderstand` valori 0 e 1 per le versioni sia di SOAP 1.1 e SOAP 1.2 della SOAP envelope. WCF accetta l'intero spazio dei valori `xs:boolean` per il `mustUnderstand` intestazione (0, 1, `false`, `true`)

#### <a name="soap-faults"></a>Errori SOAP
Di seguito è un elenco delle implementazioni di errore SOAP WCF specifico.

- B2121: Poiché WCF restituisce i seguenti codici di errore SOAP 1.1: `s11:mustUnderstand`, `s11:Client`, e `s11:Server`.

- B2122: Poiché WCF restituisce i seguenti codici di errore SOAP 1.2: `s12:MustUnderstand`, `s12:Sender`, e `s12:Receiver`.

### <a name="http-binding"></a>Associazione HTTP

#### <a name="soap-11-http-binding"></a>Associazione SOAP 1,1 HTTP
WCF implementa associazione SOAP 1.1 HTTP dopo la specifica Basic Profile 1.1 sezione 3.4 con le precisazioni seguenti:

- B2211: Servizio WCF può neimplementuje metodu reindirizzamento delle richieste HTTP POST.

- B2212: I client WCF supportano i cookie HTTP in conformità alla sezione 3.4.8.

#### <a name="soap-12-http-binding"></a>Associazione SOAP 1,2 HTTP
WCF implementa l'associazione SOAP 1.2 HTTP come descritto nella SOAP 1.2-part 2 (SOAP12Part2) specifica con le precisazioni seguenti.

SOAP 1.2 introduce un nuovo parametro Action facoltativo per il tipo di supporto `application/soap+xml`. Questo parametro è utile per ottimizzare l'invio dei messaggi in quanto elimina l'esigenza di analizzare il corpo del messaggio SOAP quando non si utilizza la specifica WS-Addressing.

- R2221: Il `application/soap+xml` parametro action, quando presente in una richiesta SOAP 1.2, deve corrispondere il `soapAction` attributo il `wsoap12:operation` elemento all'interno di associazione WSDL corrispondente.

- R2222: Il `application/soap+xml` parametro action, quando presente in un messaggio SOAP 1.2, deve corrispondere `wsa:Action` quando vengono utilizzati WS-Addressing 2004/08 o WS-Addressing 1.0.

Quando la specifica WS-Addressing è disabilitata e in una richiesta in ingresso non è incluso alcun parametro Action, il parametro `Action` del messaggio viene considerato come non specificato.

## <a name="ws-addressing"></a>WS-Addressing
WCF di implementare 3 versioni di WS-Addressing:

- WS-Addressing 2004/08

- Specifica di base di W3C Web Services Addressing 1.0 (ADDR10-CORE) e associazione SOAP (ADDR10-SOAP)

- WS-Addressing 1.0 - Metadata

### <a name="endpoint-references"></a>Riferimenti a endpoint
Tutte le versioni di WS-Addressing che WCF implementa usano riferimenti a endpoint per descrivere gli endpoint.

#### <a name="endpoint-references-and-ws-addressing-versions"></a>Utilizzo dei riferimenti a endpoint con le versioni di WS-Addressing
WCF implementa diversi protocolli di infrastruttura che utilizzano WS-Addressing e in particolare il `EndpointReference` elemento e `W3C.WsAddressing.EndpointReferenceType` classe (ad esempio, WS-ReliableMessaging WS-SecureConversation e WS-Trust). WCF supporta l'utilizzo di entrambe le versioni di WS-Addressing con gli altri protocolli di infrastruttura. Gli endpoint WCF supportano una versione di WS-Addressing per ogni endpoint.

R3111: lo spazio dei nomi per il `EndpointReference` elemento o del tipo utilizzato nei messaggi scambiati con un endpoint WCF deve corrispondere alla versione di WS-Addressing implementata da questo endpoint.

Ad esempio, se un endpoint WCF implementa WS-ReliableMessaging, il `AcksTo` intestazione restituita da tale endpoint all'interno `CreateSequenceResponse` Usa la versione di WS-Addressing che il `EncodingBinding` elemento specifica per questo endpoint.

#### <a name="endpoint-references-and-metadata"></a>Utilizzo dei riferimenti a endpoint con i metadati
Diversi scenari richiedono la comunicazione di metadati o di riferimenti a metadati relativi a un dato endpoint.

B3121: WCF utilizza i meccanismi descritti nella sezione 6 di includere i metadati per i riferimenti all'endpoint per valore o per riferimento specifica WS-MetadataExchange (MEX).

Si consideri uno scenario in cui un servizio WCF richiede l'autenticazione tramite un token Security Assertions Markup Language (SAML) emesso dall'emittente del token a `http://sts.fabrikam123.com`. L'endpoint WCF descrive questo requisito di autenticazione utilizzando `sp:IssuedToken` asserzione con nidificato `sp:Issuer` asserzione che punta all'emittente del token. Le applicazioni client che accedono all'asserzione `sp:Issuer` devono conoscere la modalità di comunicazione con l'endpoint dell'emittente di token. In particolare, il client deve conoscere i metadati relativi all'emittente di token. Usa le estensioni dei metadati di riferimento endpoint definite nel MEX, WCF fornisce un riferimento ai metadati dell'emittente del token.

```xml
<sp:IssuedToken>
  <sp:Issuer>
    <wsa10:Address>
      http://sts.fabrikam123.com
    </wsa10:Address>
    <wsa10:Metadata>
      <mex:Metadata>
        <mex:MetadataSection>
          <mex:MetadataReference>
            <wsa10:Address>
              http://sts.fabrikam123.com/mex
            </wsa10:Address>
          </mex:MetadataReference>
        </mex:MetadataSection>
      </mex:Metadata>
    </wsa10:Metadata>
  </sp:Issuer>
</sp:IssuedToken>
```

### <a name="message-addressing-headers"></a>Intestazioni di indirizzamento dei messaggi

#### <a name="message-headers"></a>Intestazioni del messaggio
Per entrambe le versioni di WS-Addressing, WCF Usa le seguenti intestazioni del messaggio come previsto dalle specifiche `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, e `wsa:RelatesTo`.

B3211: Per tutte le versioni di WS-Addressing, WCF rispetta, ma non viene generato per impostazione predefinita, le intestazioni dei messaggi WS-Addressing `wsa:FaultTo` e `wsa:From`.

Le applicazioni che interagiscono con le applicazioni WCF possono aggiungere che queste intestazioni del messaggio e WCF verranno elaborate di conseguenza.

#### <a name="reference-parameters-and-properties"></a>Parametri e proprietà dei riferimenti

WCF implementa l'elaborazione dei parametri di riferimento dell'endpoint e le proprietà di riferimento in base alle rispettive specifiche.

B3221: Se è configurato per usare WS-Addressing 2004/08, gli endpoint WCF viene fatta distinzione tra l'elaborazione delle proprietà di riferimento e i parametri per riferimento.

### <a name="message-exchange-patterns"></a>Modelli di scambio dei messaggi
La sequenza dei messaggi coinvolti nella chiamata di operazione del servizio Web è detta il *modello di scambio messaggi*. I modelli di scambio di messaggi duplex WCF supporta unidirezionali e request / reply. Questa sezione descrive i requisiti della specifica WS-Addressing che definiscono il modo in cui il modello di scambio dei messaggi usato influisce sull'elaborazione dei messaggi.

Contenuto della sezione, il richiedente invia il primo messaggio e il risponditore riceve il primo messaggio.

#### <a name="one-way-message"></a>Modello unidirezionale
Quando un endpoint WCF è configurato per supportare messaggi aventi un determinato `Action` per seguire un modello unidirezionale, l'endpoint WCF segue i seguenti comportamenti e requisiti. Salvo diversamente specificato, per entrambe le versioni di WS-Addressing supportate in WCF si applicano i comportamenti e le regole:

- R3311: Il richiedente deve includere `wsa:To`, `wsa:Action`e le intestazioni per tutti i parametri di riferimento specificati dal riferimento all'endpoint. Quando si utilizza la specifica WS-Addressing 2004/08 e il riferimento a endpoint specifica le proprietà di riferimento [reference properties], occorre aggiungere al messaggio anche le intestazioni corrispondenti.

- B3312: Il richiedente può includere `MessageID`, `ReplyTo`, e `FaultTo` intestazioni. Dopo essere stati ignorati dall'infrastruttura del destinatario, questi elementi vengono passati all'applicazione.

- R3313: Quando viene usato HTTP e non viene inviato alcun messaggio sulla parte della risposta HTTP, il risponditore deve inviare una risposta HTTP con un corpo vuoto e un codice di stato HTTP 202.

     Quando si utilizza il trasporto HTTP e il contratto dell'operazione dichiara un messaggio unidirezionale, la risposta HTTP può comunque essere utilizzata per l'invio di messaggi di infrastruttura. Ad esempio, la funzionalità di messaggistica affidabile può inviare un messaggio `SequenceAcknowledgement` in una risposta HTTP.

- B3314: Il risponditore WCF non invia un messaggio di errore in risposta a un messaggio unidirezionale.

#### <a name="request-reply"></a>Request/Reply
Quando un endpoint WCF è configurato per un messaggio con un determinato `Action` per seguire il modello request / reply, l'endpoint WCF attiene ai comportamenti e requisiti riportati di seguito. Se non specificato diversamente, si applicano le regole e i comportamenti per entrambe le versioni di WS-Addressing supportate in WCF:

- R3321: Il richiedente deve includere nella richiesta `wsa:To`, `wsa:Action`, `wsa:MessageID`e le intestazioni per tutti i parametri per riferimento oppure riferimento proprietà (o entrambi) specificati nel riferimento a endpoint.

- R3322: Quando viene usato WS-Addressing 2004/08, `ReplyTo` deve essere incluso anche nella richiesta.

- R3323: Quando si utilizza WS-Addressing 1.0 e `ReplyTo` non è presente nella richiesta, un riferimento all'endpoint predefinito con la proprietà [address] uguale a `http://www.w3.org/2005/08/addressing/anonymous` viene usato.

- R3324: Il richiedente deve includere `wsa:To`, `wsa:Action`, e `wsa:RelatesTo` intestazioni nel messaggio di risposta, nonché le intestazioni per tutti i parametri per riferimento oppure riferimento proprietà (o entrambi) specificato da di `ReplyTo` riferimento dell'endpoint nella richiesta.

### <a name="web-services-addressing-faults"></a>Errori di indirizzamento dei servizi Web
R3411: WCF genera gli errori seguenti definiti da WS-Addressing 2004/08.

| Codice | Causa |
|----------|-----------|
| `wsa:DestinationUnreachable` | Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale. Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione. |
| `wsa:ActionNotSupported` | I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`. |

R3412: WCF genera gli errori seguenti definiti da WS-Addressing 1.0.

| Codice | Causa |
|----------|-----------|
| `wsa10:InvalidAddressingHeader` | Duplica `wsa:To`, `wsa:ReplyTo`, `wsa:From` o `wsa:MessageID`. Duplica `wsa:RelatesTo` con lo stesso `RelationshipType`. |
| `wsa10:MessageAddressingHeaderRequired` | L'intestazione obbligatoria di indirizzamento è mancante. |
| `wsa10:DestinationUnreachable` | Il messaggio in ingresso presenta un riferimento `ReplyTo` diverso dall'indirizzo per risposte definito per questo canale. Non esiste alcun endpoint in attesa presso l'indirizzo specificato nell'intestazione di destinazione. |
| `wsa10:ActionNotSupported` | I canali dell'infrastruttura o il dispatcher associato all'endpoint non riconoscono l'azione specificata nell'intestazione `Action`. |
| `wsa10:EndpointUnavailable` | Il canale RM restituisce questo errore per indicare che l'endpoint non elaborerà la sequenza basata sull'esame delle intestazioni di indirizzamento del messaggio `CreateSequence`. |

Il codice delle tabelle precedenti viene mappato al codice `FaultCode` in SOAP 1.1 e al codice `SubCode` (in cui il codice corrisponde al mittente) in SOAP 1.2.

### <a name="wsdl-11-binding-and-ws-policy-assertions"></a>Utilizzo di associazioni WSDL 1.1 con le asserzioni di WS-Policy

#### <a name="indicating-use-of-ws-addressing"></a>Definizione dell'uso di WS-Addressing
WCF utilizza le asserzioni di criteri per indicare il supporto di endpoint per una particolare versione di WS-Addressing.

L'asserzione di criteri seguente contiene il soggetto dei criteri di endpoint [WS-PA] e indica che i messaggi scambiati con l'endpoint devono utilizzare la specifica WS-Addressing 2004/08.

```xml
<wsap:UsingAddressing />
```

Questa asserzione di criteri si aggiunge alla specifica WS-Addressing 2004/08.

Tramite l'asserzione di criteri seguente viene indicato che nei messaggi inviati/ricevuti deve essere utilizzato WS-Addressing 1.0.

```xml
<wsam:Addressing/>
```

Nell'asserzione di criteri seguente è incluso un soggetto dei criteri di endpoint [WS-PA] e viene indicato che nei messaggi scambiati con l'endpoint deve essere utilizzata la specifica WS-Addressing 2004/08.

```xml
<wsaw10:UsingAddressing />
```

L'elemento `wsaw10:UsingAddressing` è preso in prestito da [WS-Addressing-WSDL] e viene utilizzato nel contesto di WS-Policy in conformità alla sezione 3.1.2 di tale specifica.

L'utilizzo dell'intestazione di indirizzamento non modifica la semantica delle associazioni WSDL 1.1 HTTP, SOAP 1.1 HTTP e SOAP 1.2 HTTP. Ad esempio, se si prevede una risposta a una richiesta inviata a un endpoint in cui vengono utilizzati WS-Addressing e l'associazione WSDL SOAP 1.x HTTP, la risposta deve essere inviata tramite la risposta HTTP.

Per le risposte inviate tramite la risposta http, l'asserzione WS-AM è:

```xml
<wsam:AnonymousResponses/>
```

L'asserzione di criteri completa potrebbe essere simile alla seguente:

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:AnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

Tuttavia, sono presenti modelli di scambio dei messaggi che traggono profitto dalla presenza di due connessioni HTTP opposte indipendenti stabilite tra il richiedente e il risponditore, ad esempio i messaggi unidirezionali non richiesti inviati dal risponditore.

WCF offre una funzionalità di base al quale due canali di trasporto sottostanti possono formare un canale Duplex composito, in cui un canale viene utilizzato per i messaggi di input e l'altra viene usata per i messaggi di output. Nel caso del trasporto HTTP, il modello duplex composito offre due connessioni HTTP opposte. Il richiedente utilizza una connessione per inviare i messaggi al risponditore, mentre quest'ultimo utilizza l'altra connessione per inviare i messaggi di risposta al richiedente.

Per le risposte inviate tramite richieste http distinte, l'asserzione ws-am è:

```xml
<wsam:NonAnonymousResponses/>
```

L'asserzione di criteri completa potrebbe essere simile alla seguente:

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:NonAnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

Per l'utilizzo dell'asserzione seguente che presenta il soggetto dei criteri di endpoint [WS-PA] negli endpoint in cui vengono utilizzate le associazioni SOAP 1.x HTTP WSDL 1.1 sono richieste due connessioni HTTP opposte e distinte da utilizzare rispettivamente per i messaggi dal richiedente al risponditore e dal risponditore al richiedente.

```xml
<cdp:CompositeDuplex/>
```

L'istruzione precedente comporta i requisiti seguenti per l'intestazione `wsa:ReplyTo` dei messaggi di richiesta:

- R3514: Richiedere i messaggi inviati a un endpoint devono presentare un `ReplyTo` intestazione con il `[address]` proprietà non è uguale a `http://www.w3.org/2005/08/addressing/anonymous` se l'endpoint utilizza un'associazione WSDL 1.1 SOAP 1.x HTTP e dispone di un'alternativa criteri avente un' `wsap10:UsingAddressing` o `wsap:UsingAddressing` asserzione insieme a `cdp:CompositeDuplex` collegato.

- R3515: Richiedere i messaggi inviati a un endpoint devono presentare un `ReplyTo` intestazione con il `[address]` proprietà è uguale a `http://www.w3.org/2005/08/addressing/anonymous`, o non hanno un `ReplyTo` intestazione affatto, se l'endpoint utilizza un'associazione WSDL 1.1 SOAP 1.x HTTP e dispone di un'alternativa criteri avente `wsap10:UsingAddressing` asserzione e nessun `cdp:CompositeDuplex` asserzione associata.

- R3516: Richiedere i messaggi inviati a un endpoint devono presentare un `ReplyTo` intestazione con un `[address]` uguale alla proprietà `http://www.w3.org/2005/08/addressing/anonymous` se l'endpoint utilizza un'associazione WSDL 1.1 SOAP 1.x HTTP e dispone di un'alternativa criteri avente `wsap:UsingAddressing` asserzione e nessun `cdp:CompositeDuplex` asserzione associata.

La specifica WS-Addressing WSDL tenta di descrivere associazioni del protocollo simili introducendo un elemento `<wsaw:Anonymous/>` con tre valori testuali (obbligatorio, facoltativo e proibito) per indicare requisiti nell'intestazione `wsa:ReplyTo` (sezione 3.2). Sfortunatamente, tale definizione dell'elemento non è utilizzabile in modo specifico nel contesto di WS-Policy, perché richiede estensioni specifiche di dominio per supportare l'intersezione di alternative che utilizzano tale elemento come asserzione. A differenza del comportamento di endpoint in transito, che rende il valore dell'intestazione `ReplyTo` specifico del trasporto HTTP, il suddetto elemento indica questo valore senza associarlo a un determinato protocollo.

#### <a name="action-definition"></a>Definizione dell'attributo Action
La specifica WS-Addressing 2004/08 definisce un attributo `wsa:Action` per gli elementi `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`. L'associazione WS-Addressing 1.0 WSDL (WS-ADDR10-WSDL) definisce un attributo simile, ovvero `wsaw10:Action`.

L'unica differenza consiste nella semantica del modello Action predefinito, descritta rispettivamente nella sezione 3.3.2 della specifica WS-ADDR e nella sezione 4.4.4 della specifica WS-ADDR10-WSDL.

È ammissibile avere due endpoint che condividono lo stesso `portType` (o contratto, nella terminologia di WCF), ma mediante versioni diverse di WS-Addressing. Tuttavia, se l'attributo Action è definito dall'attributo `portType` e deve essere condiviso da tutti gli endpoint che implementano l'attributo `portType`, risulta impossibile supportare entrambi i modelli Action predefiniti.

Per risolvere questa problematica, WCF supporta una sola versione del `Action` attributo.

B3521: WCF Usa il `wsaw10:Action` attributo `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` gli elementi come definito in WS-ADDR10-WSDL per determinare il `Action` URI per i messaggi corrispondenti indipendentemente dalla versione WS-Addressing utilizzata dall'endpoint.

#### <a name="use-endpoint-reference-inside-wsdl-port"></a>Utilizzare il riferimento a endpoint nell'elemento wsdl:port
La sezione 4.1 di WS-ADDR10-WSDL estende l'elemento `wsdl:port` per includere l'elemento figlio `<wsa10:EndpointReference…/>` allo scopo di descrivere l'endpoint in termini di WS-Addressing. WCF estende questa utilità in WS-Addressing 2004/08, consentendo `<wsa:EndpointReference…/>` venga visualizzato come elemento figlio di `wsdl:port`.

- R3531: Se un endpoint è associata un'alternativa criteri con un `<wsaw10:UsingAddressing/>` asserzione di criteri corrispondenti `wsdl:port` elemento può contenere un elemento figlio `<wsa10:EndpointReference …/>`.

- R3532: Se un `wsdl:port` contiene un elemento figlio `<wsa10:EndpointReference …/>`, il `wsa10:EndpointReference/wsa10:Address` valore dell'elemento figlio deve corrispondere al valore della `@address` attributo dell'elemento di pari livello `wsdl:port` / `wsdl:location` elemento.

- R3533: Se un endpoint è associata un'alternativa criteri con `<wsap:UsingAddressing/>` asserzione di criteri corrispondenti `wsdl:port` elemento può contenere un elemento figlio `<wsa:EndpointReference …/>`.

- R3534: Se un `wsdl:port` contiene un elemento figlio `<wsa:EndpointReference …/>`, il `wsa:EndpointReference/wsa:Address` valore dell'elemento figlio deve corrispondere al valore della `@address` attributo dell'elemento di pari livello `wsdl:port` / `wsdl:location` elemento.

### <a name="composition-with-ws-security"></a>Integrazione con WS-Security
Secondo le sezioni di WS-ADDR e WS-ADDR10 relative alle considerazioni sulla sicurezza, è consigliabile firmare tutte le intestazioni dei messaggi di indirizzamento insieme al corpo del messaggio, in modo da associarli fra loro.

Quando si utilizza WS-Security per garantire l'integrità dei messaggi, le intestazioni dei messaggi di WS-Addressing nonché le intestazioni ottenute dai parametri o dalle proprietà del riferimento (o da entrambi) devono essere firmate insieme al corpo del messaggio.

### <a name="examples"></a>Esempi

#### <a name="one-way-message"></a>Modello unidirezionale
In questo scenario, il mittente invia un messaggio unidirezionale al destinatario. Vengono utilizzate le specifiche SOAP 1.2, HTTP 1.1 e W3C WS-Addressing 1.0.

La struttura dei messaggi di richiesta: Includono le intestazioni del messaggio `wsa10:To` e `wsa10:Action` elementi. Il corpo dei messaggi include un elemento `<app:Ping>` specifico dello spazio dei nomi dell'applicazione.

Intestazioni HTTP: La destinazione indicata in POST corrisponde all'URI specificato nel `wsa10:To` elemento.

L'intestazione Content-Type dispone del valore di `application/soap+xml` come richiesto da SOAP 1.2. I parametri `charset` e `action` sono inclusi. Il parametro `action` dell'intestazione Content-Type corrisponde al valore dell'intestazione dei messaggi `wsa10:Action`.

```
POST http://fabrikam123.com/Service HTTP/1.1
Content-Type: application/soap+xml; charset=utf-8;  
              action="http://fabrikam123.com/Service/OneWay"
Host: 131.107.72.15
Content-Length: 1501
Expect: 100-continue
Proxy-Connection: Keep-Alive
<s12:Envelope>
  <s12:Header>
    <wsa10:To s12:mustUnderstand="1">
        http://fabrikam123.com/Service
    </wsa10:To>
    <wsa10:Action s12:mustUnderstand="1">
        http://fabrikam123.com/Service/OneWay 
    </wsa10:Action>
  </s12:Header>
  <s12:Body>
    <Ping xmlns="http://fabrikam123.com/Service/">
      <Text>Hello World</Text>
    </Ping>
  </s12:Body>
</s12:Envelope>
```

Il destinatario fornisce con una risposta HTTP vuota e lo stato 202. Un esempio della risposta HTTP:

```
HTTP/1.1 202 Accepted
Date: Fri, 15 Jul 2005 08:56:07 GMT
Server: Microsoft-IIS/6.0
MicrosoftOfficeWebServer: 5.0_Pub
X-Powered-By: ASP.NET
X-AspNet-Version: 2.0.50215
Cache-Control: private
Content-Length: 0
```

## <a name="soap-message-transmission-optimization-mechanism"></a>SOAP MTOM
In questa sezione descrive i dettagli di implementazione WCF per il meccanismo HTTP SOAP MTOM. Tecnologia MTOM è un meccanismo di codifica messaggi SOAP della stessa classe di codifica text/XML tradizionali o codifica binaria di WCF. Il meccanismo MTOM prevede le funzionalità seguenti:

- Meccanismo di codifica e assemblaggio di pacchetti XML descritto da [XOP] che ottimizza le voci di informazioni XML contenenti dati binari con codifica in base 64 suddividendoli in parti binarie distinte.

- Incapsulamento MIME del pacchetto XOP che serializza l'InfoSet XML e ogni parte binaria del pacchetto XOP in una parte MIME distinta.

- Codifica MIME XOP applicata alla SOAP 1.x envelope.

- Associazione di trasporto HTTP.

È possibile utilizzare il meccanismo MTOM con trasporti non HTTP con WCF. quanto descritto in questo argomento si basa sul protocollo HTTP.

Il formato MTOM sfrutta un numeroso set di specifiche relative al meccanismo MTOM stesso, a XOP e a MIME. La modularità di questo set di specifiche rende piuttosto difficile ricavare in modo esatto i requisiti relativi alla semantica di formato ed elaborazione. Questa sezione descrive i requisiti di formato ed elaborazione dell'associazione MTOM HTTP.

### <a name="mtom-message-encoding"></a>Codifica dei messaggi MTOM

#### <a name="generating-mtom-messages"></a>Generazione di messaggi MTOM
La sezione 3.1 di [XOP] descrive il processo di codifica di elementi XML aventi voci di informazioni sugli elementi contenenti valori in base 64 in un pacchetto XOP definito in modo astratto.

La sequenza di passaggi seguente descrive il processo di codifica specifico del meccanismo MTOM:

1. Assicurarsi che la SOAP Envelope da codificare non contiene alcun elemento informazioni sull'elemento con un `[namespace name]` dei `http://www.w3.org/2004/08/xop/include` e una `[local name]` di `Include`.

2. Creare un pacchetto MIME vuoto.

3. Identificare all'interno dell'InfoSet XML originale le voci di informazioni sugli elementi da ottimizzare. Per gli elementi da ottimizzare, i caratteri che costituiscono il `[children]` le informazioni elemento elemento deve essere nel formato canonico `xs:base64Binary` (vedere XSD-2, 3.2.16 base64Binary) e non deve contenere i caratteri spazi vuoti precedente, in linea con, o Dopo il contenuto di spazio non vuoto.

4. Creare una XOP SOAP envelope uguale alla SOAP envelope originale, sostituendo tuttavia al figlio di ogni voce di informazioni sugli elementi identificato nel passaggio precedente una voce di informazioni sugli elementi `xop:Include` costruito come segue:

    1. Trasformare i caratteri sostituiti in dati binari elaborandoli come dati codificati in base 64.

    2. Generare un valore univoco di intestazione Content-ID che soddisfi i requisiti R3133 e R3134.

    3. Generare un'intestazione MIME Content-Transfer-Encoding con il valore in binario.

    4. Se la voce di informazioni sugli elementi da ottimizzare (ovvero il padre [parent] della voce di informazioni sugli elementi `xop:Include` appena aggiunto) contiene una voce di informazioni sugli attributi `xmime:contentType`, generare un'intestazione Content-Type MIME con il valore dell'attributo `xmime:contentType`.

    5. Generare una nuova parte MIME binaria avente un contenuto formato dagli elementi seguenti: dati binari decodificati a partire dai caratteri sostituiti elaborati come dati in base 64, intestazione Content-ID come da passaggio 4b, intestazione Content- Transfer-Encoding come da passaggio 4c e intestazione Content-Type come da passaggio 4d, se presente.

    6. Aggiungere un attributo `href` all'elemento `xop:Include` con il valore cid: uri derivato dal valore dell'intestazione Content-ID generato nel passaggio 4b. Rimuovere il tipo di inclusione "\<" e ">" caratteri escape-URL la stringa restante e aggiungere il prefisso `cid:`. La suddetta conversione, da eseguire in base ai documenti RFC1738 e RFC2396, deve riguardare almeno il set di caratteri seguente, ma può essere applicata anche ad altri caratteri.

        ```
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"
        ```

5. Creare una parte MIME radice contenente la XOP SOAP envelope ottenuta nel passaggio 4.

6. Scrivere le intestazioni HTTP, compresa l'intestazione Content-Type HTTP.

7. Scrivere il pacchetto MIME.

#### <a name="processing-mtom-messages"></a>Elaborazione di messaggi MTOM
L'elaborazione di un messaggio MTOM è l'esatto contrario del processo descritto nella sezione precedente "Generazione di messaggi MTOM":

1. Verificare che la parte MIME radice contenga l'elemento Content-Type `application/xop+xml`.

2. Costruire una SOAP envelope analizzando la parte MIME radice del pacchetto come documento XML. La codifica dei caratteri viene determinata in base al parametro `charset` del Content-Type della parte MIME radice.

3. Per ogni voce di informazioni sugli elementi della SOAP envelope costruita, che come unico membro della proprietà dei relativi figli [children] presenta una voce di informazioni sugli elementi `xop:Include`, eseguire quanto segue:

    1. Rimuovere il prefisso `cid:` ed eseguire la conversione URI inversa di tutte le sequenze escape (RFC 2396) contenute nel valore dell'attributo `@href` dell'elemento `xop:Include`. Racchiudere la stringa di risultato in "\<", ">".

    2. Individuare la parte MIME contenente il valore dell'intestazione Content-ID corrispondente alla stringa ottenuta nel passaggio 3a.

    3. Sostituire la voce di informazioni sugli elementi `xop:Include` contenuto nella proprietà `children` di ogni elemento contenente le voci di informazioni sugli elementi che rappresentano la codifica canonica in base 64 (vedere XSD-2, 3.2.16 base64Binary) del corpo dell'entità della parte MIME identificato nel passaggio 3b. In pratica, sostituire la voce di informazioni sugli elementi `xop:Include` con i dati ricostruiti a partire dalla parte di pacchetto.

#### <a name="http-content-type-header"></a>Intestazione Content-Type HTTP
Di seguito è riportato un elenco di precisazioni WCF per il formato dell'intestazione Content-Type HTTP di un messaggio SOAP 1.x con codifica MTOM derivato dai requisiti dichiarati nella specifica di MTOM e si basano MTOM e RFC 2387.

- R4131: Un'intestazione Content-Type HTTP deve avere il valore multipart/Related (maiuscole e minuscole) e i relativi parametri. Anche i nomi dei parametri non fanno distinzione tra maiuscole e minuscole. Inoltre, l'ordine dei parametri è irrilevante.

- La notazione BNF completa dell'intestazione Content-Type dei messaggi MIME è riportata nella sezione 5.1 del documento RFC 2045.

- R4132: Un'intestazione Content-Type HTTP deve contenere un parametro di tipo con il valore `application/xop+xml` racchiuso tra virgolette doppie.

Anche la necessità di utilizzare le virgolette doppie non è esplicita in RFC 2387, il testo osserva che molto probabilmente tutti i parametri di tipo di supporto multipart/related contengono caratteri riservati, ad esempio "\@" o "/" e pertanto richiede le virgolette doppie contrassegni.

- R4133: Un'intestazione Content-Type HTTP deve contenere un parametro di avvio con il valore dell'intestazione Content-ID della parte MIME contenente il SOAP 1.x Envelope, racchiuso tra virgolette doppie. Se tale parametro viene omesso, la SOAP 1.x envelope deve essere inclusa nella prima parte MIME.

- R4134: Un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.1 MTOM deve includere il parametro start-info con il valore di testo/xml, racchiuso tra virgolette doppie.

- R4135: Un'intestazione Content-Type HTTP di un messaggio con codifica SOAP 1.2 MTOM deve includere il parametro start-info con il valore di `application/soap+xml`, racchiuso tra virgolette doppie.

- R4136: Intestazione Content-Type HTTP per un messaggio con codifica MTOM SOAP 1.x deve contenere il parametro limite con il valore (racchiuso tra virgolette doppie) che corrisponde al limite MIME che BNF definito in RFC 2046, sezione 5.1.1

    ```
    boundary := 0*69<bchars> bcharsnospace 
    bchars := bcharsnospace / " " 
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+" 
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"
    ```

     Esempi:

     CORRETTO

    ```
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"
    ```

     CORRETTO

    ```
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

     NON CORRETTO

    ```
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1" 
    ```

#### <a name="infoset-mime-part"></a>Parte MIME InfoSet
La SOAP 1.x envelope è incapsulata come parte radice del pacchetto XOP MIME e spesso viene detta "parte `infoset`".

- R4141: Il SOAP 1.x Envelope deve essere incapsulata come parte radice del pacchetto XOP MIME, chiamato il `infoset` parte e il riferimento da Content-Type HTTP.

- R4142: SOAP `Infoset` parte deve includere le intestazioni MIME seguenti: `Content-ID`, `Content-Transfer-Encoding`, e `Content-Type`.

Il formato dell'intestazione Content-ID è definito nel documento RFC 2045 come

```
"Content-ID" ":" msg-id
```

in cui l'elemento `msg-id` è definito nel documento RFC 2822 (che sostituisce il documento RFC 822, a cui si fa riferimento nel documento RFC 2045) come:

```
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]
```

e in modo efficace un indirizzo di posta elettronica è incluso all'interno di "\<" e ">". Il prefisso e il suffisso `[CFWS]` sono stati aggiunti nel documento RFC 2822 per contenere commenti e non devono essere utilizzati per mantenere l'interoperabilità.

R4143: Il valore dell'intestazione Content-ID per la parte MIME Infoset deve seguire `msg-id` produzione dal documento RFC 2822 con il `[CFWS]` parti del prefisso e suffisso omesso.

Molte implementazioni MIME ridotti i requisiti per il valore racchiuso tra parentesi "\<" e ">" per essere un indirizzo di posta elettronica e usati `absoluteURI` racchiusa tra "\<", ">" oltre all'indirizzo di posta elettronica. Questa versione di WCF utilizza i valori dell'intestazione MIME Content-ID nel formato:

```
Content-ID: <http://tempuri.org/0> 
```

R4144: Processori MTOM devono accettare valori di intestazione Content-ID che corrispondono a ridotti riportato `msg-id`.

```
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]
mail-address   =     id-left "@" id-right
```

Il protocollo MIME (RFC 2045) fornisce l'intestazione Content-Transfer-Encoding per comunicare la codifica del contenuto della parte MIME. L'impostazione predefinita dell'intestazione Content-Transfer-Encoding è una codifica a 7 bit, che tuttavia per la maggior parte dei messaggi SOAP risulta inadatta. Pertanto, tale intestazione è necessaria per garantire una maggiore interoperabilità:

- R4145: La parte SOAP Infoset deve contenere l'intestazione Content-Transfer-Encoding.

- R4146: Se la codifica di caratteri della SOAP Envelope è UTF-8, il valore dell'intestazione Content-Transfer-Encoding deve essere 8 bit.

- R4147: Se la codifica di caratteri della SOAP Envelope è UTF-16, il valore dell'intestazione Content-Transfer-Encoding deve essere binario.

- Secondo quanto indicato nella sezione 5 di [XOP]:

- R4148: Parte SOAP1.1 Infoset deve contenere l'intestazione Content-Type con tipo di supporto application/xop + xml e parametri di tipo = "text/xml" e charset

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="text/xml"
    ```

- R4149: La parte SOAP 1.2 Infoset deve contenere l'intestazione Content-Type con tipo di supporto `application/xop+xml` e parametri di tipo = "`application/soap+xml`" e `charset`.

    ```
    Content-Type: application/xop+xml;
                  charset=utf-8;type="application/soap+xml"
    ```

     Benché XOP consenta di definire il parametro `charset` di `application/xop+xml` come facoltativo, tale parametro è necessario per l'interoperabilità, analogamente al requisito di BP 1.1 relativo al parametro `charset` del tipo di supporto `text/xml`.

- R41410: Il `type` e `charset` parametri devono essere presenti nell'intestazione Content-Type della parte SOAP 1.x Infoset.

#### <a name="wcf-endpoint-support-for-mtom"></a>Supporto degli endpoint WCF per MTOM
Lo scopo del meccanismo MTOM è codificare un messaggio SOAP allo scopo di ottimizzare i dati codificati in base 64. Segue un elenco di vincoli:

- R4151: Eventuali informazioni sugli elementi che contiene i dati con codifica base 64 può essere ottimizzata.

- B4152: WCF consente di ottimizzare le informazioni sugli elementi che contengono dati con codifica base64 e superare i 1024 byte in lunghezza.

Un endpoint WCF configurato per utilizzare il meccanismo MTOM inviano sempre i messaggi con codifica MTOM. Anche se nessuna parte soddisfa i criteri previsti, il messaggio viene comunque considerato come messaggio con codifica MTOM, serializzato come pacchetto MIME e avente una sola parte MIME contenente la SOAP envelope.

### <a name="ws-policy-assertion-for-mtom"></a>Asserzione di WS-Policy relativa a MTOM
WCF utilizza l'asserzione di criteri seguenti per indicare l'utilizzo del meccanismo MTOM dall'endpoint:

```xml
<wsoma:OptimizedMimeSerialization ... />
```

- R4211: L'asserzione di criteri precedente contiene un soggetto dei criteri di Endpoint e specifica che tutti i messaggi inviati e ricevuti dall'endpoint devono essere ottimizzati tramite MTOM.

- B4212: Se è configurato per utilizzare l'ottimizzazione MTOM, un endpoint WCF aggiunge un'asserzione di criteri MTOM al criterio associato all'oggetto corrispondente `wsdl:binding`.

### <a name="composition-with-ws-security"></a>Integrazione con WS-Security
MTOM è un meccanismo di codifica che è simile a `text/xml` e XML binario WCF. Il meccanismo MTOM può integrarsi perfettamente con il protocollo WS-Security e gli altri protocolli WS - *: un messaggio protetto mediante il protocollo WS-Security può infatti essere ottimizzato tramite MTOM.

### <a name="examples"></a>Esempi

#### <a name="wcf-soap-11-message-encoded-using-mtom"></a>Esempio di messaggio WCF SOAP 1.1 codificato tramite MTOM

```
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"
Content-Type: multipart/related;type="application/xop+xml";
              start="<http://tempuri.org/0>";start-info="text/xml";
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
Host: 131.107.72.15
Content-Length: 1501
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">
      <array>
        <xop:Include
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </array>
    </EchoBinaryAsString>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/1/632618206521093670>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
…Binary Content..
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
```

#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a>Esempio di messaggio WCF Secure SOAP 1.2 codificato tramite MTOM
Questo esempio illustra la codifica tramite MTOM e SOAP 1.2 di un messaggio protetto mediante WS-Security. Le parti binarie identificate per la codifica sono il contenuto del token `BinarySecurityToken`, il valore `CipherValue` dell'elemento `EncryptedData` che corrisponde alla firma crittografata e il corpo crittografato. Si noti che il `CipherValue` del `EncryptedKey` non identificata per l'ottimizzazione da WCF, poiché la sua lunghezza è inferiore a 1024 byte.

```
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1
Content-Type: multipart/related; type="application/xop+xml";
              start="<http://tempuri.org/0>";
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";
              start-info="application/soap+xml"; 
              action="http://xmlsoap.org/echoBinaryAsString"
Host: 131.107.72.15
Content-Length: 1941
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
  <s:Header>
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>
      </u:Timestamp>
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </o:BinarySecurityToken>
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>
        </e:CipherData>
      </e:EncryptedKey>
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">
        <o:SecurityTokenReference>
          <o:Reference URI="#_1"/>
        </o:SecurityTokenReference>
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>
      </c:DerivedKeyToken>
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:DataReference URI="#_3"/>
        <e:DataReference URI="#_4"/>
      </e:ReferenceList>
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:Reference URI="#_2"/>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>
          <e:CipherValue>
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
          </e:CipherValue>
        </e:CipherData>
      </e:EncryptedData>
    </o:Security>
  </s:Header>
  <s:Body u:Id="_0">
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
          <o:Reference URI="#_2"/>
        </o:SecurityTokenReference>
      </KeyInfo>
      <e:CipherData>
        <e:CipherValue>
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
        </e:CipherValue>
      </e:CipherData>
    </e:EncryptedData>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/1/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary content of BinarySecurityToken - X509 Certificate...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/2/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted primary signature...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/3/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted Body...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--
```