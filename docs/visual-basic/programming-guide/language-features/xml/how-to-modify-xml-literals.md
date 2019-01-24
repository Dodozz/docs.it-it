---
title: 'Procedura: Modificare i valori letterali XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 7a01fdc9d0541b5d277c2f283e25e9a1cef3b862
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636339"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="80b53-102">Procedura: Modificare i valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80b53-102">How to: Modify XML Literals (Visual Basic)</span></span>
<span data-ttu-id="80b53-103">Visual Basic consente di modificare i valori letterali XML agevolmente.</span><span class="sxs-lookup"><span data-stu-id="80b53-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="80b53-104">È possibile aggiungere o eliminare elementi e attributi ed è anche possibile sostituire un elemento esistente con un nuovo elemento XML.</span><span class="sxs-lookup"><span data-stu-id="80b53-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="80b53-105">In questo argomento fornisce alcuni esempi di come modificare un valore letterale XML esistente.</span><span class="sxs-lookup"><span data-stu-id="80b53-105">This topic provides several examples of how to modify an existing XML literal.</span></span>  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="80b53-106">Per modificare il valore di un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="80b53-106">To modify the value of an XML literal</span></span>  
  
1.  <span data-ttu-id="80b53-107">Per modificare il valore di un valore letterale XML, ottenere un riferimento al codice XML letterale e impostare il `Value` proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="80b53-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>  
  
     <span data-ttu-id="80b53-108">Nell'esempio seguente aggiorna il valore di tutti i \<prezzo > elementi in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="80b53-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]  
  
     <span data-ttu-id="80b53-109">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="80b53-109">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>47.20</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>48.25</Price>  
      </Book>  
    </Catalog>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="80b53-110">Il `Value` proprietà fa riferimento al primo elemento in una raccolta di XML.</span><span class="sxs-lookup"><span data-stu-id="80b53-110">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="80b53-111">Se è presente più di un elemento che ha lo stesso nome in una raccolta, l'impostazione di `Value` proprietà interessa solo il primo elemento nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="80b53-111">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="80b53-112">Per aggiungere un attributo a un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="80b53-112">To add an attribute to an XML literal</span></span>  
  
1.  <span data-ttu-id="80b53-113">Per aggiungere un attributo a un valore letterale XML, ottenere prima un riferimento al valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="80b53-113">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="80b53-114">È quindi possibile aggiungere un attributo mediante l'aggiunta di una proprietà axis dell'attributo XML nuovo.</span><span class="sxs-lookup"><span data-stu-id="80b53-114">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="80b53-115">È anche possibile aggiungere una nuova <xref:System.Xml.Linq.XAttribute> oggetto per il valore letterale XML tramite la <xref:System.Xml.Linq.XContainer.Add%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="80b53-115">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="80b53-116">Nell'esempio seguente illustra entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="80b53-116">The following example shows both options.</span></span>  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]  
  
     <span data-ttu-id="80b53-117">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="80b53-117">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
    ```  
  
     <span data-ttu-id="80b53-118">Per altre informazioni sulle proprietà dell'asse degli attributi XML, vedere [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="80b53-118">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>  
  
### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="80b53-119">Per aggiungere un elemento a un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="80b53-119">To add an element to an XML literal</span></span>  
  
1.  <span data-ttu-id="80b53-120">Per aggiungere un elemento a un valore letterale XML, ottenere prima un riferimento al valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="80b53-120">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="80b53-121">È quindi possibile aggiungere una nuova <xref:System.Xml.Linq.XElement> oggetti come sottoelemento dell'ultimo elemento dell'elemento usando la <xref:System.Xml.Linq.XContainer.Add%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="80b53-121">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="80b53-122">È possibile aggiungere una nuova <xref:System.Xml.Linq.XElement> oggetto come primo sottoelemento con il <xref:System.Xml.Linq.XContainer.AddFirst%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="80b53-122">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>  
  
     <span data-ttu-id="80b53-123">Per aggiungere un nuovo elemento in un percorso specifico rispetto agli altri sottoelementi, ottenere prima un riferimento a un sottoelemento adiacente.</span><span class="sxs-lookup"><span data-stu-id="80b53-123">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="80b53-124">È quindi possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement> oggetto prima dell'elemento adiacente secondario usando la <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="80b53-124">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="80b53-125">È anche possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement> oggetto dopo l'elemento adiacente secondario usando la <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="80b53-125">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>  
  
     <span data-ttu-id="80b53-126">Nell'esempio seguente illustra esempi di ognuna di queste tecniche.</span><span class="sxs-lookup"><span data-stu-id="80b53-126">The following example shows examples of each of these techniques.</span></span>  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]  
  
     <span data-ttu-id="80b53-127">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="80b53-127">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331">  
        <Publisher>Microsoft Press</Publisher>  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <PublishDate>2005-2-14</PublishDate>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
    ```  
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="80b53-128">Per rimuovere un elemento o attributo da un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="80b53-128">To remove an element or attribute from an XML literal</span></span>  
  
