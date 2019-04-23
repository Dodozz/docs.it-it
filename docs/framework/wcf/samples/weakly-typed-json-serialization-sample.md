---
title: Esempio di serializzazione JSON con tipizzazione debole
ms.date: 03/30/2017
ms.assetid: 0b30e501-4ef5-474d-9fad-a9d559cf9c52
ms.openlocfilehash: b0e9617ad5d616e8921fbf142085f2758f3e0cd4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59303687"
---
# <a name="weakly-typed-json-serialization-sample"></a>Esempio di serializzazione JSON con tipizzazione debole
Quando si serializza un tipo definito dall'utente in un formato di trasmissione specificato o si deserializza un formato di trasmissione in un tipo definito dall'utente, il tipo definito dall'utente specificato deve essere disponibile sia nel servizio che nel client. Per eseguire questa operazione, in genere l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> viene applicato ai tipi definiti dall'utente e l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> viene applicato ai relativi membri. Questo meccanismo viene applicato anche quando si lavora con gli oggetti JavaScript Object Notation (JSON), come descritto nell'argomento [come: Serializzare e deserializzare dati JSON](../../../../docs/framework/wcf/feature-details/how-to-serialize-and-deserialize-json-data.md).  
  
 In alcuni scenari, un servizio Windows Communication Foundation (WCF) o un client deve accedere a oggetti JSON generati da un servizio o client che si trova all'esterno del controllo dello sviluppatore. Come altri servizi Web espongono pubblicamente API JSON, possono diventare poco pratica per gli sviluppatori WCF costruire tipi definiti dall'utente locali nei quali deserializzare oggetti JSON arbitrari. In questo esempio fornisce un meccanismo che consente agli sviluppatori WCF lavorare con oggetti JSON arbitrari, deserializzati, senza creare tipi definiti dall'utente. Questo meccanismo è noto come *serializzazione con tipizzazione debole* di oggetti JSON, perché il tipo nel quale viene deserializzato un oggetto JSON non è noto in fase di compilazione.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Ad esempio, l'API di un servizio Web pubblico restituisce l'oggetto JSON seguente che fornisce alcune informazioni su un utente del servizio.  
  
```json  
{"personal": {"name": "Paul", "age": 23, "height": 1.7, "isSingle": true, "luckyNumbers": [5,17,21]}, "favoriteBands": ["Band ABC", "Band XYZ"]}  
```  
  
 Per deserializzare questo oggetto, un client WCF deve implementare i seguenti tipi definiti dall'utente.  
  
```  
[DataContract]  
 public class MemberProfile  
 {  
     [DataMember]  
     public PersonalInfo personal;  
  
     [DataMember]  
     public string[] favoriteBands;  
 }  
  
 [DataContract]  
 public class PersonalInfo  
 {  
     [DataMember]  
     public string name;  
  
     [DataMember]  
     public int age;  
  
     [DataMember]  
     public double height;  
  
     [DataMember]  
     public bool isSingle;  
  
     [DataMember]  
     public int[] luckyNumbers;  
 }  
```  
  
 Questa operazione può risultare ardua, specialmente se il client deve gestire più di un tipo di oggetto JSON.  
  
 Il tipo `JsonObject` fornito in questo esempio introduce una rappresentazione con tipizzazione debole dell'oggetto JSON deserializzato. `JsonObject` si basa sul mapping naturale tra oggetti JSON e dizionari [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] e sul mapping tra matrici JSON e matrici [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . Nel codice seguente viene illustrato il tipo `JsonObject` .  
  
```  
// Instantiation of JsonObject json omitted  
  
string name = json["root"]["personal"]["name"];  
int age = json["root"]["personal"]["age"];  
double height = json["root"]["personal"]["height"];  
bool isSingle = json["root"]["personal"]["isSingle"];  
int[] luckyNumbers = {  
                                     json["root"]["personal"]["luckyNumbers"][0],  
                                     json["root"]["personal"]["luckyNumbers"][1],  
                                     json["root"]["personal"]["luckyNumbers"][2]   
                                 };  
string[] favoriteBands = {  
                                        json["root"]["favoriteBands"][0],  
                                        json["root"]["favoriteBands"][1]  
                                    };  
```  
  
 Si noti che è possibile "esplorare" oggetti JSON e matrici senza doverne dichiarare il tipo in fase di compilazione. Per una spiegazione dei requisiti per l'oggetto `["root"]` di primo livello, vedere l'argomento [Mapping Between JSON and XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
> [!NOTE]
>  La classe `JsonObject` viene fornita a solo scopo esemplificativo. Non è stata testata completamente e non deve essere utilizzata negli ambienti di produzione. Un'implicazione ovvia della serializzazione JSON con tipizzazione debole è la mancanza di indipendenza dai tipi quando si utilizza `JsonObject`.  
  
 Per utilizzare il tipo `JsonObject` , il contratto dell'operazione client deve utilizzare <xref:System.ServiceModel.Channels.Message> come tipo restituito.  
  
```  
[ServiceContract]  
    interface IClientSideProfileService  
    {  
        // There is no need to write a DataContract for the complex type returned by the service.  
        // The client will use a JsonObject to browse the JSON in the received message.  
  
        [OperationContract]  
        [WebGet(ResponseFormat = WebMessageFormat.Json)]  
        Message GetMemberProfile();  
    }  
```  
  
 Viene quindi creata un'istanza di `JsonObject` come illustrato nel codice seguente.  
  
```  
// Code to instantiate IClientSideProfileService channel omitted…  
  
// Make a request to the service and obtain the Json response  
XmlDictionaryReader reader = channel.GetMemberProfile().GetReaderAtBodyContents();  
  
// Go through the Json as though it is a dictionary. There is no need to map it to a .NET CLR type.  
JsonObject json = new JsonObject(reader);  
```  
  
 Il costruttore `JsonObject` accetta una classe <xref:System.Xml.XmlDictionaryReader>, ottenuta tramite il metodo <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> . Il lettore contiene una rappresentazione XML del messaggio JSON ricevuto dal client. Per altre informazioni, vedere l'argomento [Mapping Between JSON and XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
 Il programma produce l'output seguente:  
  
```  
Service listening at http://localhost:8000/.  
To view the JSON output from the sample, navigate to http://localhost:8000/GetMemberProfile  
This is Paul's page. I am 23 years old and I am 1.7 meters tall.  
I am single.  
My lucky numbers are 5, 17, and 21.  
My favorite bands are Band ABC and Band XYZ.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Compilare la soluzione WeaklyTypedJson.sln come descritto in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Eseguire la soluzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Ajax\WeaklyTypedJson`  
