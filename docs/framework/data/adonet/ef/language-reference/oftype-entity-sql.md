---
title: OFTYPE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: bbc3ffd4902fe8c1c41aebe88317d0e3c32f7771
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760363"
---
# <a name="oftype-entity-sql"></a><span data-ttu-id="8554a-102">OFTYPE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8554a-102">OFTYPE (Entity SQL)</span></span>
<span data-ttu-id="8554a-103">Restituisce una raccolta di oggetti da un'espressione di query appartenente a un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="8554a-103">Returns a collection of objects from a query expression that is of a specific type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8554a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8554a-104">Syntax</span></span>  
  
```  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="8554a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8554a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8554a-106">Qualsiasi espressione di query valida che restituisca una raccolta di oggetti.</span><span class="sxs-lookup"><span data-stu-id="8554a-106">Any valid query expression that returns a collection of objects.</span></span>  
  
 `test_type`  
 <span data-ttu-id="8554a-107">Il tipo rispetto al quale testare ogni oggetto restituito da `expression` .</span><span class="sxs-lookup"><span data-stu-id="8554a-107">The type to test each object returned by `expression` against.</span></span> <span data-ttu-id="8554a-108">Il tipo deve essere qualificato da uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8554a-108">The type must be qualified by a namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8554a-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8554a-109">Return Value</span></span>  
 <span data-ttu-id="8554a-110">Raccolta di oggetti appartenenti al tipo `test_type`o un tipo di base o un tipo derivato di `test_type`.</span><span class="sxs-lookup"><span data-stu-id="8554a-110">A collection of objects that are of type `test_type`, or a base type or derived type of `test_type`.</span></span> <span data-ttu-id="8554a-111">Se si specifica ONLY, verranno restituite solo le istanze di `test_type` o una raccolta vuota.</span><span class="sxs-lookup"><span data-stu-id="8554a-111">If ONLY is specified, only instances of the `test_type` or an empty collection will be returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8554a-112">Note</span><span class="sxs-lookup"><span data-stu-id="8554a-112">Remarks</span></span>  
 <span data-ttu-id="8554a-113">Un'espressione `OFTYPE` specifica un'espressione del tipo usata per eseguire un test del tipo rispetto a ogni elemento di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="8554a-113">An `OFTYPE` expression specifies a type expression that is issued to perform a type test against each element of a collection.</span></span>  <span data-ttu-id="8554a-114">L'espressione `OFTYPE` produce una nuova raccolta del tipo specificato, contenente solo gli elementi equivalenti o al tipo o al relativo sottotipo.</span><span class="sxs-lookup"><span data-stu-id="8554a-114">The `OFTYPE` expression produces a new collection of the specified type containing only those elements that were either equivalent to that type or a sub-type of it.</span></span>  
  
 <span data-ttu-id="8554a-115">Un'espressione `OFTYPE` è un'abbreviazione dell'espressione di query seguente:</span><span class="sxs-lookup"><span data-stu-id="8554a-115">An `OFTYPE` expression is an abbreviation of the following query expression:</span></span>  
  
```  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 <span data-ttu-id="8554a-116">Dal momento che Manager è un sottotipo di Employee, l'espressione seguente produce una raccolta dei soli manager da una raccolta di dipendenti:</span><span class="sxs-lookup"><span data-stu-id="8554a-116">Given that a Manager is a subtype of Employee, the following expression produces a collection of only managers from a collection of employees:</span></span>  
  
```  
OfType(employees, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="8554a-117">È inoltre possibile eseguire l'upcast di una raccolta usando il filtro del tipo:</span><span class="sxs-lookup"><span data-stu-id="8554a-117">It is also possible to up cast a collection using the type filter:</span></span>  
  
```  
OfType(executives, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="8554a-118">Poiché tutti i dirigenti sono manager, la raccolta risultante contiene ancora tutti i dirigenti d'azienda originali, sebbene la raccolta sia ora indicata come una raccolta di manager.</span><span class="sxs-lookup"><span data-stu-id="8554a-118">Since all executives are managers, the resulting collection still contains all the original executives, though the collection is now typed as a collection of managers.</span></span>  
  
 <span data-ttu-id="8554a-119">Nella tabella seguente viene illustrato il comportamento dell'operatore `OFTYPE` con alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="8554a-119">The following table shows the behavior of the `OFTYPE` operator over some patterns.</span></span> <span data-ttu-id="8554a-120">Tutte le eccezioni vengono generate sul lato client prima che il provider venga richiamato:</span><span class="sxs-lookup"><span data-stu-id="8554a-120">All exceptions are thrown from the client side before the provider is invoked:</span></span>  
  
|<span data-ttu-id="8554a-121">Modello</span><span class="sxs-lookup"><span data-stu-id="8554a-121">Pattern</span></span>|<span data-ttu-id="8554a-122">Comportamento</span><span class="sxs-lookup"><span data-stu-id="8554a-122">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="8554a-123">OFTYPE(Collection(EntityType), EntityType)</span><span class="sxs-lookup"><span data-stu-id="8554a-123">OFTYPE(Collection(EntityType), EntityType)</span></span>|<span data-ttu-id="8554a-124">Collection(EntityType)</span><span class="sxs-lookup"><span data-stu-id="8554a-124">Collection(EntityType)</span></span>|  
|<span data-ttu-id="8554a-125">OFTYPE(Collection(ComplexType), ComplexType)</span><span class="sxs-lookup"><span data-stu-id="8554a-125">OFTYPE(Collection(ComplexType), ComplexType)</span></span>|<span data-ttu-id="8554a-126">Genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="8554a-126">Throws</span></span>|  
|<span data-ttu-id="8554a-127">OFTYPE(Collection(RowType), RowType)</span><span class="sxs-lookup"><span data-stu-id="8554a-127">OFTYPE(Collection(RowType), RowType)</span></span>|<span data-ttu-id="8554a-128">Genera un'eccezione</span><span class="sxs-lookup"><span data-stu-id="8554a-128">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8554a-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="8554a-129">Example</span></span>  
 <span data-ttu-id="8554a-130">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore OFTYPE per restituire una raccolta di oggetti OnsiteCourse da una raccolta di oggetti Course.</span><span class="sxs-lookup"><span data-stu-id="8554a-130">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the OFTYPE operator to return a collection of OnsiteCourse objects from a collection of Course objects.</span></span> <span data-ttu-id="8554a-131">La query è basata sul [modello School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8554a-131">The query is based on the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OFTYPE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#oftype)]  
  
## <a name="see-also"></a><span data-ttu-id="8554a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8554a-132">See also</span></span>

- [<span data-ttu-id="8554a-133">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8554a-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
