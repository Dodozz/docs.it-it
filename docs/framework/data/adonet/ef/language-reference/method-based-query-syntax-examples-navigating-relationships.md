---
title: 'Esempi di sintassi di Query basate sul metodo: Navigazione tra relazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
ms.openlocfilehash: 450fa284254c9a78a287c922424f0deaafd7534f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692246"
---
# <a name="method-based-query-syntax-examples-navigating-relationships"></a><span data-ttu-id="12a43-102">Esempi di sintassi di Query basate sul metodo: Navigazione tra relazioni</span><span class="sxs-lookup"><span data-stu-id="12a43-102">Method-Based Query Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="12a43-103">Le proprietà di navigazione in [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sono proprietà di collegamento usate per individuare le entità finali di un'associazione.</span><span class="sxs-lookup"><span data-stu-id="12a43-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="12a43-104">Le proprietà di navigazione consentono a un utente di spostarsi da un'entità a un'altra o da un entità alle entità correlate tramite un set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="12a43-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="12a43-105">In questo argomento sono inclusi alcuni esempi nella sintassi delle query basate su metodo in cui viene illustrato come spostarsi tra relazioni tramite proprietà di navigazione in query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12a43-105">This topic provides examples in method-based query syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="12a43-106">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="12a43-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="12a43-107">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="12a43-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="12a43-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="12a43-108">Example</span></span>  
 <span data-ttu-id="12a43-109">Nell'esempio seguente nella sintassi delle query basate su metodi viene usato il metodo <xref:System.Linq.Queryable.SelectMany%2A> per ottenere tutti gli ordini dei contatti il cui cognome è "Zhou".</span><span class="sxs-lookup"><span data-stu-id="12a43-109">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.SelectMany%2A> method to get all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="12a43-110">La proprietà di navigazione `Contact.SalesOrderHeader` viene usata per ottenere la raccolta di oggetti `SalesOrderHeader` per ciascun contatto.</span><span class="sxs-lookup"><span data-stu-id="12a43-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## <a name="example"></a><span data-ttu-id="12a43-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="12a43-111">Example</span></span>  
 <span data-ttu-id="12a43-112">Nell'esempio seguente nella sintassi delle query basate su metodo viene usato il metodo <xref:System.Linq.Queryable.Select%2A> per ottenere tutti gli ID contatto e la somma del totale dovuto per ogni contatto il cui cognome è "Zhou".</span><span class="sxs-lookup"><span data-stu-id="12a43-112">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="12a43-113">La proprietà di navigazione `Contact.SalesOrderHeader` viene usata per ottenere la raccolta di oggetti `SalesOrderHeader` per ciascun contatto.</span><span class="sxs-lookup"><span data-stu-id="12a43-113">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="12a43-114">Il metodo `Sum` usa la proprietà di navigazione `Contact.SalesOrderHeader` per sommare il totale dovuto per tutti gli ordini per ciascun contatto.</span><span class="sxs-lookup"><span data-stu-id="12a43-114">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## <a name="example"></a><span data-ttu-id="12a43-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="12a43-115">Example</span></span>  
 <span data-ttu-id="12a43-116">Nell'esempio seguente nella sintassi delle query basate su metodo vengono recuperati tutti gli ordini dei contatti il cui cognome è "Zhou."</span><span class="sxs-lookup"><span data-stu-id="12a43-116">The following example in method-based query syntax gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="12a43-117">La proprietà di navigazione `Contact.SalesOrderHeader` viene usata per ottenere la raccolta di oggetti `SalesOrderHeader` per ciascun contatto.</span><span class="sxs-lookup"><span data-stu-id="12a43-117">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="12a43-118">Il nome e gli ordini del contatto vengono restituiti in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="12a43-118">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## <a name="example"></a><span data-ttu-id="12a43-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="12a43-119">Example</span></span>  
 <span data-ttu-id="12a43-120">Nell'esempio seguente vengono usate le proprietà di navigazione `SalesOrderHeader.Address` e `SalesOrderHeader.Contact` per ottenere la raccolta di oggetti `Address` e `Contact` associati a ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="12a43-120">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties to get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="12a43-121">Il cognome del contatto, l'indirizzo, il numero dell'ordine di vendita e il totale dovuto per ogni ordine alla città di Seattle vengono restituiti in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="12a43-121">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## <a name="example"></a><span data-ttu-id="12a43-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="12a43-122">Example</span></span>  
 <span data-ttu-id="12a43-123">Nell'esempio seguente viene usato il metodo `Where` per individuare gli ordini effettuati dopo l'1 dicembre 2003, quindi viene usata la proprietà di navigazione `order.SalesOrderDetail` per ottenere i dettagli relativi a ogni ordine.</span><span class="sxs-lookup"><span data-stu-id="12a43-123">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="12a43-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12a43-124">See also</span></span>
- [<span data-ttu-id="12a43-125">Proprietà di navigazione</span><span class="sxs-lookup"><span data-stu-id="12a43-125">Navigation Properties</span></span>](https://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)
- [<span data-ttu-id="12a43-126">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="12a43-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
