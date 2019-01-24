---
title: Ordine dei membri dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: 93ec81d94d8133fc5a6d71d7f1b57b2e9a6aad21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659631"
---
# <a name="data-member-order"></a>Ordine dei membri dati
In alcune applicazioni, è utile conoscere l'ordine in cui i dati dei vari membri dati vengono inviati o si prevede che siano ricevuti (ad esempio l'ordine in cui i dati vengono visualizzati nell'XML serializzato). Talvolta può essere necessario modificare tale ordine. In questo argomento vengono illustrate le regole di ordinamento.  
  
## <a name="basic-rules"></a>Regole di base  
 Le regole di base per l'ordinamento dei dati sono le seguenti:  
  
-   Se un tipo di contratto dei dati fa parte di una gerarchia di ereditarietà, i membri dati dei relativi tipi di base sono sempre i primi dell'ordine.  
  
-   Seguono in ordine alfabetico i membri dati del tipo corrente per i quali non è impostata la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> dell'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
-   Ci sono poi i membri dati per i quali è impostata la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> dell'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>. Questi vengono ordinati prima in base al valore della proprietà `Order` e quindi alfabeticamente in caso di presenza di più membri di un determinato valore `Order`. I valori di ordinamento possono essere ignorati.  
  
 L'ordine alfabetico viene stabilito chiamando il metodo <xref:System.String.CompareOrdinal%2A>.  
  
## <a name="examples"></a>Esempi  
 Si consideri il codice seguente.  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 L'XML prodotto è simile al codice seguente.  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>   
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>   
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>   
</DerivedType>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Runtime.Serialization.DataContractAttribute>
- [Equivalenza dei contratti di dati](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)
- [Uso di contratti di dati](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
