---
title: Generazione di un client WCF dai metadati del servizio
ms.date: 03/30/2017
ms.assetid: 27f8f545-cc44-412a-b104-617e0781b803
ms.openlocfilehash: c9a72228ddb32786f39585083d62e1f3f028763c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613374"
---
# <a name="generating-a-wcf-client-from-service-metadata"></a>Generazione di un client WCF dai metadati del servizio
In questo argomento viene illustrato come utilizzare le varie opzioni in Svcutil.exe per generare client da documenti dei metadati.  
  
 Questi documenti dei metadati possono essere salvati in modo permanente o recuperati in linea. Il recupero in linea segue il protocollo WS-MetadataExchange o il protocollo Microsoft Discovery (DISCO). Per recuperare metadati, Svcutil.exe genera contemporaneamente le richieste di metadati seguenti:  
  
- Richiesta WS-MetadataExchange (MEX) all'indirizzo fornito.  
  
- Richiesta MEX all'indirizzo fornito con `/mex` accodato.  
  
- Richiesta DISCO (utilizzando la [DiscoveryClientProtocol](https://go.microsoft.com/fwlink/?LinkId=94777) dai servizi Web ASP.NET) all'indirizzo fornito.  
  
 Lo strumento Svcutil.exe consente di generare il client in base al WSDL (Web Services Description Language) o al file dei criteri ricevuto dal servizio. Il nome dell'entità utente (UPN) è generato concatenando il nome utente con "\@" e l'aggiunta di un nome di dominio completo (FQDN). Tuttavia, per gli utenti registrati su Active Directory, questo formato non valido e l'UPN generato dallo strumento provoca un errore nell'autenticazione Kerberos con il messaggio di errore seguente: **Non è riuscito il tentativo di accesso.** Per risolvere questo problema, è necessario correggere manualmente il file client generato da questo strumento.  
  
```  
svcutil.exe [/t:code]  <metadataDocumentPath>* | <url>* | <epr>  
```  
  
## <a name="referencing-and-sharing-types"></a>Riferimento e condivisione dei tipi  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**-reference:\<percorso file >**|Fa riferimento a tipi nell'assembly specificato. Quando si generano client, utilizzare questa opzione per specificare assembly che potrebbero contenere tipi che rappresentano i metadati importati.<br /><br /> Forma abbreviata: `/r`|  
|**/excludeType:\<type>**|Specifica un nome tipo completo o un nome completo del tipo dell’assembly da escludere dai tipi di contratto a cui si fa riferimento.<br /><br /> Forma abbreviata: `/et`|  
  
## <a name="choosing-a-serializer"></a>Scelta di un serializzatore  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/serializer:Auto**|Seleziona automaticamente il serializzatore. Utilizza il serializzatore `DataContract`. In caso di errore, viene utilizzato `XmlSerializer`.<br /><br /> Forma abbreviata: `/ser:Auto`|  
|**/serializer:DataContractSerializer**|Generare tipi di dati che utilizzano il serializzatore `DataContract` per la serializzazione e la deserializzazione.<br /><br /> Forma abbreviata: `/ser:DataContractSerializer`|  
|**/serializer:XmlSerializer**|Genera tipi di dati che utilizzano `XmlSerializer` per la serializzazione e la deserializzazione.<br /><br /> Forma abbreviata: `/ser:XmlSerializer`|  
|**/importXmlTypes**|Configura il serializzatore `DataContract` per importare tipi non `DataContract` come tipi `IXmlSerializable`.<br /><br /> Forma abbreviata: `/ixt`|  
|**/dataContractOnly**|Genera codice solo per i tipi `DataContract`. Vengono generati i tipi `ServiceContract`.<br /><br /> Per questa opzione è necessario specificare soltanto file di metadati locali.<br /><br /> Forma abbreviata: `/dconly`|  
  
## <a name="choosing-a-language-for-the-client"></a>Scelta di un linguaggio per il client  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/Language:\<lingua >**|Specifica il linguaggio di programmazione da utilizzare per la generazione del codice. Fornire un nome di linguaggio registrato nel file Machine.config o il nome completo di una classe che eredita da <xref:System.CodeDom.Compiler.CodeDomProvider>.<br /><br /> Valori: C#, cs, csharp, vb, vbs, visualbasic, vbscript, javascript, c++, mc, cpp<br /><br /> Impostazione predefinita: csharp<br /><br /> Forma abbreviata: `/l`<br /><br /> Per altre informazioni, vedere [classe CodeDomProvider](https://go.microsoft.com/fwlink/?LinkId=94778).|  
  
## <a name="choosing-a-namespace-for-the-client"></a>Scelta di uno spazio dei nomi per il client  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/namespace:\<string,string>**|Specifica un mapping da un WSDL o XML Schema `targetNamespace` a uno spazio dei nomi Common Language Runtime (CLR). L’utilizzo di un carattere jolly (*) per `targetNamespace` consente di eseguire il mapping di tutti i `targetNamespaces` senza un mapping esplicito a quello spazio dei nomi CLR.<br /><br /> Per assicurarsi che il nome del contratto di messaggio non entri in conflitto con il nome dell'operazione, è necessario qualificare il riferimento al tipo con doppi due punti (`::`) o verificare che i nomi siano univoci.<br /><br /> Valore predefinito: Derivato dallo spazio dei nomi di destinazione del documento dello schema per `DataContracts`. Lo spazio dei nomi predefinito viene utilizzato per tutti gli altri tipi generati.<br /><br /> Forma abbreviata: `/n`|  
  
## <a name="choosing-a-data-binding"></a>Scelta di un data binding  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/enableDataBinding**|Implementa l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> su tutti i tipi `DataContract` per consentire il data binding.<br /><br /> Forma abbreviata: `/edb`|  
  
## <a name="generating-configuration"></a>Generazione della configurazione  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/config:\<configFile>**|Specifica il nome file per il file di configurazione generato.<br /><br /> Impostazione predefinita: output.config|  
|**/mergeConfig**|Incorpora la configurazione generata in un file esistente, anziché sovrascrivere il file esistente.|  
|**/noConfig**|Non genera file di configurazione.|  
  
## <a name="see-also"></a>Vedere anche

- [Uso di metadati](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [Panoramica dell'architettura dei metadati](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
