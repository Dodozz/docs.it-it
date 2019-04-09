---
title: Deduzione di tabelle
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 2c2a93d413f301dc3006b701e4bc7979a3fa7a1d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181831"
---
# <a name="inferring-tables"></a><span data-ttu-id="cf771-102">Deduzione di tabelle</span><span class="sxs-lookup"><span data-stu-id="cf771-102">Inferring Tables</span></span>
<span data-ttu-id="cf771-103">Durante l'inferenza di uno schema per un tipo <xref:System.Data.DataSet> da un documento XML, ADO.NET determina innanzitutto quali elementi XML rappresentano tabelle.</span><span class="sxs-lookup"><span data-stu-id="cf771-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="cf771-104">Le strutture XML seguente come risultato una tabella per la **set di dati** dello schema:</span><span class="sxs-lookup"><span data-stu-id="cf771-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="cf771-105">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="cf771-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="cf771-106">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cf771-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="cf771-107">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="cf771-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="cf771-108">Elementi con attributi</span><span class="sxs-lookup"><span data-stu-id="cf771-108">Elements with Attributes</span></span>  
 <span data-ttu-id="cf771-109">Gli elementi in cui sono stati specificati degli attributi daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="cf771-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="cf771-110">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="cf771-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="cf771-111">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="cf771-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="cf771-112">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="cf771-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="cf771-113">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="cf771-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="cf771-114">attr1</span><span class="sxs-lookup"><span data-stu-id="cf771-114">attr1</span></span>|<span data-ttu-id="cf771-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="cf771-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="cf771-116">value1</span><span class="sxs-lookup"><span data-stu-id="cf771-116">value1</span></span>||  
|<span data-ttu-id="cf771-117">value2</span><span class="sxs-lookup"><span data-stu-id="cf771-117">value2</span></span>|<span data-ttu-id="cf771-118">Text1</span><span class="sxs-lookup"><span data-stu-id="cf771-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="cf771-119">Elementi con elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cf771-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="cf771-120">Gli elementi a cui sono associati elementi figlio daranno come risultato delle tabelle inferite.</span><span class="sxs-lookup"><span data-stu-id="cf771-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="cf771-121">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="cf771-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="cf771-122">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="cf771-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="cf771-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="cf771-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="cf771-124">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="cf771-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="cf771-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="cf771-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="cf771-126">Text1</span><span class="sxs-lookup"><span data-stu-id="cf771-126">Text1</span></span>|  
  
 <span data-ttu-id="cf771-127">L'elemento del documento, o elemento radice, dà come risultato una tabella inferita nel caso in cui a tale elemento siano associati attributi o elementi figlio che vengono inferiti come colonne.</span><span class="sxs-lookup"><span data-stu-id="cf771-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="cf771-128">Se l'elemento documento presenta alcun attributo e nessun elemento figlio da inferire come colonne, l'elemento viene inferito come un **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="cf771-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="cf771-129">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="cf771-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="cf771-130">Il processo di inferenza produce una tabella denominata "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="cf771-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="cf771-131">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="cf771-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="cf771-132">**tavolo:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="cf771-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="cf771-133">Element1</span><span class="sxs-lookup"><span data-stu-id="cf771-133">Element1</span></span>|<span data-ttu-id="cf771-134">Element2</span><span class="sxs-lookup"><span data-stu-id="cf771-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="cf771-135">Text1</span><span class="sxs-lookup"><span data-stu-id="cf771-135">Text1</span></span>|<span data-ttu-id="cf771-136">Text2</span><span class="sxs-lookup"><span data-stu-id="cf771-136">Text2</span></span>|  
  
 <span data-ttu-id="cf771-137">Si consideri in alternativa il seguente elemento XML:</span><span class="sxs-lookup"><span data-stu-id="cf771-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="cf771-138">Il processo di inferenza produce una **set di dati** denominata "DocumentElement" contenente una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="cf771-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="cf771-139">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="cf771-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="cf771-140">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="cf771-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="cf771-141">attr1</span><span class="sxs-lookup"><span data-stu-id="cf771-141">attr1</span></span>|<span data-ttu-id="cf771-142">attr2</span><span class="sxs-lookup"><span data-stu-id="cf771-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="cf771-143">value1</span><span class="sxs-lookup"><span data-stu-id="cf771-143">value1</span></span>|<span data-ttu-id="cf771-144">value2</span><span class="sxs-lookup"><span data-stu-id="cf771-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="cf771-145">Elementi ripetuti</span><span class="sxs-lookup"><span data-stu-id="cf771-145">Repeating Elements</span></span>  
 <span data-ttu-id="cf771-146">Gli elementi ripetuti danno come risultato una singola tabella inferita.</span><span class="sxs-lookup"><span data-stu-id="cf771-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="cf771-147">Ad esempio, si consideri il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="cf771-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="cf771-148">Il processo di inferenza produce una tabella denominata "Element1".</span><span class="sxs-lookup"><span data-stu-id="cf771-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="cf771-149">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="cf771-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="cf771-150">**tavolo:** Element1</span><span class="sxs-lookup"><span data-stu-id="cf771-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="cf771-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="cf771-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="cf771-152">Text1</span><span class="sxs-lookup"><span data-stu-id="cf771-152">Text1</span></span>|  
|<span data-ttu-id="cf771-153">Text2</span><span class="sxs-lookup"><span data-stu-id="cf771-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf771-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf771-154">See also</span></span>

- [<span data-ttu-id="cf771-155">Deduzione della struttura relazionale di dataset da XML</span><span class="sxs-lookup"><span data-stu-id="cf771-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="cf771-156">Caricamento di un dataset da XML</span><span class="sxs-lookup"><span data-stu-id="cf771-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="cf771-157">Caricamento delle informazioni dello schema di dataset da XML</span><span class="sxs-lookup"><span data-stu-id="cf771-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="cf771-158">Utilizzo di XML in un dataset</span><span class="sxs-lookup"><span data-stu-id="cf771-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="cf771-159">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="cf771-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="cf771-160">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="cf771-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
