---
title: Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 1a356e2872f803d393015574c380c5f99110074e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185602"
---
# <a name="find-and-highlight-text-using-ui-automation"></a>Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento viene illustrato come sequenza cercare ed evidenziare tutte le occorrenze di una stringa all'interno del contenuto di un controllo testo utilizzando [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].  
  
## <a name="example"></a>Esempio  
 L'esempio seguente ottiene un <xref:System.Windows.Automation.TextPattern> oggetto da un controllo testo. Oggetto <xref:System.Windows.Automation.Text.TextPatternRange> oggetto che rappresenta il contenuto testuale dell'intero documento, viene quindi creata utilizzando la <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> proprietà di questo oggetto <xref:System.Windows.Automation.TextPattern>. Altri due <xref:System.Windows.Automation.Text.TextPatternRange> gli oggetti vengono quindi creati per la ricerca sequenza ed evidenziare la funzionalità.  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a>Vedere anche  
 [Trovare ed evidenziare il testo usando l'automazione interfaccia utente](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
