---
title: Modifica della selezione a livello di codice in un oggetto RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: 1dd6063796c7ed63ddee5e6e2338663db1340fec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664643"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a>Modifica della selezione a livello di codice in un oggetto RichTextBox
In questo esempio viene illustrato come modificare a livello di codice la selezione corrente in un <xref:System.Windows.Controls.RichTextBox>. Questa selezione è lo stesso come se l'utente ha selezionato il contenuto usando l'interfaccia utente.  
  
## <a name="example"></a>Esempio  
 Quanto segue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] codice descrive un oggetto denominato <xref:System.Windows.Controls.RichTextBox> controllo con contenuto semplice.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente a livello di codice consente di selezionare testo arbitrario quando l'utente fa clic all'interno di <xref:System.Windows.Controls.RichTextBox>.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
- [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
