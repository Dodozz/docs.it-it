---
title: 'Procedura: Associare un menu di scelta rapida a un nodo di TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: f818cccb3103866af993f1aff527a9c1a7c82109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053015"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="4f8c9-102">Procedura: Associare un menu di scelta rapida a un nodo di TreeView</span><span class="sxs-lookup"><span data-stu-id="4f8c9-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="4f8c9-103">I moduli di Windows <xref:System.Windows.Forms.TreeView> controllo Visualizza una gerarchia di nodi, simile ai file e cartelle vengono visualizzati nel riquadro a sinistra di Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="4f8c9-104">Impostando il <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire operazioni sensibili al contesto per l'utente quando sono fare doppio clic il <xref:System.Windows.Forms.TreeView> controllo.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="4f8c9-105">Associando un <xref:System.Windows.Forms.ContextMenuStrip> componenti con singolo <xref:System.Windows.Forms.TreeNode> gli elementi, è possibile aggiungere un livello di funzionalità dal menu di scelta rapida per personalizzato di <xref:System.Windows.Forms.TreeView> controlli.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="4f8c9-106">Per associare un menu di scelta rapida a un TreeNode a livello di codice</span><span class="sxs-lookup"><span data-stu-id="4f8c9-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1. <span data-ttu-id="4f8c9-107">Creare un'istanza di un <xref:System.Windows.Forms.TreeView> controllo con le impostazioni delle proprietà appropriata, creare una radice <xref:System.Windows.Forms.TreeNode>e quindi aggiungere i sottonodi.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2. <span data-ttu-id="4f8c9-108">Creare un'istanza di un <xref:System.Windows.Forms.ContextMenuStrip> componente, quindi aggiungere un <xref:System.Windows.Forms.ToolStripMenuItem> per ogni operazione che si desidera rendere disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3. <span data-ttu-id="4f8c9-109">Impostare il <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> proprietà del appropriato <xref:System.Windows.Forms.TreeNode> al menu di scelta rapida si crea.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4. <span data-ttu-id="4f8c9-110">Quando questa proprietà è impostata, verrà visualizzato il menu di scelta rapida si fa clic con il pulsante destro del nodo.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="4f8c9-111">L'esempio di codice seguente viene creata una semplice <xref:System.Windows.Forms.TreeView> e <xref:System.Windows.Forms.ContextMenuStrip> associato alla radice <xref:System.Windows.Forms.TreeNode> del <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="4f8c9-112">È necessario personalizzare le opzioni di menu in base a quelle di <xref:System.Windows.Forms.TreeView> si sta sviluppando.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="4f8c9-113">Inoltre, è opportuno scrivere codice per gestire il <xref:System.Windows.Forms.ToolStripItem.Click> gli eventi per queste voci di menu.</span><span class="sxs-lookup"><span data-stu-id="4f8c9-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4f8c9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f8c9-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="4f8c9-115">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="4f8c9-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
