---
title: Deduzione del testo dell'elemento
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 6ffe8f2fbf01fbe8dfa9d78f3dfb9e39b6e80b16
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224962"
---
# <a name="inferring-element-text"></a><span data-ttu-id="2853d-102">Deduzione del testo dell'elemento</span><span class="sxs-lookup"><span data-stu-id="2853d-102">Inferring Element Text</span></span>
<span data-ttu-id="2853d-103">Se un elemento contiene testo e non contiene elementi figlio da inferire come tabelle, ad esempio (elementi con attributi) o elementi ripetuti, una nuova colonna con il nome **TableName_Text** verranno aggiunti alla tabella inferita per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="2853d-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="2853d-104">Il testo contenuto nell'elemento viene aggiunto a una riga della tabella e archiviato nella nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="2853d-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="2853d-105">Il **ColumnMapping** della nuova colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="2853d-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="2853d-106">Ad esempio, si consideri il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="2853d-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2853d-107">Il processo di inferenza genererà una tabella denominata **Element1** con due colonne: **attr1** e **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="2853d-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="2853d-108">Il **ColumnMapping** proprietà delle **attr1** colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="2853d-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="2853d-109">Il **ColumnMapping** proprietà delle **Element1_Text** colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="2853d-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="2853d-110">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2853d-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2853d-111">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="2853d-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2853d-112">attr1</span><span class="sxs-lookup"><span data-stu-id="2853d-112">attr1</span></span>|<span data-ttu-id="2853d-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="2853d-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="2853d-114">value1</span><span class="sxs-lookup"><span data-stu-id="2853d-114">value1</span></span>|<span data-ttu-id="2853d-115">Text1</span><span class="sxs-lookup"><span data-stu-id="2853d-115">Text1</span></span>|  
  
 <span data-ttu-id="2853d-116">Se in un elemento è presente del testo ma a tale elemento sono associati anche elementi figlio contenenti testo, alla tabella non verrà aggiunta alcuna colonna in cui archiviare il testo contenuto nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="2853d-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="2853d-117">Il testo contenuto nell'elemento verrà ignorato e il testo degli elementi figlio viene incluso in una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="2853d-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="2853d-118">Ad esempio, si consideri il seguente codice XML.</span><span class="sxs-lookup"><span data-stu-id="2853d-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="2853d-119">Il processo di inferenza genererà una tabella denominata **Element1** con una sola colonna denominata **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="2853d-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="2853d-120">Il testo per il **ChildElement1** elemento verrà incluso in una riga nella tabella.</span><span class="sxs-lookup"><span data-stu-id="2853d-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="2853d-121">Il testo rimanente verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="2853d-121">The other text will be ignored.</span></span> <span data-ttu-id="2853d-122">Il **ColumnMapping** proprietà delle **ChildElement1** colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="2853d-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="2853d-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2853d-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2853d-124">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="2853d-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2853d-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="2853d-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="2853d-126">Text2</span><span class="sxs-lookup"><span data-stu-id="2853d-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2853d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2853d-127">See also</span></span>

- [<span data-ttu-id="2853d-128">Deduzione della struttura relazionale di DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="2853d-128">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="2853d-129">Caricamento di un oggetto DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="2853d-129">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="2853d-130">Caricamento delle informazioni dello schema DataSet da XML</span><span class="sxs-lookup"><span data-stu-id="2853d-130">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="2853d-131">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="2853d-131">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="2853d-132">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="2853d-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="2853d-133">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="2853d-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
