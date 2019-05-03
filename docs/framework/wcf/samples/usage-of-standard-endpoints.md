---
title: Uso di endpoint standard
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: 4ef0714acad12db1414e34fbb476b4ae7d1d9fb2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006334"
---
# <a name="usage-of-standard-endpoints"></a>Uso di endpoint standard

In questo esempio viene illustrato come usare endpoint standard in file di configurazione del servizio. Un endpoint standard consente all'utente di semplificare le definizioni degli endpoint usando una singola proprietà per descrivere un indirizzo, un'associazione e una combinazione del contratto con proprietà aggiuntive associate. In questo esempio viene descritto come definire e implementare un endpoint standard personalizzato e come definire proprietà specifiche nell'endpoint.

## <a name="sample-details"></a>Dettagli dell'esempio

È possibile specificare gli endpoint del servizio fornendo tre parametri: indirizzo, associazione e contratto. Gli altri parametri che è possibile fornire includono la configurazione del comportamento, le intestazioni, l'URI di ascolto e così via. In alcuni casi, alcuni o tutti gli indirizzi, le associazioni e i contratti dispongono di valori che non possono essere modificati. Per questo motivo, è possibile usare endpoint standard. Alcuni esempi di tali endpoint includono endpoint per lo scambio di metadati ed endpoint di individuazione. Gli endpoint standard migliorano inoltre l'usabilità consentendo la configurazione degli endpoint del servizio senza che sia necessario fornire informazioni di natura fissa o creare endpoint standard personalizzati, migliorando ad esempio l'usabilità attraverso la specifica di un set limitato di valori predefiniti e la conseguente riduzione del livello di dettaglio dei file di configurazione.

Questo esempio è costituito da due progetti, ovvero dal servizio che definisce due endpoint standard e dal client che comunica con il servizio. Il modo in cui gli endpoint standard sono definiti per il servizio nel file di configurazione è illustrato nell'esempio seguente.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <extensions>
      <endpointExtensions>
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />
      </endpointExtensions>
    </extensions>
    <services>
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />
        <endpoint kind="mexEndpoint" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="True"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <standardEndpoints>
      <customEndpoint>
        <standardEndpoint property="True" />
      </customEndpoint>
    </standardEndpoints>
  </system.serviceModel>
</configuration>
```

Il primo endpoint definito per il servizio è di tipo `customEndpoint`, la cui definizione è inclusa nella sezione `<standardEndpoints>` dove alla proprietà `property` è assegnato il valore `true`. Si tratta del caso di un endpoint personalizzato con una nuova proprietà. Il secondo endpoint corrisponde a un endpoint di metadati, in cui i valori per indirizzo, associazione e contratto sono fissi.

Per definire l'elemento dell'endpoint standard, è necessario creare una classe che deriva da `StandardEndpointElement`. In questo esempio la classe `CustomEndpointElement` è stata definita come illustrato nell'esempio seguente.

```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```

Nella funzione `CreateServiceEndpoint` viene creato un oggetto `CustomEndpoint`. La relativa definizione è illustrata nell'esempio seguente:

```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    {
    }

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    {
    }

    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    public bool Property
    {
        get;
        set;
    }
}
```

 Per stabilire la comunicazione tra il servizio e il client, nel client viene creato un riferimento al servizio. Quando l'esempio viene compilato ed eseguito, il servizio viene eseguito e il client comunica con il servizio. Si noti che il riferimento al servizio deve essere aggiornato ogni volta che viene apportata una modifica nel servizio.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Usa Visual Studio 2012, aprire il file standardEndpoints.

2. Consentire l'avvio di più progetti.

    1. Nelle **Esplora soluzioni**, fare doppio clic su soluzione Standard Endpoints, quindi selezionare **proprietà**.

    2. Nelle **proprietà comuni**, selezionare **progetto di avvio**, quindi fare clic su **progetti di avvio multipli**.

    3. Spostare il progetto di servizio all'inizio dell'elenco, con la **azione** impostata su **avviare**.

    4. Spostare il progetto Client dopo il progetto di servizio, anche con il **azione** impostata su **avviare**.

         In questo modo si specifica che il progetto Client viene eseguito dopo il progetto Service.

3. Per eseguire la soluzione, premere F5.

> [!NOTE]
> Se questi passaggi risolve il problema, assicurarsi che l'ambiente è stato configurato correttamente, usando la procedura seguente:
>
> 1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).
> 2. Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](building-the-samples.md).
> 3. Per eseguire l'esempio in una o più configurazioni di computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`
