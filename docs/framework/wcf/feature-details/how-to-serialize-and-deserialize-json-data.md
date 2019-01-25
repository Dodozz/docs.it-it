---
title: 'Procedura: Serializzare e deserializzare dati JSON'
ms.date: 03/30/2017
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 797b29fd7ddecd3e3ed85f8cb3a6df93044942ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704342"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a>Procedura: Serializzare e deserializzare dati JSON
JSON (JavaScript Object Notation) è un efficiente formato di codifica dati che consente scambi rapidi di piccole quantità di dati tra browser client e servizi Web compatibili con AJAX.  
  
 In questo argomento viene descritto come serializzare oggetti di tipo .NET in dati con codifica JSON e quindi come deserializzare i dati in formato JSON in istanze di tipi .NET utilizzando <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>. In questo esempio viene utilizzato un contratto dati per illustrare la serializzazione e la deserializzazione di un tipo `Person` definito dall'utente.  
  
 In genere, la serializzazione JSON e la deserializzazione viene gestita automaticamente da Windows Communication Foundation (WCF) quando si usano tipi di contratto dati nelle operazioni del servizio esposte su endpoint compatibili con AJAX. Tuttavia, in alcuni casi potrebbe essere necessario utilizzare direttamente dati JSON, come nel caso dello scenario descritto in questo argomento.  
  
> [!NOTE]
>  Se si verifica un errore durante la serializzazione di una risposta in uscita nel server o se l'operazione di risposta genera un'eccezione per qualche altro motivo, è possibile che l'errore non venga restituito al client.  
  
 In questo argomento si basa sul [serializzazione JSON](../../../../docs/framework/wcf/samples/json-serialization.md) esempio.  
  
### <a name="to-define-the-data-contract-for-a-person"></a>Per definire il contratto dati per Person  
  
1.  Definire il contratto dati per `Person` collegando l'oggetto <xref:System.Runtime.Serialization.DataContractAttribute> alla classe e l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> ai membri da serializzare. Per altre informazioni sui contratti dati, vedere [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
    ```csharp  
    [DataContract]  
    internal class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a>Per serializzare un'istanza di tipo Person in JSON  
  
1.  Creare un'istanza del tipo `Person`.  
  
    ```csharp  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  Serializzare l'oggetto `Person` in un flusso di memoria utilizzando <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```csharp  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  Utilizzare il metodo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> per scrivere dati JSON nel flusso.  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  Visualizzare l'output JSON.  
  
    ```csharp  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a>Per deserializzare un'istanza di tipo Person da JSON  
  
1.  Deserializzare i dati con codifica JSON in una nuova istanza di `Person` utilizzando il metodo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> di <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.  
  
    ```csharp  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  Visualizzare i risultati.  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a>Esempio  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    //Create User object.  
    User user = new User("Bob", 42);  
  
    //Create a stream to serialize the object to.  
    MemoryStream ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    User deserializedUser = new User();  
    MemoryStream ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
>  Il serializzatore JSON genera un'eccezione di serializzazione per i contratti dati che dispongono di più membri con lo stesso nome, come illustrato nel codice di esempio seguente.  
  
```csharp  
[DataContract]  
public class TestDuplicateDataBase  
{  
    [DataMember]  
    public int field1 = 123;  
}

[DataContract]  
public class TestDuplicateDataDerived : TestDuplicateDataBase  
{  
    [DataMember]  
    public new int field1 = 999;  
}  
```  
  
## <a name="see-also"></a>Vedere anche
- [Serializzazione JSON autonoma](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [Supporto per JSON e altri formati di trasferimento dati](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
