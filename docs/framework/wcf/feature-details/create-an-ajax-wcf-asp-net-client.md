---
title: Creare un servizio WCF compatibile con AJAX e un Client ASP.NET in Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 06fa3a9d0151f3b4b865c421f9960854ef471377
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807891"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="bede2-102">Procedura: Creare un servizio WCF compatibile con AJAX e un Client ASP.NET che accede a servizio</span><span class="sxs-lookup"><span data-stu-id="bede2-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="bede2-103">In questo argomento viene illustrato come usare Visual Studio per creare un servizio compatibile con AJAX Windows Communication Foundation (WCF) e un client ASP.NET che accede al servizio.</span><span class="sxs-lookup"><span data-stu-id="bede2-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="bede2-104">Creare un'app Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bede2-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="bede2-105">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bede2-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="bede2-106">Dal **File** dal menu **New** > **progetto**</span><span class="sxs-lookup"><span data-stu-id="bede2-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="bede2-107">Nel **nuovo progetto** finestra di dialogo espandere il **installati** > **Visual c#** > **Web** categoria e quindi Selezionare **applicazione Web ASP.NET (.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="bede2-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="bede2-108">Denominare il progetto **SandwichServices** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bede2-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="bede2-109">Nel **nuova applicazione Web ASP.NET** finestra di dialogo, seleziona **vuota** e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="bede2-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Finestra di tipo app web ASP.NET in Visual Studio](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="bede2-111">Aggiungere un web form</span><span class="sxs-lookup"><span data-stu-id="bede2-111">Add a web form</span></span>

1. <span data-ttu-id="bede2-112">Fare clic sul progetto in SandwichServices **Esplora soluzioni** e selezionare **Add** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="bede2-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="bede2-113">Nel **Aggiungi nuovo elemento** finestra di dialogo espandere il **installato** > **Visual c#** > **Web** categoria, quindi Selezionare il **Web Form** modello.</span><span class="sxs-lookup"><span data-stu-id="bede2-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="bede2-114">Accettare il nome predefinito (**WebForm1**), quindi selezionare **Add**.</span><span class="sxs-lookup"><span data-stu-id="bede2-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="bede2-115">*WebForm1.aspx* viene aperto in **origine** visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="bede2-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="bede2-116">Aggiungere il markup seguente all'interno di  **\<corpo >** tag:</span><span class="sxs-lookup"><span data-stu-id="bede2-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="bede2-117">Creare un servizio WCF abilitato per AJAX</span><span class="sxs-lookup"><span data-stu-id="bede2-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="bede2-118">Fare clic sul progetto in SandwichServices **Esplora soluzioni** e selezionare **Add** > **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="bede2-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="bede2-119">Nel **Aggiungi nuovo elemento** finestra di dialogo espandere il **installato** > **Visual c#** > **Web** categoria, quindi Selezionare il **servizio WCF (compatibile con AJAX)** modello.</span><span class="sxs-lookup"><span data-stu-id="bede2-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Modello di elemento (compatibile con AJAX) del servizio WCF in Visual Studio](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="bede2-121">Nome del servizio **CostService** e quindi selezionare **Add**.</span><span class="sxs-lookup"><span data-stu-id="bede2-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="bede2-122">*CostService.svc.cs* viene aperto nell'editor.</span><span class="sxs-lookup"><span data-stu-id="bede2-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="bede2-123">Implementare l'operazione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="bede2-123">Implement the operation in the service.</span></span> <span data-ttu-id="bede2-124">Aggiungere il metodo seguente alla classe CostService per calcolare il costo di una quantità di panini:</span><span class="sxs-lookup"><span data-stu-id="bede2-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="bede2-125">Configurare il client per accedere al servizio</span><span class="sxs-lookup"><span data-stu-id="bede2-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="bede2-126">Aprire il *WebForm1.aspx* del file e selezionare il **progettazione** visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="bede2-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="bede2-127">Dal **View** dal menu **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="bede2-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="bede2-128">Espandere la **AJAX Extensions** nodo e trascinare un **ScriptManager** nel form.</span><span class="sxs-lookup"><span data-stu-id="bede2-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="bede2-129">Nel **origine** consente di visualizzare, aggiungere il codice seguente tra i  **\<ScriptManager >** tag per specificare il percorso del servizio WCF:</span><span class="sxs-lookup"><span data-stu-id="bede2-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="bede2-130">Aggiungere il codice per la funzione Javascript `Calculate()`.</span><span class="sxs-lookup"><span data-stu-id="bede2-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="bede2-131">Inserire il codice seguente nel **head** sezione di web form:</span><span class="sxs-lookup"><span data-stu-id="bede2-131">Place the following code in the **head** section of the web form:</span></span>

    ```html
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
    ```

   <span data-ttu-id="bede2-132">Questo codice chiama il metodo di CostService per calcolare il prezzo per tre panini e quindi Visualizza il risultato nel controllo span chiamato **additionResult**.</span><span class="sxs-lookup"><span data-stu-id="bede2-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="bede2-133">Eseguire il programma</span><span class="sxs-lookup"><span data-stu-id="bede2-133">Run the program</span></span>

<span data-ttu-id="bede2-134">Verificare che l'opzione *WebForm1.aspx* ha lo stato attivo e quindi premere **avviare** pulsante per avviare il client web.</span><span class="sxs-lookup"><span data-stu-id="bede2-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="bede2-135">Il pulsante dispone di un triangolo verde e trovo una **IIS Express (Microsoft Edge)**.</span><span class="sxs-lookup"><span data-stu-id="bede2-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="bede2-136">In alternativa, premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="bede2-136">Or, you can press **F5**.</span></span> <span data-ttu-id="bede2-137">Scegliere il **prezzo di 3 panini** pulsante per generare l'output previsto di "3.75".</span><span class="sxs-lookup"><span data-stu-id="bede2-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="bede2-138">codice di esempio</span><span class="sxs-lookup"><span data-stu-id="bede2-138">Example code</span></span>

<span data-ttu-id="bede2-139">Seguito è riportato il codice completo nel *CostService.svc.cs* file:</span><span class="sxs-lookup"><span data-stu-id="bede2-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

```csharp
using System.ServiceModel;
using System.ServiceModel.Activation;

namespace SandwichServices
{
    [ServiceContract(Namespace = "")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class CostService
    {
        [OperationContract]
        public double CostOfSandwiches(int quantity)
        {
            return 1.25 * quantity;
        }
    }
}
```

<span data-ttu-id="bede2-140">Seguito è riportato l'intero contenuto del *WebForm1.aspx* pagina:</span><span class="sxs-lookup"><span data-stu-id="bede2-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

```aspx-csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="SandwichServices.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
        <asp:ScriptManager ID="ScriptManager1" runat="server">
            <Services>
                <asp:ServiceReference Path="~/CostService.svc" />
            </Services>
        </asp:ScriptManager>

        <input type="button" value="Price of 3 sandwiches" onclick="Calculate()" />
        <br />
        <span id="additionResult"></span>
    </form>
</body>
</html>
```
