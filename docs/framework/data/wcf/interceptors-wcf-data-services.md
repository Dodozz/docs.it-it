---
title: Intercettori (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: 14212c9993d936138df70160e4e49152cd5ff958
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626758"
---
# <a name="interceptors-wcf-data-services"></a>Intercettori (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] consente a un'applicazione di intercettare i messaggi di richiesta in modo che è possibile aggiungere logica personalizzata a un'operazione. È possibile utilizzare questa logica personalizzata per convalidare i dati nei messaggi in ingresso. È inoltre possibile usarla per limitare ulteriormente l'ambito di una richiesta di query, inserendo ad esempio criteri di autorizzazione personalizzati per le singole richieste.  
  
 L'intercettazione viene eseguita specificando metodi attribuiti in modo specifico nel servizio dati. Questi metodi vengono chiamati da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] al momento appropriato durante l'elaborazione del messaggio. Gli intercettori vengono definiti una singole di set di entità e i metodi dell'intercettore non accettano parametri dalla richiesta, come operazioni del servizio. I metodi dell'intercettore di query, chiamati durante l'elaborazione di una richiesta HTTP GET, devono restituire un'espressione lambda che determina se un'istanza di entità dell'intercettore impostata deve essere restituita nei risultati della query. Questa espressione viene usata dal servizio dati per definire ulteriormente l'operazione richiesta. Di seguito viene riportato un esempio di definizione di un intercettore di query.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Per altre informazioni, vedere [Procedura: Intercettare messaggi del servizio dati](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Gli intercettori di modifiche, chiamati durante l'elaborazione di operazioni non di query, devono restituire `void` (`Nothing` in Visual Basic). I metodi dell'intercettore di modifiche devono accettare i due parametri seguenti:  
  
1.  Un parametro di un tipo compatibile con il tipo di entità del set di entità. Quando il servizio dati richiama l'intercettore di modifiche, il valore di questo parametro riflette le informazioni sull'entità inviate dalla richiesta.  
  
2.  Un parametro di tipo <xref:System.Data.Services.UpdateOperations>. Quando il servizio dati richiama l'intercettore di modifiche, il valore di questo parametro riflette l'operazione tentata dalla richiesta.  
  
 Di seguito viene riportato un esempio di definizione di un intercettore di modifiche.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Per altre informazioni, vedere [Procedura: Intercettare messaggi del servizio dati](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Gli attributi che seguono sono supportati per l'intercettazione.  
  
 **[QueryInterceptor(** *EntitySetName* **)]**  
 Metodi a cui è applicato l'attributo <xref:System.Data.Services.QueryInterceptorAttribute> vengono chiamati quando una richiesta GET HTTP viene ricevuta per la risorsa del set di entità di destinazione. Questi metodi devono restituire sempre un'espressione lambda nel formato `Expression<Func<T,bool>>`.  
  
 **[ChangeInterceptor(** *EntitySetName* **)]**  
 Metodi a cui è applicato l'attributo <xref:System.Data.Services.ChangeInterceptorAttribute> vengono chiamati quando una richiesta HTTP diversa da GET viene ricevuta per la risorsa del set di entità di destinazione. Questi metodi devono restituire sempre `void` (`Nothing` in Visual Basic).  
  
 Per altre informazioni, vedere [Procedura: Intercettare messaggi del servizio dati](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche
- [Operazioni di servizio](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)
