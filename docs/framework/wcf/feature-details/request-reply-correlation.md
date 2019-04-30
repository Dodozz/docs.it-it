---
title: Correlazione request/reply
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: c38854ad42ad4dddce5171482f3ddcfe5bd16b61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991133"
---
# <a name="request-reply-correlation"></a>Correlazione request/reply
Correlazione request / reply viene usata con un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia per implementare un'operazione bidirezionale in un servizio del flusso di lavoro e con un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> coppia che richiama un'operazione bidirezionale in un altro Web servizio. Quando si richiama un'operazione bidirezionale in un servizio WCF, il servizio può essere una tradizionale servizio di Windows Communication Foundation (WCF) basato su codice imperativo o può essere un servizio del flusso di lavoro. Per usare la correlazione request/reply è necessario usare un'associazione bidirezionale, ad esempio <xref:System.ServiceModel.BasicHttpBinding>. Se si richiama o implementa un'operazione bidirezionale, i passaggi dell'inizializzazione della correlazione sono simili e vengono trattati in questa sezione.  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a>Utilizzo della correlazione in un'operazione bidirezionale con Receive/SendReply  
 Oggetto <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia viene usata per implementare un'operazione bidirezionale in un servizio del flusso di lavoro. Il runtime usa la correlazione request/reply per garantire che la risposta venga inviata al chiamante corretto. Se un flusso di lavoro viene ospitato mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, come nel caso dei servizi flusso di lavoro, è sufficiente l'inizializzazione della correlazione predefinita. In questo scenario, un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia viene usata da un flusso di lavoro e sarà necessaria alcuna configurazione di correlazione specifico.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a>Inizializzazione esplicita della correlazione Request/Reply  
 Se altre operazioni bidirezionali vengono eseguite in parallelo, è necessario configurare la correlazione in modo esplicito. Questa operazione può essere eseguita specificando un <xref:System.ServiceModel.Activities.CorrelationHandle> e <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, o posizionando il <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> all'interno di un <xref:System.ServiceModel.Activities.CorrelationScope>. In questo esempio, la correlazione request / reply viene configurata in un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia.  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 Anziché configurare la correlazione in modo esplicito, è possibile usare un'attività <xref:System.ServiceModel.Activities.CorrelationScope>. <xref:System.ServiceModel.Activities.CorrelationScope> fornisce un oggetto <xref:System.ServiceModel.Activities.CorrelationHandle> implicito per le attività della messaggistica in esso contenute. In questo esempio, un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> coppia è contenuta all'interno di un <xref:System.ServiceModel.Activities.CorrelationScope>. Non è richiesta alcuna configurazione di correlazione esplicita.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =   
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 Se sono necessarie ulteriori correlazioni, è possibile configurarle usando la proprietà <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> delle rispettive attività di messaggistica mediante i tipi `CorrelationInitializer` desiderati.  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a>Utilizzo della correlazione in un'operazione bidirezionale con Send/ReceiveReply  
 Mentre il <xref:System.ServiceModel.Activities.Receive> attività può essere utilizzata solo in un servizio del flusso di lavoro ospitato da <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> e il <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> coppia può essere usata in qualsiasi flusso di lavoro che deve richiamare un metodo in un servizio Web. Se il flusso di lavoro è ospitato usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>, viene applicata la correlazione predefinita descritta nella sezione precedente. In caso contrario, è necessario configurare la correlazione in modo esplicito mediante gli elementi <xref:System.ServiceModel.Activities.CorrelationInitializer> e <xref:System.ServiceModel.Activities.CorrelationHandle>oppure tramite la gestione esplicita dell'handle dell'elemento <xref:System.ServiceModel.Activities.CorrelationScope>.  
  
 Quando si usa **Aggiungi riferimento al servizio** in un servizio con operazioni bidirezionali, vengono generate attività che eseguono il wrapping una <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> associare in modo esplicito l'attività internamente con la correlazione Request/Reply specificato.
