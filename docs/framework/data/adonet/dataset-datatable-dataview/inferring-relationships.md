---
title: Deduzione di relazioni
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: f8a9aba493dfe82466608ea60932ddfec5ef64f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127881"
---
# <a name="inferring-relationships"></a><span data-ttu-id="28431-102">Deduzione di relazioni</span><span class="sxs-lookup"><span data-stu-id="28431-102">Inferring Relationships</span></span>
<span data-ttu-id="28431-103">Se a un elemento inferito come tabella è associato un elemento figlio a sua volta inferito come tabella, tra le due tabelle verrà creato un tipo <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="28431-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="28431-104">Una nuova colonna con il nome **ParentTableName_Id** verranno aggiunti alla tabella creata per l'elemento padre sia la tabella creata per l'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="28431-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="28431-105">Il **ColumnMapping** della colonna identity verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="28431-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="28431-106">La colonna sarà una chiave primaria con incremento automatico per la tabella padre e verrà usata per il **DataRelation** tra le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="28431-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="28431-107">Il tipo di dati della colonna identity aggiunta sarà **System.Int32**, a differenza del tipo di dati di tutte le altre colonne inferite, ovvero **System. String**.</span><span class="sxs-lookup"><span data-stu-id="28431-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="28431-108">Oggetto <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** = **Cascade** verrà inoltre creato usando la nuova colonna nelle tabelle padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="28431-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="28431-109">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="28431-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="28431-110">Dal processo di inferenza verranno prodotte due tabelle: **Element1** e **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="28431-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="28431-111">Il **Element1** tabella sarà presenti due colonne: **Element1_Id** e **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="28431-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="28431-112">Il **ColumnMapping** proprietà delle **Element1_Id** colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="28431-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="28431-113">Il **ColumnMapping** proprietà delle **ChildElement2** colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="28431-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="28431-114">Il **Element1_Id** verrà impostata come chiave primaria della colonna la **Element1** tabella.</span><span class="sxs-lookup"><span data-stu-id="28431-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="28431-115">Il **ChildElement1** tabella sarà presenti tre colonne: **attr1**, **attr2** e **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="28431-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="28431-116">Il **ColumnMapping** proprietà per il **attr1** e **attr2** colonne verranno impostate su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="28431-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="28431-117">Il **ColumnMapping** proprietà delle **Element1_Id** colonna verrà impostata su **MappingType**.</span><span class="sxs-lookup"><span data-stu-id="28431-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="28431-118">Oggetto **DataRelation** e **ForeignKeyConstraint** verrà creato utilizzando il **Element1_Id** colonne di entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="28431-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="28431-119">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="28431-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="28431-120">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="28431-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="28431-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="28431-121">Element1_Id</span></span>|<span data-ttu-id="28431-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="28431-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="28431-123">0</span><span class="sxs-lookup"><span data-stu-id="28431-123">0</span></span>|<span data-ttu-id="28431-124">Text2</span><span class="sxs-lookup"><span data-stu-id="28431-124">Text2</span></span>|  
  
 <span data-ttu-id="28431-125">**tavolo:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="28431-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="28431-126">attr1</span><span class="sxs-lookup"><span data-stu-id="28431-126">attr1</span></span>|<span data-ttu-id="28431-127">attr2</span><span class="sxs-lookup"><span data-stu-id="28431-127">attr2</span></span>|<span data-ttu-id="28431-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="28431-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="28431-129">value1</span><span class="sxs-lookup"><span data-stu-id="28431-129">value1</span></span>|<span data-ttu-id="28431-130">value2</span><span class="sxs-lookup"><span data-stu-id="28431-130">value2</span></span>|<span data-ttu-id="28431-131">0</span><span class="sxs-lookup"><span data-stu-id="28431-131">0</span></span>|  
  
 <span data-ttu-id="28431-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="28431-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="28431-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="28431-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="28431-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="28431-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="28431-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="28431-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="28431-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="28431-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="28431-137">**Annidati:** True</span><span class="sxs-lookup"><span data-stu-id="28431-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="28431-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="28431-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="28431-139">**Colonna:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="28431-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="28431-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="28431-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="28431-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="28431-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="28431-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="28431-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="28431-143">**AcceptRejectRule:** nessuno</span><span class="sxs-lookup"><span data-stu-id="28431-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28431-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28431-144">See also</span></span>

- [<span data-ttu-id="28431-145">Deduzione della struttura relazionale di dataset da XML</span><span class="sxs-lookup"><span data-stu-id="28431-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="28431-146">Caricamento di un dataset da XML</span><span class="sxs-lookup"><span data-stu-id="28431-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="28431-147">Caricamento delle informazioni dello schema di dataset da XML</span><span class="sxs-lookup"><span data-stu-id="28431-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="28431-148">Annidamento di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="28431-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [<span data-ttu-id="28431-149">Utilizzo di XML in un dataset</span><span class="sxs-lookup"><span data-stu-id="28431-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="28431-150">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="28431-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="28431-151">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="28431-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
