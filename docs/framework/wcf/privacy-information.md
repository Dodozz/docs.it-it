---
title: Informazioni sulla privacy di Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: e506908299109f94be6d190017b381fe7b4ee044
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151502"
---
# <a name="windows-communication-foundation-privacy-information"></a>Informazioni sulla privacy di Windows Communication Foundation
Microsoft è impegnata a proteggere la privacy degli utenti finali. Quando si compila un'applicazione che usa Windows Communication Foundation (WCF), versione 3.0, l'applicazione può incidere sulla privacy degli utenti finali. L'applicazione potrebbe, ad esempio, raccogliere in modo esplicito informazioni di contatto sugli utenti o richiedere o inviare informazioni in Internet al sito Web. Se si incorpora la tecnologia Microsoft nell'applicazione, è possibile che tale tecnologia abbia un proprio comportamento che potrebbe influire sulla privacy. WCF non invia informazioni a Microsoft dall'applicazione, a meno che l'utente finale sceglie di inviarlo a Microsoft.  
  
## <a name="wcf-in-brief"></a>WCF in breve  
 WCF è un framework di messaggistica distribuito tramite Microsoft .NET Framework che consente agli sviluppatori di compilare applicazioni distribuite. I messaggi comunicati tra due applicazioni contengono informazioni di intestazione e corpo.  
  
 Le intestazioni possono contenere il routing dei messaggi, informazioni sulla sicurezza, transazioni e altro, a seconda dei servizi usati dall'applicazione. I messaggi vengono in genere crittografati per impostazione predefinita. L'unica eccezione a questa regola si verifica quando si usa `BasicHttpBinding`, che è stato progettato per l'uso con i servizi Web legacy, non-protetti. I progettisti dell'applicazione sono responsabili della progettazione finale. I messaggi nel corpo SOAP contengono dati specifici dell'applicazione. Tuttavia, è possibile proteggere questi dati, ad esempio le informazioni personali definite dall'applicazione, usando le funzionalità di crittografia o riservatezza WCF. Nelle sezioni seguenti vengono descritte le funzionalità che potrebbero avere un impatto sulla privacy.  
  
## <a name="messaging"></a>Messaggistica  
 Ogni messaggio WCF presenta un'intestazione di indirizzo che specifica la destinazione del messaggio e in cui la risposta dovrebbe arrivare.  
  
 Il componente indirizzo di un endpoint è un URI (Uniform Resource Identifier) che identifica l'endpoint. L'indirizzo può essere un indirizzo di rete o logico. L'indirizzo può includere il nome del computer (nome host, nome di dominio completo) e un indirizzo IP. L'indirizzo dell'endpoint può inoltre contenere un GUID (Globally Unique Identifier) o una raccolta di GUID per indirizzamento temporaneo usato per discernere ogni indirizzo. Ogni messaggio contiene un ID di messaggio che corrisponde a un GUID. Questa funzionalità segue lo standard di riferimento WS-Addressing.  
  
 Il livello di messaggistica di WCF non scrive informazioni personali nel computer locale. Tuttavia, potrebbe propagare informazioni personali a livello di rete, se un sviluppatore di servizi ha creato un servizio che espone tali informazioni usando, ad esempio, il nome di una persona in un nome di endpoint o includendo informazioni personali nel linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) dell'endpoint senza richiedere però ai client di usare https per accedere al codice WSDL. Inoltre, se uno sviluppatore è in esecuzione la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento su un endpoint che espone informazioni personali, l'output dello strumento potrebbe contenere tali informazioni e il file di output viene scritto il disco rigido locale.  
  
## <a name="hosting"></a>Hosting  
 La funzionalità di hosting di WCF consente alle applicazioni per avviare su richiesta o per abilitare la condivisione delle porte tra più applicazioni. Un'applicazione WCF può essere ospitata in Internet Information Services (IIS), simile a [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
 L'hosting non espone informazioni specifiche sulla rete e non implica il mantenimento di dati sul computer.  
  
## <a name="message-security"></a>Sicurezza dei messaggi  
 Sicurezza WCF fornisce le funzionalità di sicurezza per le applicazioni di messaggistica. Le funzioni di sicurezza previste includono autenticazione e autorizzazione.  
  
 L'autenticazione viene eseguita passando credenziali tra i client e i servizi. L'autenticazione può avvenire tramite la sicurezza a livello di trasporto o tramite la sicurezza a livello di messaggio SOAP, come riportato di seguito:  
  
