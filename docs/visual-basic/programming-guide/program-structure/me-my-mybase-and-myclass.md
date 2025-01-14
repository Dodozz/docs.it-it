---
title: Me, My, MyBase e MyClass in Visual Basic
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: 3eca756429c5fec8f324a17350844b59baf9ccf7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586262"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase e MyClass in Visual Basic
`Me`, `My`, `MyBase`, e `MyClass` in Visual Basic hanno nomi simili, ma scopi diversi. Questo argomento descrive ognuna di queste entità per distinguerli.  
  
## <a name="me"></a>Me  
 Il `Me` (parola chiave) fornisce un modo per fare riferimento all'istanza specifica di una classe o struttura in cui è attualmente in esecuzione il codice. `Me` si comporta come una variabile oggetto o una variabile di struttura che fa riferimento all'istanza corrente. Usando `Me` è particolarmente utile per passare le informazioni relative all'istanza attualmente in esecuzione di una classe o struttura a una routine in un'altra classe, struttura o modulo.  
  
 Ad esempio, si supponga di che avere la seguente procedura in un modulo.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 È possibile chiamare la routine e passare l'istanza corrente del <xref:System.Windows.Forms.Form> classe come un argomento usando l'istruzione seguente.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 Il `My` funzionalità fornisce l'accesso semplice e intuitivo a numerose classi .NET Framework, che consente all'utente di Visual Basic interagire con il computer, applicazioni, impostazioni, risorse e così via.  
  
## <a name="mybase"></a>MyBase  
 Il `MyBase` (parola chiave) si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe. `MyBase` viene comunemente utilizzato per accedere ai membri di classe base sottoposto a override o shadowing in una classe derivata. `MyBase.New` Consente di chiamare in modo esplicito un costruttore di classe di base da un costruttore di classe derivata.  
  
## <a name="myclass"></a>MyClass  
 Il `MyClass` (parola chiave) si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente. `MyClass` è simile a `Me`, ma tutte le chiamate di metodo su di essa sono trattate come se fosse il metodo `NotOverridable`.  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
