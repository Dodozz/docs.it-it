---
title: add - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: 6cc1b504de383ae63284ecb3ac7d0b1b47b36bfe
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244375"
---
# <a name="add-c-reference"></a>add (Riferimenti per C#)
La parola chiave contestuale `add` viene usata per definire una funzione di accesso a eventi personalizzata che viene chiamata quando il codice client sottoscrive l'[evento](../../../csharp/language-reference/keywords/event.md). Se si specifica una funzione di accesso `add` personalizzata, è necessario specificare anche una funzione di accesso [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un evento con le funzioni di accesso `add` personalizzata e [remove](../../../csharp/language-reference/keywords/remove.md). Per l'esempio completo, vedere [Procedura:  Implementare eventi di interfaccia](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 In genere, non è necessario fornire funzioni di accesso a eventi personalizzate. Le funzioni di accesso generate automaticamente dal compilatore quando si dichiara un evento sono sufficienti per la maggior parte degli scenari.  
  
## <a name="see-also"></a>Vedere anche  
- [Eventi](../../../csharp/programming-guide/events/index.md)
