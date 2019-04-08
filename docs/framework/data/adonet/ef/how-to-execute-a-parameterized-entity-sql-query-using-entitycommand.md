---
title: 'Procedura: Eseguire una query Entity SQL con parametri tramite EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: 252d04ce96e222526bfd3d3e0b798f1c5edd2c8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079708"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a><span data-ttu-id="bae8f-102">Procedura: Eseguire una query Entity SQL con parametri tramite EntityCommand</span><span class="sxs-lookup"><span data-stu-id="bae8f-102">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>
<span data-ttu-id="bae8f-103">In questo argomento viene illustrato come eseguire un' [!INCLUDE[esql](../../../../../includes/esql-md.md)] query con parametri utilizzando un <xref:System.Data.EntityClient.EntityCommand> oggetto.</span><span class="sxs-lookup"><span data-stu-id="bae8f-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that has parameters by using an <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="bae8f-104">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="bae8f-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="bae8f-105">Aggiungere il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bae8f-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="bae8f-106">Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bae8f-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="bae8f-107">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="bae8f-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="bae8f-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="bae8f-108">Example</span></span>  
 <span data-ttu-id="bae8f-109">Nell'esempio seguente viene illustrato come costruire una stringa di query con due parametri.</span><span class="sxs-lookup"><span data-stu-id="bae8f-109">The following example shows how to construct a query string with two parameters.</span></span> <span data-ttu-id="bae8f-110">Viene quindi creato un oggetto <xref:System.Data.EntityClient.EntityCommand>, vengono aggiunti due parametri alla raccolta <xref:System.Data.EntityClient.EntityParameter> di <xref:System.Data.EntityClient.EntityCommand> e viene scorsa la raccolta di elementi `Contact`.</span><span class="sxs-lookup"><span data-stu-id="bae8f-110">It then creates an <xref:System.Data.EntityClient.EntityCommand>, adds two parameters to the <xref:System.Data.EntityClient.EntityParameter> collection of that <xref:System.Data.EntityClient.EntityCommand>, and iterates through the collection of `Contact` items.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="bae8f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bae8f-111">See also</span></span>

- [<span data-ttu-id="bae8f-112">Procedura: Eseguire una Query con parametri</span><span class="sxs-lookup"><span data-stu-id="bae8f-112">How to: Execute a Parameterized Query</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))
- [<span data-ttu-id="bae8f-113">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bae8f-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
