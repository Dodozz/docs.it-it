---
title: '&lt;exception&gt; - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 1d48d9c05e23154ee98d077af5f43c80b4dbe2fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588112"
---
# <a name="ltexceptiongt-c-programming-guide"></a>&lt;exception&gt; (Guida per programmatori C#)
## <a name="syntax"></a>Sintassi  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>Parametri  
 cref = " `member`"  
 Riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente. Il compilatore controlla che l'eccezione specificata esista e converte `member` nel nome canonico dell'elemento nel file XML di output. `member` deve essere racchiuso tra virgolette doppie (" ").  
  
 Per altre informazioni su come creare un riferimento cref a un tipo generico, vedere [\<see>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Descrizione dell'eccezione.  
  
## <a name="remarks"></a>Note  
 Il tag \<exception> consente di specificare le eccezioni che possono essere generate. Questo tag può essere applicato alle definizioni di metodi, proprietà, eventi e indicizzatori.  
  
 Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.  
  
 Per altre informazioni sulla gestione delle eccezioni, vedere [Eccezioni e gestione delle eccezioni](../../../csharp/programming-guide/exceptions/index.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Tag consigliati per i commenti relativi alla documentazione](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
