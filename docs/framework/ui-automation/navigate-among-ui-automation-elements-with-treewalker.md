---
title: Navigare tra gli elementi di automazione interfaccia utente utilizzando TreeWalker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, TreeWalker
- TreeWalker class
- elements, navigating among
- UI Automation, navigating among elements
ms.assetid: afcd21dc-2ffa-48c9-9332-51269f44b7e9
ms.openlocfilehash: aed8c624a75364dcc97c73ae7ebd6331275ceff4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182871"
---
# <a name="navigate-among-ui-automation-elements-with-treewalker"></a>Navigare tra gli elementi di automazione interfaccia utente utilizzando TreeWalker
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento contiene codice di esempio che illustra come passare tra [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementi con il <xref:System.Windows.Automation.TreeWalker> classe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa <xref:System.Windows.Automation.TreeWalker.GetParent%2A> per scorrere la [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] albero fino a individuare l'elemento radice o desktop. L'elemento subito dopo che è la finestra padre dell'elemento specificato.  
  
 [!code-csharp[UIAFocusTracker_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFocusTracker_snip/CSharp/FocusTracker.cs#102)]
 [!code-vb[UIAFocusTracker_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFocusTracker_snip/VisualBasic/FocusTracker.vb#102)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa <xref:System.Windows.Automation.TreeWalker.GetFirstChild%2A> e <xref:System.Windows.Automation.TreeWalker.GetNextSibling%2A> per creare un <xref:System.Windows.Forms.TreeView> che visualizza un intero sottoalbero di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elementi che sono nella visualizzazione controlli e che sono abilitati.  
  
 [!code-csharp[UIAClient_snip#174](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#174)]
 [!code-vb[UIAClient_snip#174](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#174)]  
  
## <a name="see-also"></a>Vedere anche

- [Ottenere elementi di automazione interfaccia utente](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