1.  <span data-ttu-id="80b53-129">Per rimuovere un elemento o un attributo da un valore letterale XML, ottenere un riferimento per l'elemento o attributo e chiamare il `Remove` metodo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="80b53-129">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]  
  
     <span data-ttu-id="80b53-130">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="80b53-130">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book></Catalog>  
    ```  
  
     <span data-ttu-id="80b53-131">Per rimuovere tutti gli elementi o attributi da un valore letterale XML, ottenere un riferimento al codice XML letterale e chiamare il <xref:System.Xml.Linq.XElement.RemoveAll%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="80b53-131">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>  
  
### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="80b53-132">Per modificare un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="80b53-132">To modify an XML literal</span></span>  
  
1.  <span data-ttu-id="80b53-133">Per modificare il nome di un elemento XML, ottenere prima un riferimento all'elemento.</span><span class="sxs-lookup"><span data-stu-id="80b53-133">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="80b53-134">È quindi possibile creare una nuova <xref:System.Xml.Linq.XElement> oggetto che è disponibile un nuovo nome e passa il nuovo <xref:System.Xml.Linq.XElement> dell'oggetto per il <xref:System.Xml.Linq.XNode.ReplaceWith%2A> metodo esistenti <xref:System.Xml.Linq.XElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="80b53-134">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="80b53-135">Se l'elemento che si stia sostituendo dispone di sottoelementi che devono essere conservati, impostare il valore della nuova <xref:System.Xml.Linq.XElement> dell'oggetto per il <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà dell'elemento esistente.</span><span class="sxs-lookup"><span data-stu-id="80b53-135">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="80b53-136">Si imposterà il valore del nuovo elemento per il codice XML interno dell'elemento esistente.</span><span class="sxs-lookup"><span data-stu-id="80b53-136">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="80b53-137">In caso contrario, è possibile impostare il valore del nuovo elemento per il `Value` proprietà dell'elemento esistente.</span><span class="sxs-lookup"><span data-stu-id="80b53-137">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>  
  
     <span data-ttu-id="80b53-138">Esempio di codice seguente sostituisce tutte \<descrizione > gli elementi con un \<astratta > elemento.</span><span class="sxs-lookup"><span data-stu-id="80b53-138">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="80b53-139">Il contenuto del \<descrizione > elemento viene mantenuto nel nuovo \<astratta > elemento usando la <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà del \<descrizione > <xref:System.Xml.Linq.XElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="80b53-139">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]  
  
     <span data-ttu-id="80b53-140">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="80b53-140">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
        <Description>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Description>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <Description>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Description>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <MSRP>44.95</MSRP>    <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>    <Abstract>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Abstract>  
      </Book>  
    </Catalog>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="80b53-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80b53-141">See also</span></span>
- [<span data-ttu-id="80b53-142">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80b53-142">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="80b53-143">XML</span><span class="sxs-lookup"><span data-stu-id="80b53-143">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="80b53-144">Procedura: Caricare il documento XML da un File, stringa o Stream</span><span class="sxs-lookup"><span data-stu-id="80b53-144">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="80b53-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="80b53-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="80b53-146">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80b53-146">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
