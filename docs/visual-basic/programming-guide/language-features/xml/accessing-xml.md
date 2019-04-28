---
title: Accesso a XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 0540c52cf3e4cd7594f051c10832ea99cf58a34e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756962"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="5c076-102">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c076-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="5c076-103">Visual Basic fornisce le proprietà axis XML per l'accesso e la navigazione [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] strutture.</span><span class="sxs-lookup"><span data-stu-id="5c076-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="5c076-104">Queste proprietà utilizzano una sintassi speciale per poter accedere agli elementi e attributi specificando i nomi XML.</span><span class="sxs-lookup"><span data-stu-id="5c076-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="5c076-105">La tabella seguente elenca le funzionalità del linguaggio che consentono di accedere agli elementi XML e attributi in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5c076-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="5c076-106">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="5c076-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="5c076-107">Descrizione della proprietà</span><span class="sxs-lookup"><span data-stu-id="5c076-107">Property description</span></span>|<span data-ttu-id="5c076-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c076-108">Example</span></span>|<span data-ttu-id="5c076-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c076-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="5c076-110">*asse child*</span><span class="sxs-lookup"><span data-stu-id="5c076-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="5c076-111">Ottiene tutti i `phone` gli elementi che sono elementi figlio del `contact` elemento.</span><span class="sxs-lookup"><span data-stu-id="5c076-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="5c076-112">*asse attribute*</span><span class="sxs-lookup"><span data-stu-id="5c076-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="5c076-113">Ottiene tutti i `type` attributi del `phone` elemento.</span><span class="sxs-lookup"><span data-stu-id="5c076-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="5c076-114">*asse descendant*</span><span class="sxs-lookup"><span data-stu-id="5c076-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="5c076-115">Ottiene tutti i `name` elementi del `contacts` elemento, indipendentemente dal livello di profondità della gerarchia che si verifichino.</span><span class="sxs-lookup"><span data-stu-id="5c076-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="5c076-116">*extension indexer*</span><span class="sxs-lookup"><span data-stu-id="5c076-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="5c076-117">Ottiene il primo `name` elemento dalla sequenza.</span><span class="sxs-lookup"><span data-stu-id="5c076-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="5c076-118">*value*</span><span class="sxs-lookup"><span data-stu-id="5c076-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="5c076-119">Ottiene la rappresentazione di stringa del primo oggetto nella sequenza, o `Nothing` se la sequenza è vuota.</span><span class="sxs-lookup"><span data-stu-id="5c076-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="5c076-120">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5c076-120">In This Section</span></span>  
 [<span data-ttu-id="5c076-121">Procedura: Elementi discendenti XML di accesso</span><span class="sxs-lookup"><span data-stu-id="5c076-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="5c076-122">Viene illustrato come usare una proprietà axis discendente per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML specificato.</span><span class="sxs-lookup"><span data-stu-id="5c076-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="5c076-123">Procedura: Accedere agli elementi figlio XML</span><span class="sxs-lookup"><span data-stu-id="5c076-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="5c076-124">Viene illustrato come utilizzare un elemento figlio di proprietà dell'asse per accedere a tutti gli elementi figlio XML con un nome specificato in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="5c076-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="5c076-125">Procedura: Attributi XML di accesso</span><span class="sxs-lookup"><span data-stu-id="5c076-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="5c076-126">Viene illustrato come usare una proprietà axis dell'attributo per accedere a tutti gli attributi XML che hanno un nome specificato in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="5c076-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="5c076-127">Procedura: Dichiarare e usare prefissi XML Namespace</span><span class="sxs-lookup"><span data-stu-id="5c076-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="5c076-128">Viene illustrato come dichiarare un prefisso dello spazio dei nomi XML e usarlo per creare e accedere agli elementi XML.</span><span class="sxs-lookup"><span data-stu-id="5c076-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5c076-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5c076-129">Related Sections</span></span>  
 [<span data-ttu-id="5c076-130">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="5c076-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="5c076-131">Vengono forniti collegamenti alle sezioni che descrivono le varie proprietà di accesso XML.</span><span class="sxs-lookup"><span data-stu-id="5c076-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="5c076-132">Cenni preliminari su LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c076-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="5c076-133">Fornisce un'introduzione all'uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5c076-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="5c076-134">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c076-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="5c076-135">Fornisce un'introduzione all'uso di valori letterali XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5c076-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="5c076-136">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c076-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="5c076-137">Vengono forniti collegamenti alle sezioni sul caricamento e modifica di XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5c076-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="5c076-138">XML</span><span class="sxs-lookup"><span data-stu-id="5c076-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="5c076-139">Vengono forniti collegamenti alle sezioni che descrivono come utilizzare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5c076-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
