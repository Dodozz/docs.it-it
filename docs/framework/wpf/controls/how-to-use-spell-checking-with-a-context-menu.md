---
title: 'Procedura: Usare il controllo ortografico con un menu di scelta rapida'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 72b24c386eb99140c9c2729688994b81f92e1a6f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192979"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a>Procedura: Usare il controllo ortografico con un menu di scelta rapida
Per impostazione predefinita, quando si abilita il controllo ortografico in un controllo di modifica, ad esempio <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>, si ottengono le opzioni di controllo ortografico nel menu di scelta rapida. Ad esempio, quando gli utenti fare doppio clic su una parola errata, ricevono un set di suggerimenti ortografici o la possibilità **Ignora tutto**. Tuttavia, quando si esegue l'override di menu di scelta rapida predefinito con il proprio menu di scelta rapida personalizzato, questa funzionalità viene persa e devi scrivere codice per riabilitare la funzionalità di controllo ortografico nel menu di scelta rapida. Nell'esempio seguente viene illustrato come abilitare questa opzione su un <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra le [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che crea un <xref:System.Windows.Controls.TextBox> con alcuni degli eventi che vengono usate per implementare il menu di scelta rapida.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il codice che implementa il menu di scelta rapida.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 Il codice utilizzato per raggiungere questo obiettivo con un <xref:System.Windows.Controls.RichTextBox> è simile. La differenza principale è nel passato al parametro il `GetSpellingError` (metodo). Per un <xref:System.Windows.Controls.TextBox>, passare l'indice integer della posizione del punto di inserimento:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Per un <xref:System.Windows.Controls.RichTextBox>, passare il <xref:System.Windows.Documents.TextPointer> che specifica la posizione del cursore:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni preliminari sul controllo RichTextBox](richtextbox-overview.md)
- [Attivare il controllo ortografico in un controllo di modifica del testo](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [Usare un menu di scelta rapida personalizzato con un oggetto TextBox](how-to-use-a-custom-context-menu-with-a-textbox.md)
