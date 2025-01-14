---
title: Associazione anticipata e tardiva (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
ms.openlocfilehash: 20eb96d0d9f81ec9dfa359edf63a60f72a45aa01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973225"
---
# <a name="early-and-late-binding-visual-basic"></a>Associazione anticipata e tardiva (Visual Basic)
Il compilatore Visual Basic esegue un processo denominato `binding` quando un oggetto viene assegnato a una variabile oggetto. Un oggetto è *ad associazione anticipata* quando viene assegnato a una variabile di un tipo object specifico. Gli oggetti ad associazione anticipata consentono al compilatore di allocare memoria ed effettuare altre ottimizzazioni prima dell'esecuzione di un'applicazione. Il frammento di codice seguente, ad esempio, dichiara una variabile di tipo <xref:System.IO.FileStream>:  
  
 [!code-vb[VbVbalrOOP#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#90)]  
  
 Poiché <xref:System.IO.FileStream> è un tipo object specifico, l'istanza assegnata a `FS` è ad associazione anticipata.  
  
 Al contrario, un oggetto è *ad associazione tardiva* quando viene assegnato a una variabile dichiarata di tipo `Object`. Gli oggetti di questo tipo possono contenere riferimenti a qualsiasi oggetto, ma non presentano molti dei vantaggi offerti dagli oggetti ad associazione anticipata. Il frammento di codice seguente, ad esempio, dichiara una variabile oggetto contenente un oggetto restituito dalla funzione `CreateObject`:  
  
 [!code-vb[VbVbalrOOP#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/LateBinding.vb#91)]  
  
## <a name="advantages-of-early-binding"></a>Vantaggi offerti dall'associazione anticipata  
 Quando possibile, è consigliabile usare oggetti ad associazione anticipata. Tali oggetti consentono infatti al compilatore di eseguire ottimizzazioni significative che aumentano l'efficienza delle applicazioni. Gli oggetti ad associazione anticipata sono notevolmente più veloci di quelli ad associazione tardiva e facilitano la lettura e la gestione del codice dichiarando esattamente il tipo degli oggetti usati. Un altro vantaggio dall'associazione anticipata è che consente la funzionalità utili, ad esempio il completamento del codice automatica e la Guida dinamica perché l'ambiente di sviluppo integrato (IDE) di Visual Studio è possibile determinare esattamente quale tipo di oggetto vengono utilizzati durante la modifica di codice. L'associazione anticipata riduce il numero e la gravità degli errori di run-time poiché consente al compilatore di segnalare gli errori al momento della compilazione di un programma.  
  
> [!NOTE]
>  L'associazione tardiva può essere usata soltanto per accedere ai membri di tipi che vengono dichiarati come `Public`. L'accesso a membri dichiarati come `Friend` o `Protected Friend` determina un errore di run-time.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>
- [Durata degli oggetti: Come gli oggetti vengono creati ed eliminati](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
