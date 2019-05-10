---
title: Espressioni di inizializzazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
ms.openlocfilehash: 78bafcad0a0f34c74ea58f107621ad145c1b405b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631538"
---
# <a name="initialization-expressions"></a><span data-ttu-id="74398-102">Espressioni di inizializzazione</span><span class="sxs-lookup"><span data-stu-id="74398-102">Initialization Expressions</span></span>
<span data-ttu-id="74398-103">Un'espressione di inizializzazione consente di inizializzare un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="74398-103">An initialization expression initializes a new object.</span></span> <span data-ttu-id="74398-104">La maggior parte delle espressioni di inizializzazione è supportata, incluse le più recenti espressioni di inizializzazione di C# 3.0 e Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="74398-104">Most initialization expressions are supported, including most new C# 3.0 and Visual Basic 9.0 initialization expressions.</span></span> <span data-ttu-id="74398-105">I tipi seguenti possono essere inizializzati e restituiti da una query LINQ to Entities:</span><span class="sxs-lookup"><span data-stu-id="74398-105">The following types can be initialized and returned by a LINQ to Entities query:</span></span>  
  
- <span data-ttu-id="74398-106">Raccolta di zero o più oggetti entità tipizzate o proiezione di tipi complessi definiti nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="74398-106">A collection of zero or more typed entity objects or a projection of complex types that are defined in the conceptual model.</span></span>  
  
- <span data-ttu-id="74398-107">Tipi CLR supportati da [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74398-107">CLR types supported by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  
  
- <span data-ttu-id="74398-108">Raccolte inline.</span><span class="sxs-lookup"><span data-stu-id="74398-108">Inline collections.</span></span>  
  
- <span data-ttu-id="74398-109">Tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="74398-109">Anonymous types.</span></span>  
  
 <span data-ttu-id="74398-110">L'inizializzazione dei tipi anonimi è illustrata nell'esempio seguente nella sintassi delle espressioni di query:</span><span class="sxs-lookup"><span data-stu-id="74398-110">Anonymous type initialization is shown in the following example in query expression syntax:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 <span data-ttu-id="74398-111">Nell'esempio seguente nella sintassi delle query basate su metodo viene illustrata l'inizializzazione di un tipo anonimo:</span><span class="sxs-lookup"><span data-stu-id="74398-111">The following example in method-based query syntax shows anonymous type initialization:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 <span data-ttu-id="74398-112">È inoltre supportata l'inizializzazione delle classi definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="74398-112">User-defined class initialization is also supported.</span></span> <span data-ttu-id="74398-113">Il modello di inizializzazione di C# 3.0 e Visual Basic 9.0 è supportato e presuppone che i metodi Get e Set della proprietà siano simmetrici.</span><span class="sxs-lookup"><span data-stu-id="74398-113">The C# 3.0 and Visual Basic 9.0 initialization pattern is supported and assumes that the property getter and setter are symmetric.</span></span> <span data-ttu-id="74398-114">Nell'esempio seguente nella sintassi delle espressioni di query viene illustrata l'inizializzazione di una classe personalizzata nella query:</span><span class="sxs-lookup"><span data-stu-id="74398-114">The following example in query expression syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 <span data-ttu-id="74398-115">Nell'esempio seguente nella sintassi delle query basate su metodo viene illustrata l'inizializzazione di una classe personalizzata nella query:</span><span class="sxs-lookup"><span data-stu-id="74398-115">The following example in method-based query syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="74398-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74398-116">See also</span></span>

- [<span data-ttu-id="74398-117">Espressioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="74398-117">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
