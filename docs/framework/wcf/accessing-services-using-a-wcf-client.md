---
title: Accesso ai servizi tramite client WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 6bf683cdd0a03a5d1dbc452c28e7b33911464f09
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297252"
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="1e904-102">Accesso ai servizi tramite client WCF</span><span class="sxs-lookup"><span data-stu-id="1e904-102">Accessing Services Using a WCF Client</span></span>

<span data-ttu-id="1e904-103">Dopo aver creato un servizio, il passaggio successivo consiste nel creare un proxy client WCF.</span><span class="sxs-lookup"><span data-stu-id="1e904-103">After you create a service, the next step is to create a WCF client proxy.</span></span> <span data-ttu-id="1e904-104">Un'applicazione client usa il proxy client WCF per comunicare con il servizio.</span><span class="sxs-lookup"><span data-stu-id="1e904-104">A client application uses the WCF client proxy to communicate with the service.</span></span> <span data-ttu-id="1e904-105">Le applicazioni client importano di norma i metadati del servizio per generare codice client WCF che può essere utilizzato per richiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="1e904-105">Client applications usually import a service's metadata to generate WCF client code that can be used to invoke the service.</span></span>

 <span data-ttu-id="1e904-106">Di seguito sono indicati i passaggi di base per la creazione di un client WCF:</span><span class="sxs-lookup"><span data-stu-id="1e904-106">The basic steps for creating a WCF client include the following:</span></span>

1. <span data-ttu-id="1e904-107">Compilare il codice del servizio.</span><span class="sxs-lookup"><span data-stu-id="1e904-107">Compile the service code.</span></span>

2. <span data-ttu-id="1e904-108">Generare il proxy client WCF.</span><span class="sxs-lookup"><span data-stu-id="1e904-108">Generate the WCF client proxy.</span></span>

3. <span data-ttu-id="1e904-109">Creare un'istanza del proxy client WCF.</span><span class="sxs-lookup"><span data-stu-id="1e904-109">Instantiate the WCF client proxy.</span></span>

<span data-ttu-id="1e904-110">Il proxy client WCF può essere generato manualmente utilizzando Service Model Metadata Utility Tool (SvcUtil.exe) per altre informazioni, vedere [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1e904-110">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="1e904-111">Il proxy client WCF può essere generato anche in Visual Studio usando il **Aggiungi riferimento al servizio** funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1e904-111">The WCF client proxy can also be generated within Visual Studio using the **Add Service Reference**  feature.</span></span> <span data-ttu-id="1e904-112">Per generare il proxy client WCF usando l'uno o l'altro metodo, è necessario che il servizio sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1e904-112">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="1e904-113">Se il servizio è self-hosted, è necessario eseguire l'host.</span><span class="sxs-lookup"><span data-stu-id="1e904-113">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="1e904-114">Se il servizio è ospitato in IIS/WAS, non è necessario effettuare nessun'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="1e904-114">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>

## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="1e904-115">Strumento ServiceModel Metadata Utility Tool</span><span class="sxs-lookup"><span data-stu-id="1e904-115">ServiceModel Metadata Utility Tool</span></span>
 <span data-ttu-id="1e904-116">Il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) è uno strumento da riga di comando per la generazione di codice dai metadati.</span><span class="sxs-lookup"><span data-stu-id="1e904-116">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="1e904-117">Di seguito è riportato un esempio di utilizzo di un comando Svcutil.exe di base.</span><span class="sxs-lookup"><span data-stu-id="1e904-117">The following use is an example of a basic Svcutil.exe command.</span></span>