-   Nella sicurezza dei messaggi SOAP, l'autenticazione viene eseguita tramite credenziali quali nome utente/password, certificati X.509, ticket Kerberos e token SAML, tutti elementi che potrebbero contenere informazioni personali, a seconda dell'autorità emittente.  
  
-   Con la sicurezza del trasporto, l'autenticazione viene eseguita tramite tradizionali meccanismi di autenticazione del trasporto quali gli schemi di autenticazione HTTP (di base, digest, Negotiate, autenticazione integrata di Windows, NTLM, Nessuno e accesso anonimo) e l'autenticazione dei moduli.  
  
 Il risultato dell'autenticazione può essere una sessione protetta stabilita tra gli endpoint di comunicazione. La sessione viene identificata da un GUID che ha la durata della sessione di sicurezza. Nella tabella seguente viene mostrato cosa viene mantenuto e dove.  
  
|Dati|Archiviazione|  
|----------|-------------|  
|Credenziali di presentazione, ad esempio nome utente, certificati X.509, token Kerberos e riferimenti alle credenziali.|Meccanismi di gestione delle credenziali standard di Windows, ad esempio l'archivio certificati di Windows.|  
|Informazioni relative all'appartenenza degli utenti, ad esempio nomi utente e password.|Provider di appartenenza [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].|  
|Informazioni di identità sul servizio usato per autenticare il servizio sui client.|Indirizzo dell'endpoint del servizio.|  
|Informazioni sul chiamante.|Registri di controllo.|  
  
## <a name="auditing"></a>Controllo  
 Il controllo registra l'esito positivo o negativo degli eventi di autenticazione e autorizzazione. I record di controllo contengono i dati seguenti: URI del servizio, URI dell'azione e identificazione del chiamante.  
  
 Il controllo registra inoltre quando l'amministratore modifica la configurazione della registrazione messaggi (attivandola o disattivandola), poiché la registrazione messaggi può registrare dati specifici dell'applicazione in intestazioni e corpi. Per [!INCLUDE[wxp](../../../includes/wxp-md.md)], viene registrato un record nel registro eventi dell'applicazione. Per [!INCLUDE[wv](../../../includes/wv-md.md)] e [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], viene registrato un record nel registro eventi di sicurezza.  
  
## <a name="transactions"></a>Transazioni  
 La funzionalità transazioni fornisce servizi transazionali a un'applicazione WCF.  
  
 Le intestazioni delle transazioni usate nella propagazione delle transazioni possono contenere ID di transazione o ID di integrazione, che sono GUID.  
  
 La funzionalità Transazioni usa gestione transazioni MSDTC (Microsoft Distributed Transaction Coordinator), un componente di Window, per gestire lo stato delle transazioni. Per impostazione predefinita, le comunicazioni tra i gestori transazioni vengono crittografate. I gestori transazioni possono registrare riferimenti agli endpoint, ID di transazione e ID di integrazione come parte del proprio stato durevole. La durata di questo stato è determinata dalla durata del file di log della gestione transazioni. Il servizio MSDTC possiede e gestisce questo log.  
  
 La funzionalità Transazioni implementa gli standard WS-Coordination e WS-Atomic Transaction.  
  
## <a name="reliable-sessions"></a>Sessioni affidabili  
 Le sessioni affidabili in WCF forniscono il trasferimento dei messaggi quando si verificano errori di intermediari o trasporto. Esse garantiscono un trasferimento di tipo exactly-once dei messaggi anche quando il trasporto sottostante si disconnette (ad esempio, una connessione TCP su una rete wireless ) o perde un messaggio (un proxy HTTP che rilascia un messaggio in uscita o in ingresso). Le sessioni affidabili recuperano inoltre il riordinamento dei messaggi (come può accadere nel caso del routing a percorsi multipli), preservando l'ordine di invio.  
  
 Le sessioni affidabili vengono implementate usando il protocollo WS-RM (WS-ReliableMessaging) e aggiungono intestazioni WS-RM che contengono informazioni sulle sessioni usate per identificare tutti i messaggi associati a una particolare sessione affidabile. Ogni sessione WS-RM ha un identificatore corrispondente a un GUID.  
  
 Nessuna informazione personale viene mantenuta sul computer dell'utente finale.  
  
