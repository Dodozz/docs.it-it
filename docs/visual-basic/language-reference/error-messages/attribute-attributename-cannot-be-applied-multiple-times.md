---
title: Impossibile applicare più volte l'attributo '<attributename>'
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: da4a766e2617308cb33b9673a88db9e7a954152a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935317"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>Attributo '\<NomeAttributo >' non può essere applicato più volte
L'attributo può essere applicato una sola volta. Il `AttributeUsage` attributo determina se un attributo può essere applicato più volte.  
  
 **ID errore:** BC30663  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Assicurarsi che l'attributo viene applicato una sola volta.  
  
2. Se si usano attributi personalizzati, è possibile modificare i `AttributeUsage` attributo per consentire l'utilizzo di più attributi, come con l'esempio seguente.  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.AttributeUsageAttribute>
- [Creazione di attributi personalizzati](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