```
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 <span data-ttu-id="1e904-118">In alternativa, è possibile usare Svcutil.exe con file WSDL (Web Services Description Language) e XSD (XML Schema Definition) sul file system.</span><span class="sxs-lookup"><span data-stu-id="1e904-118">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>

```
Svcutil.exe <list of WSDL and XSD files on file system>
```

 <span data-ttu-id="1e904-119">Il risultato è un file di codice che contiene il codice client WCF che l'applicazione client può usare per richiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="1e904-119">The result is a code file that contains WCF client code that the client application can use to invoke the service.</span></span>

 <span data-ttu-id="1e904-120">È inoltre possibile usare lo strumento per generare file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1e904-120">You can also use the tool to generate configuration files.</span></span>

```
Svcutil.exe <file1 [,file2]>
```

 <span data-ttu-id="1e904-121">Se viene fornito un solo nome file, si tratta del nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="1e904-121">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="1e904-122">Se vengono forniti due nomi file, il primo indica un file di configurazione di input il cui contenuto viene unito con la configurazione generata e scritto nel secondo file.</span><span class="sxs-lookup"><span data-stu-id="1e904-122">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> <span data-ttu-id="1e904-123">Per altre informazioni sulla configurazione, vedere [configurazione di associazioni per i servizi](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1e904-123">For more information about configuration, see [Configuring Bindings for Services](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e904-124">Le richieste di metadati non protette generano rischi esattamente che effettua le richieste di rete non protetta: Se non si è certi che l'endpoint che si sta comunicando sia effettivamente chi dichiara di che è, le informazioni recuperate potrebbero essere i metadati da un servizio dannoso.</span><span class="sxs-lookup"><span data-stu-id="1e904-124">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>

## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="1e904-125">Aggiungi riferimento al servizio in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1e904-125">Add Service Reference in Visual Studio</span></span>

 <span data-ttu-id="1e904-126">Pulsante destro del mouse con il servizio in esecuzione, fare clic sul progetto che conterrà il proxy client WCF e selezionare **Add** > **riferimento al servizio**.</span><span class="sxs-lookup"><span data-stu-id="1e904-126">With the service running, right click the project that will contain the WCF client proxy and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="1e904-127">Nel **Aggiungi finestra di dialogo riferimento al servizio**, digitare l'URL per il servizio da chiamare e fare clic sui **Vai** pulsante.</span><span class="sxs-lookup"><span data-stu-id="1e904-127">In the **Add Service Reference Dialog**, type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="1e904-128">Nella finestra di dialogo viene visualizzato un elenco dei servizi disponibili all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="1e904-128">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="1e904-129">Fare doppio clic sul servizio per visualizzare i contratti e operazioni disponibili, specificare uno spazio dei nomi per il codice generato e fare clic sui **OK** pulsante.</span><span class="sxs-lookup"><span data-stu-id="1e904-129">Double click the service to see the contracts and operations available, specify a namespace for the generated code, and click the **OK** button.</span></span>

## <a name="example"></a><span data-ttu-id="1e904-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e904-130">Example</span></span>
 <span data-ttu-id="1e904-131">Nell'esempio di codice seguente viene illustrato un contratto di servizio creato per un servizio.</span><span class="sxs-lookup"><span data-stu-id="1e904-131">The following code example shows a service contract created for a service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```

```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```

 <span data-ttu-id="1e904-132">Lo strumento ServiceModel Metadata utility Tool e **Aggiungi riferimento al servizio** in Visual Studio genera la seguente classe client WCF.</span><span class="sxs-lookup"><span data-stu-id="1e904-132">The ServiceModel Metadata utility tool and **Add Service Reference** in Visual Studio generates the following WCF client class.</span></span> <span data-ttu-id="1e904-133">La classe eredita dalla classe generica <xref:System.ServiceModel.ClientBase%601> e implementa l'interfaccia `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="1e904-133">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="1e904-134">Lo strumento genera anche l'interfaccia `ICalculator` (procedure non illustrata di seguito).</span><span class="sxs-lookup"><span data-stu-id="1e904-134">The tool also generates the `ICalculator` interface (not shown here).</span></span>

```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```

```vb
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```

