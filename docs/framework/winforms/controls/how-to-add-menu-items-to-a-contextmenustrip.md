---
title: 'Procedura: Aggiungere le voci di Menu a un controllo ContextMenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: 88bf56ea21c4f120b9d745e7f8a31fed485fa192
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506238"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="dd1ab-102">Procedura: Aggiungere le voci di Menu a un controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="dd1ab-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="dd1ab-103">È possibile aggiungere solo una voce di menu o diversi elementi contemporaneamente in un <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="dd1ab-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="dd1ab-104">Per aggiungere una singola voce di menu a un controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="dd1ab-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="dd1ab-105">Usare la <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> metodo per aggiungere una voce di menu per un <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="dd1ab-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="dd1ab-106">Per aggiungere più voci di menu a un controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="dd1ab-106">To add several menu items to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="dd1ab-107">Usare la <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> metodo più voci di menu per aggiungere un <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="dd1ab-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dd1ab-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd1ab-108">See also</span></span>
- [<span data-ttu-id="dd1ab-109">Controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="dd1ab-109">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
