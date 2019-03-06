---
title: Estensibilità dell'archivio
ms.date: 03/30/2017
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
ms.openlocfilehash: 8f317e8e0864dd6c4595ac669611594c843b277c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375428"
---
# <a name="store-extensibility"></a>Estensibilità dell'archivio
<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> consente agli utenti di promuovere proprietà personalizzate specifiche dell'applicazione che possono essere usate per eseguire query per istanze nel database di persistenza. L'atto di promuovere una proprietà fa in modo che il valore sia disponibile all'interno di una visualizzazione speciale nel database. Queste proprietà promosse, ovvero proprietà che possono essere usate nelle query utente, possono essere di tipi semplici, ad esempio Int64, Guid, String e DateTime o di un tipo binario serializzato (byte[]).  
  
 La classe <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> dispone del metodo <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> che può essere usato per promuovere una proprietà come proprietà utilizzabile nelle query. Il seguente è un esempio end-to-end di estensibilità dell'archivio.  
  
1.  In questo scenario di esempio un'applicazione di elaborazione dei documenti (DP, Document Processing) dispone di flussi di lavoro in ognuno dei quali vengono usate attività personalizzate per l'elaborazione dei documenti. Questi flussi di lavoro dispongono di un set di variabili di stato che devono essere rese visibili all'utente finale. A tale scopo, l'applicazione DP fornisce un'estensione dell'istanza di tipo <xref:System.Activities.Persistence.PersistenceParticipant>, usata da attività per fornire le variabili di stato.  
  
    ```  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        public string DocumentId;  
        public string ApprovalStatus;  
        public string UserName;  
        public DateTime LastUpdateTime;  
    }  
    ```  
  
2.  La nuova estensione viene quindi aggiunta all'host.  
  
    ```  
    static Activity workflow = CreateWorkflow();  
    WorkflowApplication application = new WorkflowApplication(workflow);  
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();  
    application.Extensions.Add(documentStatusExtension);  
    ```  
  
     Per altre informazioni sull'aggiunta di un partecipante di persistenza personalizzato, vedere la [partecipanti di persistenza](../../../docs/framework/windows-workflow-foundation/persistence-participants.md) esempio.  
  
3.  Le attività personalizzate nell'applicazione DP popolano diversi campi di stato nel **Execute** (metodo).  
  
    ```  
    public override void Execute(CodeActivityContext context)  
    {  
        // ...  
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();  
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";  
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = "Approved";  
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();  
        // ...  
    }  
    ```  
  
4.  Quando un'istanza del flusso di lavoro raggiunge un punto di persistenza, il **CollectValues** metodo per il **DocumentStatusExtension** partecipante di persistenza Salva queste proprietà nei dati di persistenza raccolta.  
  
    ```  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        const XNamespace xNS = XNamespace.Get("http://contoso.com/DocumentStatus");  
  
        protected override void CollectValues(out IDictionary<XName, object> readWriteValues, out IDictionary<XName, object> writeOnlyValues)  
        {  
            readWriteValues = new Dictionary<XName, object>();  
            readWriteValues.Add(xNS.GetName("UserName"), this.UserName);  
            readWriteValues.Add(xNS.GetName("ApprovalStatus"), this.ApprovalStatus);  
            readWriteValues.Add(xNS.GetName("DocumentId"), this.DocumentId);  
            readWriteValues.Add(xNS.GetName("LastModifiedTime"), this.LastUpdateTime);  
  
            writeOnlyValues = null;  
        }  
        // ...  
    }  
    ```  
  
    > [!NOTE]
    >  Tutte queste proprietà vengono passate a **SqlWorkflowInstanceStore** con il framework di persistenza tramite il **Saveworkflowcommand** raccolta.  
  
5.  L'applicazione DP Inizializza il Store di istanza del flusso di lavoro SQL e richiama il **Promote** metodo per promuovere questi dati.  
  
    ```  
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);  
  
    List<XName> variantProperties = new List<XName>()   
    {   
        xNS.GetName("UserName"),   
        xNS.GetName("ApprovalStatus"),   
        xNS.GetName("DocumentId"),   
        xNS.GetName("LastModifiedTime")   
    };  
  
    store.Promote("DocumentStatus", variantProperties, null);  
    ```  
  
     Queste informazioni di innalzamento di livello, in base **SqlWorkflowInstanceStore** inserisce le proprietà dei dati nelle colonne delle [InstancePromotedProperties](#InstancePromotedProperties) visualizzazione.
  
6.  Per eseguire una query su un subset dei dati dalla tabella di promozione, viene aggiunta una vista personalizzata nella parte superiore di tale vista da parte dell'applicazione DP.  
  
    ```  
    create view [dbo].[DocumentStatus] with schemabinding  
    as  
        select  P.[InstanceId] as [InstanceId],  
            P.Value1 as [UserName],  
            P.Value2 as [ApprovalStatus],  
            P.Value3 as [DocumentId],  
            P.Value4 as [LastUpdatedTime]  
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P  
    where P.PromotionName = N'DocumentStatus'  
    go  
    ```  
  
## <a name="InstancePromotedProperties"></a> [System.Activities.DurableInstancing.InstancePromotedProperties] view  
  
|Nome colonna|Tipo di colonna|Descrizione|  
|-----------------|-----------------|-----------------|  
|InstanceId|GUID|Istanza del flusso di lavoro a cui appartiene questa promozione.|  
|PromotionName|nvarchar(400)|Nome della promozione stessa.|  
|Value1, Value2, Value3,..,Value32|sql_variant|Valore della proprietà promossa stessa. In sql_variant possono rientrare la maggior parte dei tipi di dati primitivi SQL, eccetto stringhe e blob binari la cui lunghezza supera gli 8000 byte.|  
|Value33, Value34, Value35, …, Value64|varbinary(max)|Valore di proprietà promosse dichiarate in modo esplicito come varbinary (valore massimo).|
