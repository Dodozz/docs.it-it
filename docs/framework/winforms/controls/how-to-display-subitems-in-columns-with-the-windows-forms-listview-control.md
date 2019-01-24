---
title: 'Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: bd41dda048aadc399c7f8ffe0926b010991d08a0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686751"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="a9461-102">Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a9461-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="a9461-103">I moduli di Windows <xref:System.Windows.Forms.ListView> controllo può visualizzare testo aggiuntivi o secondari, per ogni elemento nella visualizzazione dettagli.</span><span class="sxs-lookup"><span data-stu-id="a9461-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="a9461-104">La prima colonna consente di visualizzare il testo dell'elemento, ad esempio un numero di dipendenti.</span><span class="sxs-lookup"><span data-stu-id="a9461-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="a9461-105">La seconda, terza le colonne successive visualizzano il primo, secondo e successivi elementi secondari associati.</span><span class="sxs-lookup"><span data-stu-id="a9461-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="a9461-106">Per aggiungere gli elementi secondari a un elemento di elenco</span><span class="sxs-lookup"><span data-stu-id="a9461-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="a9461-107">Aggiungere tutte le colonne necessite.</span><span class="sxs-lookup"><span data-stu-id="a9461-107">Add any columns needed.</span></span> <span data-ttu-id="a9461-108">Poiché la prima colonna visualizzerà l'elemento <xref:System.Windows.Forms.ListView.Text%2A> proprietà, è necessario una colonna in più di quanti sono gli elementi secondari.</span><span class="sxs-lookup"><span data-stu-id="a9461-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="a9461-109">Per altre informazioni sull'aggiunta di colonne, vedere [come: Aggiungere colonne per i Windows Form controllo ListView](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="a9461-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="a9461-110">Chiamare il <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> della raccolta restituita dal metodo di <xref:System.Windows.Forms.ListViewItem.SubItems%2A> proprietà di un elemento.</span><span class="sxs-lookup"><span data-stu-id="a9461-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="a9461-111">L'esempio di codice seguente imposta il nome del dipendente e reparto per un elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a9461-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="a9461-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9461-112">See also</span></span>
- [<span data-ttu-id="a9461-113">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="a9461-113">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
- [<span data-ttu-id="a9461-114">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a9461-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="a9461-115">Procedura: Aggiungere colonne al controllo ListView Windows Form</span><span class="sxs-lookup"><span data-stu-id="a9461-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="a9461-116">Procedura: Visualizzare le icone per il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a9461-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="a9461-117">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="a9461-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
