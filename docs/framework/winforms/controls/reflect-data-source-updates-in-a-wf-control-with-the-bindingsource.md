---
title: "Procedura: Riflettere gli aggiornamenti dell'origine dati in un controllo di Windows Form con BindingSource"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: c08df86596eef23ca4706333cbfa333427fcad0e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614341"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a>Procedura: Riflettere gli aggiornamenti dell'origine dati in un controllo di Windows Form con BindingSource
Quando si usano controlli associati a dati, in alcuni casi è necessario rispondere alle modifiche che si sono verificate nell'origine dati, nel caso in cui quest'ultima non preveda la generazione di eventi di modifica degli elenchi. Quando si usa il componente <xref:System.Windows.Forms.BindingSource> per associare l'origine dati a un controllo Windows Form, è possibile inviare al controllo la notifica di modifica dell'origine dati chiamando il metodo <xref:System.Windows.Forms.BindingSource.ResetBindings%2A>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrato l'uso del metodo <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> per notificare a un controllo associato che l'origine dati è stata aggiornata.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  Vedere anche [come: Compilare ed eseguire un esempio di codice completo di Windows Form con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [Procedura: Associare un controllo di Windows Form a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
