---
title: 'Procedura: Eseguire query in un Batch (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: e5cd44ee7c3b2c2744e87ebf66973b637961893c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876265"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Procedura: Eseguire query in un Batch (WCF Data Services)
Tramite il [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] libreria client, è possibile eseguire più di una query sul servizio dati in un unico batch. Per altre informazioni, vedere [operazioni di invio in batch](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come chiamare il metodo <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A> per eseguire una matrice di oggetti <xref:System.Data.Services.Client.DataServiceRequest%601> contenente query che restituiscono gli oggetti `Customers` e `Products` dal servizio dati Northwind. La raccolta di oggetti <xref:System.Data.Services.Client.QueryOperationResponse%601> inclusa nell'oggetto <xref:System.Data.Services.Client.DataServiceResponse> restituito viene enumerata, allo stesso modo della raccolta di oggetti inclusa in ogni oggetto <xref:System.Data.Services.Client.QueryOperationResponse%601>.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
