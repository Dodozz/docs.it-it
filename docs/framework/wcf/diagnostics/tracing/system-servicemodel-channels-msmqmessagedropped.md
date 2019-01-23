---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 6218948e89288e76034d7c3f032f3c585e286c3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570538"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="8b369-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="8b369-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="8b369-103">MSMQ ha rilasciato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="8b369-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8b369-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b369-104">Description</span></span>  
 <span data-ttu-id="8b369-105">La traccia indica che è stato eliminato un messaggio MSMQ.</span><span class="sxs-lookup"><span data-stu-id="8b369-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="8b369-106">I messaggi MSMQ possono essere eliminati quando Windows Communication Foundation (WCF) (utilizzato con NetMsmqBinding o MsmqIntegrationBinding) non riesce a elaborarli.</span><span class="sxs-lookup"><span data-stu-id="8b369-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="8b369-107">Tali messaggi vengono definiti messaggi non elaborabili.</span><span class="sxs-lookup"><span data-stu-id="8b369-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="8b369-108">Un messaggio non elaborabile viene rilasciato quando la proprietà `ReceiveErrorHandling` su NetMsmqBinding o MsmqIntegrationBinding è impostata su `Drop`.</span><span class="sxs-lookup"><span data-stu-id="8b369-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="8b369-109">Un messaggio eliminato viene rimosso dalla coda e non è più recuperabile.</span><span class="sxs-lookup"><span data-stu-id="8b369-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="8b369-110">Visualizzare [dei messaggi non elaborabili](https://go.microsoft.com/fwlink/?LinkID=99546) per altri dettagli su cui i messaggi diventano non elaborabili e su come configurare il servizio per gestirli in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="8b369-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b369-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b369-111">See also</span></span>
- [<span data-ttu-id="8b369-112">Traccia</span><span class="sxs-lookup"><span data-stu-id="8b369-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8b369-113">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="8b369-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8b369-114">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="8b369-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="8b369-115">Messaggi non elaborabili</span><span class="sxs-lookup"><span data-stu-id="8b369-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
