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
# <a name="interoperable-object-references"></a>Riferimenti a oggetti interoperativi
Per impostazione predefinita <xref:System.Runtime.Serialization.DataContractSerializer> serializza gli oggetti per valore. È possibile usare la proprietà <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> per indicare al serializzatore dei contratti dati di mantenere i riferimenti all'oggetto durante la serializzazione degli oggetti del tipo.  
  
## <a name="generated-xml"></a>XML generato  
 Si consideri, come esempio, l'oggetto seguente:  
  
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
  
 Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `false` (impostazione predefinita), viene generato l'XML seguente:  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `true`, viene generato l'XML seguente:  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 <xref:System.Runtime.Serialization.XsdDataContractExporter> non descrive, tuttavia, gli attributi `id` e `ref` nello schema, anche quando la proprietà `preserveObjectReferences` viene impostata su `true`.  
  
## <a name="using-isreference"></a>Uso di IsReference  
 Per generare informazioni di riferimento all'oggetto valide secondo lo schema che lo descrive, applicare l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo e impostare il flag <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> su `true`. Uso di `IsReference` nella classe dell'esempio precedente `X`:  
  
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
  
 L'XML generato è il seguente:  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 L'utilizzo di `IsReference` garantisce conformità nelle sequenze di andata e ritorno dei messaggi. In caso contrario, quando viene generato un tipo da uno schema, l'XML restituito per il tipo non è necessariamente compatibile con lo schema inizialmente presupposto. In altre parole, nonostante la serializzazione degli attributi `id` e `ref`, lo schema originale avrebbe potuto impedire a tali attributi (o a tutti gli attributi) di verificarsi nell'XML. Se si applica `IsReference` a un membro dati, il membro continua a essere riconosciuto come possibile riferimento quando si trova in una sequenza di andata e ritorno.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
