---
title: Serializzazione selettiva
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: af608031a661037b89c9783ac2451a6b536f9cd4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731387"
---
# <a name="selective-serialization"></a>Serializzazione selettiva
Una classe spesso contiene campi che non devono essere serializzati. Ad esempio, si prenda in considerazione una classe che archivia un ID del thread in una variabile membro. Quando la classe viene deserializzata, il thread archivia l'ID nel caso in cui la classe serializzata non sia più in esecuzione. La serializzazione di questo valore non ha quindi senso. È possibile evitare che le variabili membro vengano serializzate contrassegnandole con l'attributo [NonSerialized](xref:System.NonSerializedAttribute) come riportato di seguito.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

Se possibile, rendere non serializzabili gli oggetti che possono contenere dati sensibili alla sicurezza. Se l'oggetto deve essere serializzato, applicare l'attributo `NonSerialized` ai campi specifici che archiviano dati sensibili. Se non si escludono questi campi dalla serializzazione, è necessario essere consapevoli che i dati archiviati sono esposti a qualsiasi codice con le autorizzazioni per la serializzazione. Per altre informazioni sulla scrittura di codice di serializzazione sicuro, vedere [Sicurezza e serializzazione](../../../docs/framework/misc/security-and-serialization.md).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione binaria](binary-serialization.md)
- [Serializzazione SOAP e XML](xml-and-soap-serialization.md)
- [Sicurezza e serializzazione](../../../docs/framework/misc/security-and-serialization.md)
