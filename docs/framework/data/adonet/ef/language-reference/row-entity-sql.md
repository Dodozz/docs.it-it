---
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: 9515d972addc3dd10a27ffbe7776f77d097a30d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074261"
---
# <a name="row-entity-sql"></a><span data-ttu-id="ed4d4-102">ROW (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ed4d4-102">ROW (Entity SQL)</span></span>
<span data-ttu-id="ed4d4-103">Consente di costruire record anonimi strutturalmente tipizzati da uno o più valori.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-103">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed4d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed4d4-104">Syntax</span></span>  
  
```  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="ed4d4-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ed4d4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ed4d4-106">Qualsiasi espressione di query valida che restituisce un valore da costruire in un tipo di riga.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-106">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="ed4d4-107">Specifica un alias per il valore specificato in un tipo di riga.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-107">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="ed4d4-108">Se non viene fornito un alias, in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene eseguito un tentativo di generare un alias usando le regole di generazione di alias [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed4d4-108">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed4d4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ed4d4-109">Return Value</span></span>  
 <span data-ttu-id="ed4d4-110">Tipo di riga.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-110">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed4d4-111">Note</span><span class="sxs-lookup"><span data-stu-id="ed4d4-111">Remarks</span></span>  
 <span data-ttu-id="ed4d4-112">Si usano costruttori ROW in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per costruire record anonimi strutturalmente tipizzati da uno o più valori.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-112">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="ed4d4-113">Il tipo di risultato di un costruttore ROW è un tipo di riga i cui tipi di campo corrispondono ai tipi dei valori usati per costruire la riga.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-113">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="ed4d4-114">L'espressione seguente consente ad esempio di costruire un valore di tipo `Record(a int, b string, c int)`.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-114">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="ed4d4-115">Se non si fornisce un alias per un'espressione in un costruttore di riga, in Entity Framework viene eseguito un tentativo di generarne uno.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-115">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="ed4d4-116">Per altre informazioni, vedere la sezione "Regole relative all'utilizzo degli alias" dell'argomento [Identificatori](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="ed4d4-116">For more information, see the "Aliasing Rules" section of the [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="ed4d4-117">Le regole seguenti riguardano l'uso di alias nelle espressioni in un costruttore di riga:</span><span class="sxs-lookup"><span data-stu-id="ed4d4-117">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
-   <span data-ttu-id="ed4d4-118">Le espressioni in un costruttore ROW non possono fare riferimento ad altri alias nello stesso costruttore.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-118">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
-   <span data-ttu-id="ed4d4-119">Due espressioni nello stesso costruttore di riga non possono avere lo stesso alias.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-119">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="ed4d4-120">Per altre informazioni sui costruttori di query, vedere [tipi di costruzione](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ed4d4-120">For more information about query constructors, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed4d4-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed4d4-121">Example</span></span>  
 <span data-ttu-id="ed4d4-122">Nella query Entity SQL seguente viene usato l'operatore ROW per costruire record anonimi strutturalmente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-122">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="ed4d4-123">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ed4d4-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ed4d4-124">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ed4d4-124">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ed4d4-125">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ed4d4-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ed4d4-126">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ed4d4-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ROW](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#row)]  
  
## <a name="see-also"></a><span data-ttu-id="ed4d4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed4d4-127">See also</span></span>

- [<span data-ttu-id="ed4d4-128">Costruzione di tipi</span><span class="sxs-lookup"><span data-stu-id="ed4d4-128">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [<span data-ttu-id="ed4d4-129">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ed4d4-129">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="ed4d4-130">Definizioni dei tipi</span><span class="sxs-lookup"><span data-stu-id="ed4d4-130">Type Definitions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
