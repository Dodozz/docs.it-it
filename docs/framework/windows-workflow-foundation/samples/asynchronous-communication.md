---
title: Comunicazione asincrona
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: a9da04e2c6d3c131603211f53c54fd25dde8d338
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62005589"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="f8327-102">Comunicazione asincrona</span><span class="sxs-lookup"><span data-stu-id="f8327-102">Asynchronous Communication</span></span>
<span data-ttu-id="f8327-103">Questo esempio viene illustrato come la comunicazione tra due diversi servizi di Windows Workflow Foundation (WF) viene eseguita in modo asincrono per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f8327-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="f8327-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="f8327-104">Demonstrates</span></span>  
 <span data-ttu-id="f8327-105">Comunicazione asincronica tra servizi [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8327-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="f8327-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="f8327-106">Discussion</span></span>  
 <span data-ttu-id="f8327-107">In questo esempio viene illustrata la modalità di esecuzione della comunicazione asincrona tra applicazioni [!INCLUDE[wf1](../../../../includes/wf1-md.md)] tramite le attività di messaggistica fornite da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8327-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="f8327-108">L'esempio è costituito dai tre progetti seguenti.</span><span class="sxs-lookup"><span data-stu-id="f8327-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="f8327-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="f8327-109">CreditCheckService</span></span>  
 <span data-ttu-id="f8327-110">Questo servizio riceve il punteggio del credito di una particolare persona o il valore dell'elemento da acquisire, quindi stabilisce se viene concesso alla persona il credito.</span><span class="sxs-lookup"><span data-stu-id="f8327-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="f8327-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="f8327-111">RentalApprovalService</span></span>  
 <span data-ttu-id="f8327-112">Questo servizio riceve un'applicazione da una persona che richiede credito.</span><span class="sxs-lookup"><span data-stu-id="f8327-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="f8327-113">Il servizio comunica in modo asincrono con `CreditCheckService` per determinare se la richiesta di credito è valida.</span><span class="sxs-lookup"><span data-stu-id="f8327-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="f8327-114">Client</span><span class="sxs-lookup"><span data-stu-id="f8327-114">Client</span></span>  
 <span data-ttu-id="f8327-115">Il client comunica in modo sincrono con `RentalApprovalService` per sapere se il credito è approvato.</span><span class="sxs-lookup"><span data-stu-id="f8327-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f8327-116">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="f8327-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="f8327-117">Fare doppio clic il **AsynchronousCommunication** soluzioni e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f8327-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="f8327-118">Nelle **proprietà comuni**, selezionare **progetto di avvio**e selezionare **progetti di avvio multipli**.</span><span class="sxs-lookup"><span data-stu-id="f8327-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="f8327-119">Spostare **RentalApprovalService** alla prima posizione nell'elenco, seguito da **CreditCheckService**, quindi su **Client**.</span><span class="sxs-lookup"><span data-stu-id="f8327-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="f8327-120">Impostare il **avviare** azione su tutti e tre i progetti.</span><span class="sxs-lookup"><span data-stu-id="f8327-120">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="f8327-121">Fare clic su **OK**, premere F5 per eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="f8327-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8327-122">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="f8327-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f8327-123">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="f8327-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8327-124">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="f8327-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8327-125">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="f8327-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
