---
title: "Procedura: Gestire un'eccezione usando try-catch - Guida per programmatori C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: 17b3be52bb89a1cf74bb8171ca937e434a8d94f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552528"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Procedura: Gestire un'eccezione usando try/catch (Guida per programmatori C#)
Lo scopo di un blocco [try-catch](../../../csharp/language-reference/keywords/try-catch.md) è quello di rilevare e gestire un'eccezione generata da codice in esecuzione. Alcune eccezioni possono essere gestite in un blocco `catch` e il problema viene risolto senza che l'eccezione venga generata nuovamente. Molto spesso, invece, l'unica cosa che si possa fare è assicurarsi che venga generata l'eccezione appropriata.  
  
## <a name="example"></a>Esempio  
 In questo esempio <xref:System.IndexOutOfRangeException> non è l'eccezione più appropriata: <xref:System.ArgumentOutOfRangeException> ha più senso per il metodo perché l'errore è causato dall'argomento `index` passato dal chiamante.  
  
 [!code-csharp[csProgGuideExceptions#5](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-handle-an-exception-using-try-catch_1.cs)]  
  
## <a name="comments"></a>Commenti  
 Il codice che genera un'eccezione è racchiuso nel blocco `try`. Subito dopo viene aggiunta un'istruzione `catch` per gestire `IndexOutOfRangeException`, se si verifica. Il blocco `catch` gestisce l'eccezione `IndexOutOfRangeException` e genera al suo posto l'eccezione più appropriata `ArgumentOutOfRangeException`. Per offrire al chiamante quante più informazioni possibili, specificare l'eccezione originale come <xref:System.Exception.InnerException%2A> della nuova eccezione. Poiché la proprietà <xref:System.Exception.InnerException%2A> è [readonly](../../../csharp/language-reference/keywords/readonly.md), è necessario assegnarla nel costruttore della nuova eccezione.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Eccezioni e gestione delle eccezioni](../../../csharp/programming-guide/exceptions/index.md)
- [Gestione delle eccezioni](../../../csharp/programming-guide/exceptions/exception-handling.md)
