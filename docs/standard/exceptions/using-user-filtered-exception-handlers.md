---
title: Utilizzo di gestori eccezioni filtrati dall'utente
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d1e771a95542153dfad0981d3198e6b4c31cdeb9
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261420"
---
# <a name="using-user-filtered-exception-handlers"></a>Utilizzo di gestori eccezioni filtrati dall'utente
In Visual Basic sono attualmente supportate eccezioni filtrate dall'utente. I gestori di eccezioni filtrati dall'utente intercettano e gestiscono le eccezioni in base a requisiti definiti dall'utente per le singole eccezioni. Tali gestori usano l'istruzione **Catch** con la parola chiave **When**.  
  
 Questa tecnica è utile quando un particolare oggetto eccezione corrisponde a più errori. In questo caso l'oggetto presenta in genere una proprietà che contiene il codice di errore specifico associato all'errore. È possibile usare la proprietà del codice di errore nell'espressione per selezionare solo l'errore particolare che si desidera gestire in tale clausola **Catch**.  
  
 L'esempio di Visual Basic seguente illustra l'istruzione **Catch/When**.  
  
```  
Try  
      'Try statements.  
   Catch When Err = VBErr_ClassLoadException  
      'Catch statements.  
End Try  
```  
  
 L'espressione della clausola filtrata dall'utente non è sottoposta ad alcuna restrizione. Se durante l'esecuzione dell'espressione filtrata dall'utente si verifica un'eccezione, quest'ultima viene ignorata e si considera che l'espressione di filtro abbia restituito il valore false. In questo caso Common Language Runtime continua la ricerca di un gestore per l'eccezione corrente.  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a>Combinazione di un'eccezione specifica e di clausole filtrate dall'utente  
 Un'istruzione catch può contenere sia l'eccezione specifica che le clausole filtrate dall'utente. Nel runtime viene prima eseguito il test dell'eccezione specifica. Se l'eccezione specifica ha esito positivo, verrà eseguito il filtro dell'utente. Il filtro generico può contenere un riferimento alla variabile dichiarata nel filtro della classe. Si noti che non è possibile invertire l'ordine delle due clausole di filtro.  
  
 L'esempio di Visual Basic seguente illustra l'eccezione specifica `ClassLoadException` nell'istruzione **Catch** e la clausola filtrata dall'utente che usa la parola chiave **When**.  
  
```  
Try  
      'Try statements.  
   Catch cle As ClassLoadException When cle.IsRecoverable()  
      'Catch statements.  
End Try  
```  

## <a name="see-also"></a>Vedere anche

- [Eccezioni](index.md)
