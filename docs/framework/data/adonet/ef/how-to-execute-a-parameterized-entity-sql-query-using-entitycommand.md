---
title: 'Procedura: Eseguire una Query SQL di entità con parametri tramite EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: a9b4069004cc48fa05efa29b4467aa1dca47fb29
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610097"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a>Procedura: Eseguire una Query SQL di entità con parametri tramite EntityCommand
In questo argomento viene illustrato come eseguire un' [!INCLUDE[esql](../../../../../includes/esql-md.md)] query con parametri utilizzando un <xref:System.Data.EntityClient.EntityCommand> oggetto.  
  
### <a name="to-run-the-code-in-this-example"></a>Per eseguire il codice in questo esempio  
  
1.  Aggiungere il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come costruire una stringa di query con due parametri. Viene quindi creato un oggetto <xref:System.Data.EntityClient.EntityCommand>, vengono aggiunti due parametri alla raccolta <xref:System.Data.EntityClient.EntityParameter> di <xref:System.Data.EntityClient.EntityCommand> e viene scorsa la raccolta di elementi `Contact`.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Eseguire una Query con parametri](https://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)
- [Linguaggio Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
