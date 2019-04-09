---
title: Riferimenti a oggetti interoperativi
ms.date: 03/30/2017
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 9cbbd5a34269a7c4a5c33d72487a02df21f2f0fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222705"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="29ea6-102">Riferimenti a oggetti interoperativi</span><span class="sxs-lookup"><span data-stu-id="29ea6-102">Interoperable Object References</span></span>
<span data-ttu-id="29ea6-103">Per impostazione predefinita <xref:System.Runtime.Serialization.DataContractSerializer> serializza gli oggetti per valore.</span><span class="sxs-lookup"><span data-stu-id="29ea6-103">By default the <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="29ea6-104">È possibile usare la proprietà <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> per indicare al serializzatore dei contratti dati di mantenere i riferimenti all'oggetto durante la serializzazione degli oggetti del tipo.</span><span class="sxs-lookup"><span data-stu-id="29ea6-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the Data Contract Serializer to preserve object references when serializing objects of the type.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="29ea6-105">XML generato</span><span class="sxs-lookup"><span data-stu-id="29ea6-105">Generated XML</span></span>  
 <span data-ttu-id="29ea6-106">Si consideri, come esempio, l'oggetto seguente:</span><span class="sxs-lookup"><span data-stu-id="29ea6-106">As an example, consider the following object:</span></span>  
  
```  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass   
{  
}  
```  
  
 <span data-ttu-id="29ea6-107">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `false` (impostazione predefinita), viene generato l'XML seguente:</span><span class="sxs-lookup"><span data-stu-id="29ea6-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="29ea6-108">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `true`, viene generato l'XML seguente:</span><span class="sxs-lookup"><span data-stu-id="29ea6-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 <span data-ttu-id="29ea6-109"><xref:System.Runtime.Serialization.XsdDataContractExporter> non descrive, tuttavia, gli attributi `id` e `ref` nello schema, anche quando la proprietà `preserveObjectReferences` viene impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="29ea6-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> does not describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="29ea6-110">Uso di IsReference</span><span class="sxs-lookup"><span data-stu-id="29ea6-110">Using IsReference</span></span>  
 <span data-ttu-id="29ea6-111">Per generare informazioni di riferimento all'oggetto valide secondo lo schema che lo descrive, applicare l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo e impostare il flag <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="29ea6-111">To generate object reference information that is valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="29ea6-112">Uso di `IsReference` nella classe dell'esempio precedente `X`:</span><span class="sxs-lookup"><span data-stu-id="29ea6-112">Using `IsReference` in the previous example class `X`:</span></span>  
  
 `[DataContract(IsReference=true)] public class X`  
  
 `{`  
  
 `SomeClass someInstance = new SomeClass();`  
  
 `[DataMember]`  
  
 `public SomeClass A = someInstance;`  
  
 `[DataMember]`  
  
 `public SomeClass B = someInstance;`  
  
 `}`  
  
 `public class SomeClass`  
  
 `{`  
  
 `}`  
  
 <span data-ttu-id="29ea6-113">L'XML generato è il seguente:</span><span class="sxs-lookup"><span data-stu-id="29ea6-113">The generated XML is as follows:</span></span>  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 <span data-ttu-id="29ea6-114">L'utilizzo di `IsReference` garantisce conformità nelle sequenze di andata e ritorno dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="29ea6-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="29ea6-115">In caso contrario, quando viene generato un tipo da uno schema, l'XML restituito per il tipo non è necessariamente compatibile con lo schema inizialmente presupposto.</span><span class="sxs-lookup"><span data-stu-id="29ea6-115">Without it, when a type is generated from schema, what is sent back as XML for that type is not necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="29ea6-116">In altre parole, nonostante la serializzazione degli attributi `id` e `ref`, lo schema originale avrebbe potuto impedire a tali attributi (o a tutti gli attributi) di verificarsi nell'XML.</span><span class="sxs-lookup"><span data-stu-id="29ea6-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="29ea6-117">Se si applica `IsReference` a un membro dati, il membro continua a essere riconosciuto come possibile riferimento quando si trova in una sequenza di andata e ritorno.</span><span class="sxs-lookup"><span data-stu-id="29ea6-117">With `IsReference` applied to a data member, the member continues to be recognized as "referenceable" when roundtripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29ea6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29ea6-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
