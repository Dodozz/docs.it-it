---
title: tipo di entità
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3955de1873d80e85df713a557750e34e76efeb41
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502884"
---
# <a name="entity-type"></a><span data-ttu-id="de40a-102">tipo di entità</span><span class="sxs-lookup"><span data-stu-id="de40a-102">entity type</span></span>
<span data-ttu-id="de40a-103">Il *tipo di entità* è il blocco predefinito fondamentale per descrivere la struttura dei dati con Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="de40a-103">The *entity type* is the fundamental building block for describing the structure of data with the Entity Data Model (EDM).</span></span> <span data-ttu-id="de40a-104">In un modello concettuale, un tipo di entità rappresenta la struttura di concetti di livello superiore, quale ad esempio clienti o ordini.</span><span class="sxs-lookup"><span data-stu-id="de40a-104">In a conceptual model, an entity type represents the structure of top-level concepts, such as customers or orders.</span></span> <span data-ttu-id="de40a-105">Un tipo di entità è un modello per le istanze del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="de40a-105">An entity type is a template for entity type instances.</span></span> <span data-ttu-id="de40a-106">Ogni modello contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="de40a-106">Each template contains the following information:</span></span>  
  
-   <span data-ttu-id="de40a-107">Un nome univoco.</span><span class="sxs-lookup"><span data-stu-id="de40a-107">A unique name.</span></span> <span data-ttu-id="de40a-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="de40a-108">(Required.)</span></span>  
  
-   <span data-ttu-id="de40a-109">Un' [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md) definito da una o più proprietà.</span><span class="sxs-lookup"><span data-stu-id="de40a-109">An [entity key](../../../../docs/framework/data/adonet/entity-key.md) defined by one or more properties.</span></span> <span data-ttu-id="de40a-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="de40a-110">(Required.)</span></span>  
  
-   <span data-ttu-id="de40a-111">I dati nel formato [proprietà](../../../../docs/framework/data/adonet/property.md).</span><span class="sxs-lookup"><span data-stu-id="de40a-111">Data in the form of [properties](../../../../docs/framework/data/adonet/property.md).</span></span> <span data-ttu-id="de40a-112">(Facoltative)</span><span class="sxs-lookup"><span data-stu-id="de40a-112">(Optional.)</span></span>  
  
-   <span data-ttu-id="de40a-113">[Le proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md) che consentono di navigare da un' [finali](../../../../docs/framework/data/adonet/association-end.md) di un [associazione](../../../../docs/framework/data/adonet/association-type.md) su altra estremità.</span><span class="sxs-lookup"><span data-stu-id="de40a-113">[Navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) that allow for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="de40a-114">(facoltativo)</span><span class="sxs-lookup"><span data-stu-id="de40a-114">(Optional)</span></span>  
  
 <span data-ttu-id="de40a-115">In un'applicazione, un'istanza di un tipo di entità rappresenta un oggetto specifico, quale ad esempio un cliente o un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="de40a-115">In an application, an instance of an entity type represents a specific object (such as a specific customer or order).</span></span> <span data-ttu-id="de40a-116">Ogni istanza di un tipo di entità deve avere un valore univoco [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md) all'interno di un' [set di entità](../../../../docs/framework/data/adonet/entity-set.md).</span><span class="sxs-lookup"><span data-stu-id="de40a-116">Each instance of an entity type must have a unique [entity key](../../../../docs/framework/data/adonet/entity-key.md) within an [entity set](../../../../docs/framework/data/adonet/entity-set.md).</span></span>  
  
 <span data-ttu-id="de40a-117">Due istanze di tipi di entità sono considerate uguali solo se sono dello stesso tipo e se i valori delle rispettive chiavi di entità sono uguali.</span><span class="sxs-lookup"><span data-stu-id="de40a-117">Two entity type instances are considered equal only if they are of the same type and the values of their entity keys are the same.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de40a-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="de40a-118">Example</span></span>  
 <span data-ttu-id="de40a-119">Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`:</span><span class="sxs-lookup"><span data-stu-id="de40a-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`:</span></span>  
  
 <span data-ttu-id="de40a-120">![Modello di esempio](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="de40a-120">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="de40a-121">Si noti che le proprietà di ogni tipo di entità che costituiscono la chiave di entità vengono indicate con "(Key)".</span><span class="sxs-lookup"><span data-stu-id="de40a-121">Note that the properties of each entity type that make up its entity key are denoted with "(Key)".</span></span>  
  
 <span data-ttu-id="de40a-122">Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali.</span><span class="sxs-lookup"><span data-stu-id="de40a-122">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="de40a-123">Il linguaggio CSDL seguente definisce il tipo di entità `Book` illustrato nel diagramma precedente:</span><span class="sxs-lookup"><span data-stu-id="de40a-123">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a><span data-ttu-id="de40a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de40a-124">See also</span></span>
- [<span data-ttu-id="de40a-125">Concetti chiave di Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="de40a-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="de40a-126">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="de40a-126">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
- [<span data-ttu-id="de40a-127">facet</span><span class="sxs-lookup"><span data-stu-id="de40a-127">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)