## <a name="using-the-wcf-client"></a><span data-ttu-id="1e904-135">Utilizzo del client WCF</span><span class="sxs-lookup"><span data-stu-id="1e904-135">Using the WCF Client</span></span>
 <span data-ttu-id="1e904-136">Per usare il client di WCF, creare un'istanza del client WCF e quindi chiamarne i metodi, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1e904-136">To use the WCF client, create an instance of the WCF client, and then call its methods, as shown in the following code.</span></span>

```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```

## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="1e904-137">Debug delle eccezioni generate da un client</span><span class="sxs-lookup"><span data-stu-id="1e904-137">Debugging Exceptions Thrown by a Client</span></span>

<span data-ttu-id="1e904-138">Molte eccezioni generate da un client WCF sono causate da un'eccezione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="1e904-138">Many exceptions thrown by a WCF client are caused by an exception on the service.</span></span> <span data-ttu-id="1e904-139">Di seguito ne vengono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="1e904-139">Some examples of this are:</span></span>

-   <xref:System.Net.Sockets.SocketException><span data-ttu-id="1e904-140">: Una connessione esistente chiusa forzatamente dall'host remoto.</span><span class="sxs-lookup"><span data-stu-id="1e904-140">: An existing connection was forcibly closed by the remote host.</span></span>

-   <xref:System.ServiceModel.CommunicationException><span data-ttu-id="1e904-141">: La connessione sottostante chiusa in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="1e904-141">: The underlying connection was closed unexpectedly.</span></span>

-   <xref:System.ServiceModel.CommunicationObjectAbortedException><span data-ttu-id="1e904-142">: La connessione socket è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="1e904-142">: The socket connection was aborted.</span></span> <span data-ttu-id="1e904-143">Questo problema può essere causato da un errore durante l'elaborazione del messaggio, da un timeout di ricezione superato dall'host remoto o da un problema della risorsa di rete sottostante.</span><span class="sxs-lookup"><span data-stu-id="1e904-143">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>

<span data-ttu-id="1e904-144">Quando si verificano questi tipi di eccezioni, il modo migliore per risolvere il problema è attivare la traccia sul lato servizio e individuare l'eccezione che si è verificata.</span><span class="sxs-lookup"><span data-stu-id="1e904-144">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> <span data-ttu-id="1e904-145">Per ulteriori informazioni sulla traccia, vedere [Tracing](../../../docs/framework/wcf/diagnostics/tracing/index.md) e [tramite la traccia per risolvere i problemi dell'applicazione](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="1e904-145">For more information about tracing, see [Tracing](../../../docs/framework/wcf/diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e904-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e904-146">See also</span></span>

- [<span data-ttu-id="1e904-147">Procedura: Creare un client</span><span class="sxs-lookup"><span data-stu-id="1e904-147">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="1e904-148">Procedura: Accedere ai servizi con un contratto duplex</span><span class="sxs-lookup"><span data-stu-id="1e904-148">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="1e904-149">Procedura: Chiamare operazioni del servizio in modo asincrono</span><span class="sxs-lookup"><span data-stu-id="1e904-149">How to: Call Service Operations Asynchronously</span></span>](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [<span data-ttu-id="1e904-150">Procedura: Accedere ai servizi con contratti unidirezionali e Request/Reply</span><span class="sxs-lookup"><span data-stu-id="1e904-150">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [<span data-ttu-id="1e904-151">Procedura: Accedere a un servizio WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="1e904-151">How to: Access a WSE 3.0 Service</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [<span data-ttu-id="1e904-152">Informazioni sul codice client generato</span><span class="sxs-lookup"><span data-stu-id="1e904-152">Understanding Generated Client Code</span></span>](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)
- [<span data-ttu-id="1e904-153">Procedura: Migliorare il tempo di avvio di applicazioni client WCF usando XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="1e904-153">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [<span data-ttu-id="1e904-154">Specifica del comportamento in fase di esecuzione dei client</span><span class="sxs-lookup"><span data-stu-id="1e904-154">Specifying Client Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="1e904-155">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="1e904-155">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)