## <a name="queued-channels"></a>Canali in coda  
 Le code archiviano messaggi provenienti da un'applicazione mittente per conto di un'applicazione ricevente e quindi inoltrano tali messaggi all'applicazione ricevente. Esse consentono di assicurare il trasferimento dei messaggi dalle applicazioni mittenti alle applicazioni riceventi quando, ad esempio, l'applicazione ricevente è temporanea. WCF fornisce supporto per l'accodamento utilizzando Accodamento messaggi Microsoft (MSMQ) come trasporto.  
  
 La funzionalità dei canali in coda non aggiunge intestazioni a un messaggio. Crea invece un messaggio di accodamento messaggi con le proprietà del messaggio di accodamento messaggi appropriate impostate e richiama metodi di accodamento messaggi per inserire il messaggio nella coda di accodamento messaggi. Il servizio di accodamento messaggi è un componente facoltativo fornito con Windows.  
  
 La funzionalità dei canali in coda non conserva alcuna informazione sul computer dell'utente finale, perché usa l'accodamento messaggi come infrastruttura di accodamento.  
  
## <a name="com-integration"></a>Integrazione COM+  
 Questa funzionalità esegue il wrapping di funzionalità COM e COM+ esistenti per creare servizi compatibili con i servizi WCF. Essa non usa intestazioni specifiche e non conserva dati sul computer dell'utente finale.  
  
## <a name="com-service-moniker"></a>Moniker servizio COM  
 Questo fornisce un wrapper non gestito a un client WCF standard. Essa non prevede intestazioni specifiche in transito né conserva dati sul computer.  
  
## <a name="peer-channel"></a>Canale del peer  
 Il canale peer consente lo sviluppo di applicazioni a più parti tramite WCF. La messaggistica a più parti si verifica nel contesto di una rete. Le reti vengono identificate da un nome a cui i nodi possono connettersi. Ogni nodo nel canale del peer crea un listener TCP su una porta specificata dall'utente e stabilisce connessioni con altri nodi nella rete per assicurare la flessibilità. Per connettersi ad altri nodi nella rete, i nodi si scambiano anche alcuni dati, incluso l'indirizzo del listener e gli indirizzi IP del computer. I messaggi inviati nella rete possono contenere informazioni di sicurezza relative al mittente, per impedire lo spoofing e la manomissione dei messaggi.  
  
 Non vengono archiviate informazioni personali sul computer dell'utente finale.  
  
## <a name="it-professional-experience"></a>Esperienza dei professionisti IT  
  
### <a name="tracing"></a>Traccia  
 La funzionalità di diagnostica dell'infrastruttura di WCF registra i messaggi che passano attraverso il trasporto e livelli del modello di servizio e le attività e gli eventi associati a questi messaggi. Questa funzionalità è disattivata per impostazione predefinita. Viene attivata usando il file di configurazione dell'applicazione e il comportamento della traccia può essere modificato usando il provider WMI per WCF in fase di esecuzione. Quando viene attivata, l'infrastruttura di traccia emette una traccia di diagnostica che contiene messaggi, attività ed eventi di elaborazione per i listener configurati. Il formato e la posizione dell'output vengono determinati dalle scelte di configurazione dei listener dell'amministratore, ma l'output è in genere un file con formattazione XML. L'amministratore è responsabile dell'impostazione dell'elenco di controllo di accesso sui file di traccia. In particolare, in caso di hosting in Windows Activation System (WAS), l'amministratore deve verificare che i file non vengano servizi dalla directory radice virtuale pubblica, se non lo si desidera.  
  
 Esistono due tipi di traccia: La registrazione dei messaggi e modello del servizio diagnostica tracing, descritto nella sezione seguente. Ogni tipo viene configurato tramite la propria origine di traccia: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> e <xref:System.ServiceModel>. Entrambe queste origini di traccia di registrazione acquisiscono dati locali rispetto all'applicazione.  
  
### <a name="message-logging"></a>Registrazione messaggi  
 L'origine di traccia della registrazione messaggi (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) consente a un amministratore di registrare messaggi che fluiscono attraverso il sistema. Tramite la configurazione, l'utente può decidere di registrare interi messaggi o solo intestazioni, se eseguire la registrazione a livello di trasporto e/o di modello di servizio e se includere messaggi in formato non valido. Inoltre, può configurare il filtro per limitare il numero di messaggi registrati.  
  
 Per impostazione predefinita, la registrazione messaggi è disattivata. L'amministratore del computer locale può impedire che l'amministratore a livello di applicazione attivi la registrazione messaggi.  
  
