---
title: 'Procedura: Rappresentare tabelle come classi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 49e7d6768d8739bba94c9e8d38bcc582c8bd6e4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902902"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="ad22f-102">Procedura: Rappresentare tabelle come classi</span><span class="sxs-lookup"><span data-stu-id="ad22f-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="ad22f-103">Usare la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attributo per definire una classe come classe di entità associata a una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="ad22f-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="ad22f-104">Per eseguire il mapping di una classe a una tabella di database</span><span class="sxs-lookup"><span data-stu-id="ad22f-104">To map a class to a database table</span></span>  
  
-   <span data-ttu-id="ad22f-105">Aggiungere l'attributo <xref:System.Data.Linq.Mapping.TableAttribute> alla dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="ad22f-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad22f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad22f-106">Example</span></span>  
 <span data-ttu-id="ad22f-107">Nel codice seguente la classe `Customer` viene definita come una classe di entità associata alla tabella di database `Customers`.</span><span class="sxs-lookup"><span data-stu-id="ad22f-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="ad22f-108">Non è necessario specificare la proprietà <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> se il nome può essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="ad22f-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="ad22f-109">Se non si specifica un nome, verrà usato lo stesso nome della proprietà o del campo.</span><span class="sxs-lookup"><span data-stu-id="ad22f-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad22f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad22f-110">See also</span></span>

- [<span data-ttu-id="ad22f-111">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ad22f-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="ad22f-112">Procedura: Personalizzare le classi di entità usando l'Editor di codice</span><span class="sxs-lookup"><span data-stu-id="ad22f-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
