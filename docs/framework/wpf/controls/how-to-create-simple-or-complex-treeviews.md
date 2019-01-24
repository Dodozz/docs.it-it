---
title: 'Procedura: Creare controlli TreeView semplici o complessi'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: d6f9653304b67948d8a8995d1582cb10b012ee06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609135"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a><span data-ttu-id="5ae5e-102">Procedura: Creare controlli TreeView semplici o complessi</span><span class="sxs-lookup"><span data-stu-id="5ae5e-102">How to: Create Simple or Complex TreeViews</span></span>
<span data-ttu-id="5ae5e-103">In questo esempio viene illustrato come creare semplici o complesse <xref:System.Windows.Controls.TreeView> controlli.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-103">This example shows how to create simple or complex <xref:System.Windows.Controls.TreeView> controls.</span></span>  
  
 <span data-ttu-id="5ae5e-104">Oggetto <xref:System.Windows.Controls.TreeView> è costituito da una gerarchia di <xref:System.Windows.Controls.TreeViewItem> controlli, che possono contenere stringhe di testo semplice e contenuto anche più complesso, ad esempio <xref:System.Windows.Controls.Button> controlli o <xref:System.Windows.Controls.StackPanel> con contenuto incorporato.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-104">A <xref:System.Windows.Controls.TreeView> consists of a hierarchy of <xref:System.Windows.Controls.TreeViewItem> controls, which can contain simple text strings and also more complex content, such as <xref:System.Windows.Controls.Button> controls or a <xref:System.Windows.Controls.StackPanel> with embedded content.</span></span> <span data-ttu-id="5ae5e-105">È possibile definire in modo esplicito il <xref:System.Windows.Controls.TreeView> contenuto o un'origine dati può fornire il contenuto.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-105">You can explicitly define the <xref:System.Windows.Controls.TreeView> content or a data source can provide the content.</span></span> <span data-ttu-id="5ae5e-106">In questo argomento vengono forniti esempi di questi concetti.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-106">This topic provides examples of these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ae5e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ae5e-107">Example</span></span>  
 <span data-ttu-id="5ae5e-108">Il <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà del <xref:System.Windows.Controls.TreeViewItem> include il contenuto che il <xref:System.Windows.Controls.TreeView> Visualizza per quell'elemento.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-108">The <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property of the <xref:System.Windows.Controls.TreeViewItem> contains the content that the <xref:System.Windows.Controls.TreeView> displays for that item.</span></span> <span data-ttu-id="5ae5e-109">Oggetto <xref:System.Windows.Controls.TreeViewItem> può anche avere <xref:System.Windows.Controls.TreeViewItem> controlli come elementi figlio ed è possono definire tali elementi figlio tramite la <xref:System.Windows.Controls.ItemsControl.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-109">A <xref:System.Windows.Controls.TreeViewItem> can also have <xref:System.Windows.Controls.TreeViewItem> controls as its child elements and you can define these child elements by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="5ae5e-110">Nell'esempio seguente viene illustrato come definire in modo esplicito <xref:System.Windows.Controls.TreeViewItem> contenuto impostando le <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà da una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-110">The following example shows how to explicitly define <xref:System.Windows.Controls.TreeViewItem> content by setting the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property to a text string.</span></span>  
  
 [!code-xaml[TreeViewSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="5ae5e-111">Nell'esempio seguente mostra come definire gli elementi figlio di un <xref:System.Windows.Controls.TreeViewItem> definendo <xref:System.Windows.Controls.ItemsControl.Items%2A> che si trovano <xref:System.Windows.Controls.Button> controlli.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-111">The following example show how to define child elements of a <xref:System.Windows.Controls.TreeViewItem> by defining <xref:System.Windows.Controls.ItemsControl.Items%2A> that are <xref:System.Windows.Controls.Button> controls.</span></span>  
  
 [!code-xaml[TreeViewSimple#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 <span data-ttu-id="5ae5e-112">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.TreeView> in cui un' <xref:System.Windows.Data.XmlDataProvider> fornisce <xref:System.Windows.Controls.TreeViewItem> contenuto e un <xref:System.Windows.HierarchicalDataTemplate> definisce l'aspetto del contenuto.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-112">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where an <xref:System.Windows.Data.XmlDataProvider> provides <xref:System.Windows.Controls.TreeViewItem> content and a <xref:System.Windows.HierarchicalDataTemplate> defines the appearance of the content.</span></span>  
  
 [!code-xaml[TreeViewSimple#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 <span data-ttu-id="5ae5e-113">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.TreeView> in cui la <xref:System.Windows.Controls.TreeViewItem> contenuto contiene <xref:System.Windows.Controls.DockPanel> controlli contenuto incorporato.</span><span class="sxs-lookup"><span data-stu-id="5ae5e-113">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where the <xref:System.Windows.Controls.TreeViewItem> content contains <xref:System.Windows.Controls.DockPanel> controls that have embedded content.</span></span>  
  
 [!code-xaml[TreeViewSimple#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a><span data-ttu-id="5ae5e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ae5e-114">See also</span></span>
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="5ae5e-115">Panoramica sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="5ae5e-115">TreeView Overview</span></span>](../../../../docs/framework/wpf/controls/treeview-overview.md)
- [<span data-ttu-id="5ae5e-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="5ae5e-116">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