#### <a name="encrypted-and-decrypted-message-logging"></a>Registrazione di messaggi crittografati e decrittografati  
 I messaggi vengono registrati, crittografati o decrittografati, come descritto nei termini seguenti.  
  
 Registrazione trasporto  
 Registra messaggi ricevuti e inviati a livello di trasporto. Questi messaggi contengono tutte le intestazioni e possono essere crittografati prima dell'invio in rete e al momento della ricezione.  
  
 Se i messaggi vengono crittografati prima dell'invio in rete e al momento della ricezione, vengono anche registrati in forma crittografata. Si verifica un'eccezione a questa regola quando viene usato un protocollo di sicurezza (https). In questo caso, i messaggi vengono registrati in forma decrittografata prima dell'invio e dopo la ricezione, anche se risultano crittografati in rete.  
  
 Registrazione servizio  
 Registra i messaggi ricevuti o inviati a livello del modello di servizio, dopo l'elaborazione dell'intestazione di canale, immediatamente prima e dopo l'immissione del codice utente.  
  
 I messaggi registrati a questo livello vengono decrittografati anche se sono stati protetti e crittografati durante il transito.  
  
 Registrazione messaggi in formato non valido  
 Registra i messaggi che non è possibile comprendere o elaborare l'infrastruttura WCF.  
  
 I messaggi vengono registrati così come sono, ovvero in forma crittografata o decrittografata.  
  
 Quando i messaggi vengono registrati forma decrittografata o non crittografata, per impostazione predefinita WCF rimuove le chiavi di sicurezza e potenziali informazioni personali dai messaggi prima la registrazione. Nelle sezioni successive vengono descritte quali informazioni vengono rimosse e quando. L'amministratore del computer e il distributore dell'applicazione devono entrambi eseguire determinate operazioni di configurazione per modificare il comportamento predefinito al fine di registrare chiavi e potenziali informazioni personali.  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a>Informazioni rimosse dalle intestazioni dei messaggi in caso di registrazione di messaggi decrittografati/non crittografati  
 Quando i messaggi vengono registrati in forma decrittografata/non crittografata, le chiavi di sicurezza e le potenziali informazioni personali vengono rimosse, per impostazione predefinita, dalle intestazioni e dai corpi dei messaggi prima della registrazione. Nell'elenco seguente viene illustrato cosa WCF considera chiavi e potenziali informazioni personali.  
  
 Chiavi rimosse:  
  
 \- Per xmlns:wst = "http://schemas.xmlsoap.org/ws/2004/04/trust" e xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust"  
  
 wst:BinarySecret  
  
 wst:Entropy  
  
 \- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Password  
  
 wsse:Nonce  
  
 Potenziali informazioni personali rimosse:  
  
 \- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Username  
  
 wsse:BinarySecurityToken  
  
 \- Per xmlns:SAML="urn:OASIS:Names:TC:SAML:1.0:Assertion ="urn: oasis: nomi: tc: SAML:1.0:assertion"vengono rimossi gli elementi in grassetto (seguenti):  
  
 \<Asserzione  
  
 MajorVersion="1"  
  
 MinorVersion="1"  
  
 AssertionId="[ID]"  
  
 Issuer="[string]"  
  
 IssueInstant="[dateTime]"  
  
 >  
  
 \<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]">  
  
 \<AudienceRestrictionCondition>  
  
 \<Gruppo di destinatari > [uri]\</Audience > +  
  
 \</AudienceRestrictionCondition>*  
  
 \<DoNotCacheCondition />*  
  
 <\!-tipo di base astratta  
  
 \<Condizione / > *  
  
 -->  
  
 \</Conditions>?  
  
 \<Advice>  
  
 \<AssertionIDReference > [ID]\</AssertionIDReference > *  
  
 \<Asserzione > [asserzione]\</Assertion > *  
  
 [any]*  
  
 \</Advice>?  
  
 <\!: Tipi di base astratti  
  
 \<Istruzione / > *  
  
 \<SubjectStatement>  
  
 \<Subject>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 \<SubjectConfirmation>  
  
 \<ConfirmationMethod > [anyUri]\</ConfirmationMethod > +  
  
 \<SubjectConfirmationData > [qualsiasi]\</SubjectConfirmationData >?  
  
 \<ds:KeyInfo>...\</ds:KeyInfo>?  
  
 \</SubjectConfirmation>?  
  
 \</Subject>  
  
 \</SubjectStatement>*  
  
 -->  
  
 \<AuthenticationStatement  
  
 AuthenticationMethod="[uri]"  
  
 AuthenticationInstant="[dateTime]"  
  
 >  
  
 [Subject]  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <AuthorityBinding  
  
 AuthorityKind="[QName]"  
  
 Location="[uri]"  
  
 Binding="[uri]"  
  
 />*  
  
 \</AuthenticationStatement>*  
  
 \<AttributeStatement>  
  
 [Subject]  
  
 \<Attributo  
  
 AttributeName="[string]"  
  
 AttributeNamespace="[uri]"  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 \</ Attributo > +  
  
 \</AttributeStatement>*  
  
 \<AuthorizationDecisionStatement  
  
 Resource="[uri]"  
  
 Decision="[Permit&#124;Deny&#124;Indeterminate]"  
  
 >  
  
 [Subject]  
  
 \<Action Namespace="[uri]">[string]\</Action>+  
  
 \<Evidence>  
  
 \<AssertionIDReference > [ID]\</AssertionIDReference > +  
  
 \<Asserzione > [asserzione]\</Assertion > +  
  
 \</Evidence>?  
  
 \</AuthorizationDecisionStatement>*  
  
 \</ Asserzione >  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a>Informazioni rimosse dai corpi dei messaggi in caso di registrazione di messaggi decrittografati/non crittografati  
 Come descritto in precedenza, WCF rimuove chiavi e potenziali informazioni personali note dalle intestazioni del messaggio per i messaggi decrittografati/non crittografati registrati. Inoltre, WCF consente di rimuovere le chiavi e potenziali informazioni personali note dai corpi dei messaggi per gli elementi di corpo e le azioni nell'elenco seguente, che descrivono messaggi di sicurezza coinvolti nello scambio di chiave.  
  
 Per gli spazi dei nomi seguenti:  
  
 xmlns:WST = "http://schemas.xmlsoap.org/ws/2004/04/trust" e xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust" (ad esempio, se nessuna azione disponibile)  
  
 Vengono rimosse informazioni per questi elementi del corpo, che implicano lo scambio di chiavi:  
  
 wst:RequestSecurityToken  
  
 wst:RequestSecurityTokenResponse  
  
 wst:RequestSecurityTokenResponseCollection  
  
 Vengono inoltre rimosse informazioni per ognuna delle azioni seguenti:  
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend`
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a>Non vengono rimosse informazioni dalle intestazioni e dai dati del corpo specifici dell'applicazione  
 WCF non tiene traccia delle informazioni personali nelle intestazioni specifiche dell'applicazione (ad esempio, le stringhe di query) o dati del corpo (ad esempio, numero di carta di credito).  
  
 Quando la registrazione messaggi è attiva, le informazioni personali presenti in intestazioni e dati del corpo specifici dell'applicazione potrebbero essere visibili nei log. È il distributore dell'applicazione ad essere, ancora una volta, responsabile dell'impostazione degli elenchi di controllo di accesso nei file di configurazione e di log. Egli può inoltre disattivare la registrazione, se non desidera che queste informazioni siano visibili, o può filtrare le informazioni dai file di log dopo la registrazione.  
  
### <a name="service-model-tracing"></a>Traccia del modello di servizio  
 L'origine della traccia del modello di servizio (<xref:System.ServiceModel>) consente la traccia di attività ed eventi correlati all'elaborazione dei messaggi. Questa funzionalità usa la funzionalità di diagnostica di .NET Framework da <xref:System.Diagnostics>. Come con la proprietà <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>, il percorso e il relativo elenco di controllo di accesso sono configurabili dall'utente mediante i file di configurazione dell'applicazione .NET Framework. Come con la registrazione messaggi, il percorso dei file viene sempre configurato quando l'amministratore attiva la traccia ed è quindi l'amministratore a controllare l'elenco di controllo di accesso.  
  
 Le tracce contengono intestazioni di messaggio quando un messaggio è nell'ambito. Si applicano le stesse regole descritte nella sezione precedente per nascondere potenziali informazioni personali presenti nelle intestazioni dei messaggi: le informazioni personali precedentemente identificate vengono rimosse, per impostazione predefinita, dalle intestazioni nelle tracce. L'amministratore del computer e il distributore dell'applicazione devono modificare la configurazione per poter registrare potenziali informazioni personali. Tuttavia, le informazioni personali contenute nelle intestazioni specifiche dell'applicazione vengono registrate nelle tracce. Il distributore dell'applicazione è responsabile dell'impostazione degli elenchi di controllo di accesso nei file di configurazione e di traccia. Può inoltre disattivare la traccia se non desidera che queste informazioni siano visibili, o può filtrare le informazioni dai file di traccia dopo la registrazione.  
  
 Come parte della traccia ServiceModel, ID univoci (denominati ID attività e GUID) collegano insieme attività differenti quando un messaggio passa attraverso diverse parti dell'infrastruttura.  
  
#### <a name="custom-trace-listeners"></a>Listener di traccia personalizzati  
 Per la registrazione e la traccia dei messaggi è possibile configurare un listener di traccia personalizzato che può inviare tracce e messaggi in rete, ad esempio, a un database remoto. Il distributore dell'applicazione è responsabile della configurazione di listener personalizzati o dell'abilitazione degli utenti a tale attività. È inoltre responsabile di qualsiasi informazione personale esposta nel percorso remoto e della corretta applicazione di elenchi di controllo di accesso al percorso in questione.  
  
### <a name="other-features-for-it-professionals"></a>Altre funzionalità per i professionisti IT  
 WCF include un provider WMI che espone le informazioni di configurazione dell'infrastruttura WCF tramite WMI (forniti con Windows). Per impostazione predefinita, l'interfaccia WMI è disponibile per gli amministratori.  
  
 Configurazione di WCF utilizza il meccanismo di configurazione di .NET Framework. I file di configurazione vengono archiviati sul computer. Lo sviluppatore dell'applicazione e l'amministratore creano i file di configurazione e l'elenco di controllo di accesso per ognuno dei requisiti dell'applicazione. Un file di configurazione può contenere indirizzi degli endpoint e collegamenti ai certificati nell'archivio certificati. I certificati possono essere usati per fornire dati dell'applicazione e configurare le varie proprietà delle funzionalità usate dall'applicazione.  
  
 WCF Usa anche la funzionalità di dump di processo di .NET Framework chiamando il <xref:System.Environment.FailFast%2A> (metodo).  
  
### <a name="it-pro-tools"></a>Strumenti per i professionisti IT  
 WCF fornisce anche gli strumenti professionali a IT seguenti, che vengono fornito con il SDK di Windows.  
  
#### <a name="svctraceviewerexe"></a>SvcTraceViewer.exe  
 Il Visualizzatore Visualizza file di traccia WCF. Il visualizzatore mostra tutte le informazioni contenute nelle tracce.  
  
#### <a name="svcconfigeditorexe"></a>SvcConfigEditor.exe  
 L'editor consente all'utente di creare e modificare i file di configurazione WCF. L'editor mostra tutte le informazioni contenute nei file di configurazione. La stessa attività può essere eseguita con un editor di testo.  
  
#### <a name="servicemodelreg"></a>ServiceModel_Reg  
 Questo strumento consente all'utente di gestire installazioni ServiceModel in un computer. Lo strumento visualizza messaggi di stato nella finestra della console quando viene eseguito e, nel processo, possono essere visualizzate informazioni relative alla configurazione dell'installazione di WCF.  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a>WSATConfig.exe e WSATUI.dll  
 Questi strumenti consentono ai professionisti IT di configurare il supporto di rete interoperativo WS-AtomicTransaction in WCF. Gli strumenti visualizzano i valori delle impostazioni WS-AtomicTransaction più comunemente usate archiviati nel Registro di sistema e consentono all'utente di modificarli.  
  
## <a name="cross-cutting-features"></a>Funzionalità a montaggio incrociato  
 Le funzionalità seguenti sono a montaggio incrociato, ovvero possono essere composte con qualsiasi funzionalità precedente.  
  
### <a name="service-framework"></a>Framework dei servizi  
 Le intestazioni possono contenere un ID di istanza, che è un GUID che associa un messaggio a un'istanza di una classe CLR.  
  
 Il linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) contiene una definizione della porta. Ogni porta ha un indirizzo endpoint e un'associazione che rappresenta i servizi usati dall'applicazione. L'esposizione del codice WSDL può essere disattivata usando la configurazione. Nessuna informazioni viene conservata sul computer.  
  
## <a name="see-also"></a>Vedere anche

- [Windows Communication Foundation](index.md)
- [Sicurezza](../../../docs/framework/wcf/feature-details/security.md)
