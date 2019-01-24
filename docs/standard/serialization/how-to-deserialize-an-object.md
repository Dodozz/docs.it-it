---
title: 'Procedura: Deserializzare un oggetto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: d0b953e4f570f349edeb80fc2316530494905ec0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583311"
---
# <a name="how-to-deserialize-an-object"></a><span data-ttu-id="3ace0-102">Procedura: Deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="3ace0-102">How to: Deserialize an Object</span></span>
<span data-ttu-id="3ace0-103">Quando si deserializza un oggetto, il formato di trasporto determina se verrà creato un flusso o un oggetto file.</span><span class="sxs-lookup"><span data-stu-id="3ace0-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="3ace0-104">Una volta determinato il formato di trasporto, è possibile chiamare i metodi <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> o <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>, in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="3ace0-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="3ace0-105">Per deserializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="3ace0-105">To deserialize an object</span></span>  
  
1.  <span data-ttu-id="3ace0-106">Construire un <xref:System.Xml.Serialization.XmlSerializer> che utilizza il tipo dell'oggetto da deserializzare.</span><span class="sxs-lookup"><span data-stu-id="3ace0-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>  
  
2.  <span data-ttu-id="3ace0-107">Chiamare il metodo <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> per produrre una replica dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3ace0-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="3ace0-108">Durante la deserializzazione, è necessario eseguire il cast dell'oggetto restituito al tipo dell'originale, come illustrato nell'esempio riportato di seguito, in cui viene deserializzato l'oggetto in un file (sebbene possa anche essere deserializzato in un flusso).</span><span class="sxs-lookup"><span data-stu-id="3ace0-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object into a file (although it could also be deserialized into a stream).</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3ace0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ace0-109">See also</span></span>

- [<span data-ttu-id="3ace0-110">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="3ace0-110">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="3ace0-111">Procedura: Serializzare un oggetto</span><span class="sxs-lookup"><span data-stu-id="3ace0-111">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
