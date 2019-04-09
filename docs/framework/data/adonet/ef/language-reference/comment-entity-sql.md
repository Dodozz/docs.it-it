---
title: -- (commento) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 40a0ee8f6bc2cf8fae5779ecb3d103c77dde161b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137176"
---
# <a name="---comment-entity-sql"></a><span data-ttu-id="180c2-102">-- (commento) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="180c2-102">-- (Comment) (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="180c2-103">le query possono contenere commenti.</span><span class="sxs-lookup"><span data-stu-id="180c2-103">queries can contain comments.</span></span> <span data-ttu-id="180c2-104">Due trattini (`--`) indicano l'inizio di una riga di commento.</span><span class="sxs-lookup"><span data-stu-id="180c2-104">Two dashes (`--`) start a comment line.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="180c2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="180c2-105">Syntax</span></span>  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a><span data-ttu-id="180c2-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="180c2-106">Arguments</span></span>  
 `text_of_comment`  
 <span data-ttu-id="180c2-107">Stringa di caratteri contenente il testo del commento.</span><span class="sxs-lookup"><span data-stu-id="180c2-107">Is the character string that contains the text of the comment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="180c2-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="180c2-108">Example</span></span>  
 <span data-ttu-id="180c2-109">Nella query Entity SQL seguente viene illustrato come usare i commenti.</span><span class="sxs-lookup"><span data-stu-id="180c2-109">The following Entity SQL query demonstrates how to use comments.</span></span> <span data-ttu-id="180c2-110">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="180c2-110">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="180c2-111">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="180c2-111">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="180c2-112">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="180c2-112">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="180c2-113">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="180c2-113">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a><span data-ttu-id="180c2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="180c2-114">See also</span></span>

- [<span data-ttu-id="180c2-115">Cenni preliminari su Entity SQL</span><span class="sxs-lookup"><span data-stu-id="180c2-115">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [<span data-ttu-id="180c2-116">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="180c2-116">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
