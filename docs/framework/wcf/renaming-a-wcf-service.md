---
title: Ridenominazione di un servizio WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 8cb86621972423f55bfa18c60c1d4eb60cacb205
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651055"
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="397dd-102">Ridenominazione di un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="397dd-102">Renaming a WCF Service</span></span>
<span data-ttu-id="397dd-103">In questo argomento viene descritto come ridenominare un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="397dd-103">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="397dd-104">Ridenominazione di un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="397dd-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="397dd-105">Eseguire la procedura seguente per rinominare un servizio in un modello di Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="397dd-105">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="397dd-106">Modificare il nome della classe che implementa il servizio.</span><span class="sxs-lookup"><span data-stu-id="397dd-106">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="397dd-107">Nel file di configurazione del servizio, impostare il nome del servizio sul nuovo nome scelto, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="397dd-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="397dd-108">A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.</span><span class="sxs-lookup"><span data-stu-id="397dd-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="397dd-109">Se il servizio è WebHosted, utilizza un file \*.svc.</span><span class="sxs-lookup"><span data-stu-id="397dd-109">If your service is webhosted, it uses an \*.svc file.</span></span> <span data-ttu-id="397dd-110">Aprire questo file e modificare il nome del servizio, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="397dd-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="397dd-111">Questo passaggio non è necessario per le applicazioni indipendenti, in quanto questo tipo di applicazione non prevede alcun file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="397dd-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="397dd-112">Ridenominazione del contratto di un servizio WCF</span><span class="sxs-lookup"><span data-stu-id="397dd-112">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="397dd-113">Per ridenominare il contratto di servizio, attenersi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="397dd-113">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="397dd-114">Modificare il nome del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="397dd-114">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="397dd-115">Nel file di configurazione del servizio, impostare il nome del contratto di servizio sul nuovo nome scelto, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="397dd-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="397dd-116">A seconda del modello di hosting utilizzato, il file di configurazione può essere app.config oppure web.config.</span><span class="sxs-lookup"><span data-stu-id="397dd-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
