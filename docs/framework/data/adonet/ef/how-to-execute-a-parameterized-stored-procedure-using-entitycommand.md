---
title: 'Procedura: Eseguire una Stored Procedure con parametri tramite EntityCommand'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: 11894decbb81192eb68c680149bbe9f7398f0203
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587811"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="6f21e-102">Procedura: Eseguire una Stored Procedure con parametri tramite EntityCommand</span><span class="sxs-lookup"><span data-stu-id="6f21e-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="6f21e-103">In questo argomento viene mostrato come eseguire una stored procedure con parametri usando la classe <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="6f21e-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="6f21e-104">Per eseguire il codice in questo esempio</span><span class="sxs-lookup"><span data-stu-id="6f21e-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="6f21e-105">Aggiungere il [modello School](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) al progetto e configurare il progetto per usare il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f21e-105">Add the [School Model](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="6f21e-106">Per altre informazioni, vedere [Procedura: Usare la procedura guidata Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="6f21e-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="6f21e-107">Nella tabella codici per l'applicazione aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="6f21e-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="6f21e-108">Importare la stored procedure `GetStudentGrades` e specificare entità `CourseGrade` come tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="6f21e-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="6f21e-109">Per informazioni su come importare una stored procedure, vedere [come: Importare una Stored Procedure](https://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span><span class="sxs-lookup"><span data-stu-id="6f21e-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](https://msdn.microsoft.com/library/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f21e-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="6f21e-110">Example</span></span>  
 <span data-ttu-id="6f21e-111">Nel codice seguente viene eseguita la stored procedure `GetStudentGrades`, dove `StudentId` è un parametro obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6f21e-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="6f21e-112">I risultati vengono quindi letti da <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="6f21e-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="6f21e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f21e-113">See also</span></span>
- [<span data-ttu-id="6f21e-114">Provider EntityClient per Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6f21e-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
