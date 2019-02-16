---
title: 'Procedura: Gestire gli eventi Input utente dei controlli Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: e4fa03a07e97fe1d860b281b8e5cece0c41d6c27
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "56331961"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a>Procedura: Gestire gli eventi Input utente dei controlli Windows Form
In questo esempio viene illustrato come gestire la maggior parte degli eventi di convalida, stato attivo, mouse e tastiera che possono verificarsi in un controllo Windows Form. La casella di testo denominata `TextBoxInput` riceve gli eventi quando è attiva e le informazioni relative a ogni evento vengono scritte nella casella di testo denominata `TextBoxOutput` nell'ordine di generazione degli eventi. L'applicazione include anche un set di caselle di controllo che possono essere usate per filtrare gli eventi da segnalare.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="see-also"></a>Vedere anche
- [Input dell'utente in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)
