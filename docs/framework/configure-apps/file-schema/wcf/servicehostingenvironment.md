---
title: <serviceHostingEnvironment>
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 16dacee89576b4ede0f2f80255ba8a0dcbc8c0dc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610182"
---
# <a name="servicehostingenvironment"></a>\<serviceHostingEnvironment>
Questo elemento definisce il tipo di cui l'ambiente host del servizio crea un'istanza per un determinato trasporto. Se questo elemento è vuoto, viene usato il tipo predefinito. Questo elemento può essere usato solo nei file di configurazione a livello di applicazione o computer.  
  
 \<system.ServiceModel>  
\<ServiceHostingEnvironment>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean"
                           minFreeMemoryPercentageToActivateService="Integer"
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|aspNetCompatibilityEnabled|Valore booleano che indica se la modalità di compatibilità con ASP.NET è stata attivata per l'applicazione corrente. Il valore predefinito è `false`.<br /><br /> Quando questo attributo è impostato su `true`, le richieste ai servizi Windows Communication Foundation (WCF) passano attraverso la pipeline HTTP ASP.NET e comunicazione tra protocolli non HTTP non è consentito. Per altre informazioni, vedere [servizi WCF e ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).|  
|minFreeMemoryPercentageToActivateService|Valore intero che specifica la quantità minima di memoria libera che deve essere disponibile per il sistema, prima di poter attivare un servizio WCF. **Attenzione:**  Se si specifica questo attributo con attendibilità parziale nel file Web. config di un servizio WCF verrà generato un <xref:System.Security.SecurityException> quando viene eseguito il servizio.|  
|multipleSiteBindingsEnabled|Valore booleano che specifica se sono abilitate più associazioni IIS per sito.<br /><br /> IIS è costituito da siti Web contenitori di applicazioni virtuali che includono directory virtuali. È possibile accedere all'applicazione in un sito tramite una o più associazioni IIS. Un'associazione IIS fornisce due tipi di informazioni: un protocollo di associazione e delle informazioni di associazione. Il protocollo di associazione definisce lo schema in base al quale ha luogo la comunicazione, mentre le informazioni di associazione sono usate per accedere al sito. Un esempio di protocollo di associazione è HTTP. Le informazioni di associazione possono contenere un indirizzo IP, una porta, un'intestazione host, e così via.<br /><br /> In IIS è disponibile il supporto per specificare più associazioni per sito, questo comporta la presenza di più indirizzi di base per schema. Tuttavia, un servizio Windows Communication Foundation (WCF) ospitato in un sito consente l'associazione a un solo indirizzo di base per schema.<br /><br /> Per abilitare più associazioni IIS per sito per un servizio Windows Communication Foundation (WCF), impostare questo attributo su `true`. Si noti che l'associazione di più siti è supportata solo per il protocollo HTTP. L'indirizzo degli endpoint nel file di configurazione deve essere un URI completo.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|Raccolta di elementi di configurazione che specificano i filtri di prefisso degli indirizzi di base usati dall'host del servizio.|  
|[\<serviceActivations>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceactivations.md)|Sezione di configurazione in cui vengono descritte le impostazioni di attivazione.|  
|[\<transportConfigurationTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|Raccolta di elementi di configurazione che identificano il tipo di un determinato trasporto.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|serviceModel|L'elemento radice di tutti gli elementi di configurazione di Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, i servizi WCF vengono eseguiti side-by-side con ASP.NET nei domini applicazioni ospitati. Benché WCF e ASP.NET possano coesistere nello stesso dominio applicazione, per impostazione predefinita le richieste WCF non vengono elaborate dalla pipeline HTTP ASP.NET. Di conseguenza, diversi elementi della piattaforma delle applicazioni ASP.NET non sono disponibili per i servizi WCF. Segue un elenco di tali elementi.  
  
- Autorizzazione file/URL di ASP.NET  
  
- Rappresentazione di ASP.NET  
  
- Stato sessione basato su cookie  
  
- HttpContext.Current  
  
- Estensibilità della pipeline tramite HttpModule personalizzato  
  
 Se i servizi WCF devono funzionare nel contesto ASP.NET e comunicano solo su HTTP, è possibile usare la modalità di compatibilità con ASP.NET di WCF. Questa modalità viene attivata quando l'attributo `aspNetCompatibilityEnabled` è impostato su `true` a livello di applicazione. Le implementazioni dei servizi devono usare la classe <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> per dichiarare la propria capacità di essere in esecuzione in tale modalità di compatibilità. Quando la modalità di compatibilità è attiva si verifica quanto segue:  
  
- L'autorizzazione file/URL di ASP.NET viene applicata prima dell'autorizzazione WCF. Le decisioni di autorizzazione si basano sull'identità a livello di trasporto della richiesta. Le identità a livello di messaggio vengono ignorate.  
  
- L'esecuzione delle operazioni dei servizi WCF inizia nel contesto di rappresentazione di ASP.NET. Se per un servizio specifico sono attivate sia la rappresentazione di ASP.NET sia la rappresentazione di WCF, il sistema applica il contesto di rappresentazione di WCF.  
  
- HttpContext.Current può essere usato dal codice dei servizi WCF. Inoltre, ai servizi viene impedito di esporre endpoint non HTTP.  
  
- Le richieste WCF vengono elaborate dalla pipeline ASP.NET. Le richieste WCF possono inoltre essere elaborate dagli elementi HttpModules configurati per agire sulle richieste in ingresso. Questi elementi possono includere componenti della piattaforma di ASP.NET (ad esempio <xref:System.Web.SessionState.SessionStateModule>) nonché moduli personalizzati di terze parti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene mostrato come abilitare la modalità di compatibilità con ASP.  
  
## <a name="code"></a>Codice  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)
- [Servizi WCF e ASP.NET](../../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
