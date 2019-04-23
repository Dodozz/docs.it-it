---
title: "Procedura: Gestire l'evento MouseDoubleClick per ciascun elemento di ListView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 443e5c620ef5bf240d3e317f0234aac0b29b456f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145080"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="d4f4b-102">Procedura: Gestire l'evento MouseDoubleClick per ciascun elemento di ListView</span><span class="sxs-lookup"><span data-stu-id="d4f4b-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="d4f4b-103">Per gestire un evento per un elemento in un <xref:System.Windows.Controls.ListView>, è necessario aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="d4f4b-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="d4f4b-104">Quando un <xref:System.Windows.Controls.ListView> è associato a un'origine dati, è necessario creare in modo esplicito un <xref:System.Windows.Controls.ListViewItem>, ma è possibile gestire l'evento per ogni elemento tramite l'aggiunta di un <xref:System.Windows.EventSetter> a uno stile di un <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="d4f4b-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4f4b-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4f4b-105">Example</span></span>  
 <span data-ttu-id="d4f4b-106">L'esempio seguente crea un'associazione a dati <xref:System.Windows.Controls.ListView> e crea un' <xref:System.Windows.Style> per aggiungere un gestore eventi a ogni <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="d4f4b-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="d4f4b-107">L'esempio seguente viene gestito il <xref:System.Windows.Controls.Control.MouseDoubleClick> evento.</span><span class="sxs-lookup"><span data-stu-id="d4f4b-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="d4f4b-108">Sebbene sia più comune per associare un <xref:System.Windows.Controls.ListView> a un'origine dati, è possibile usare uno stile per aggiungere un gestore eventi per ognuno <xref:System.Windows.Controls.ListViewItem> in un'associazione di dati non <xref:System.Windows.Controls.ListView> indipendentemente dal fatto che crea in modo esplicito un <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="d4f4b-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="d4f4b-109">Per altre informazioni sulle creati in modo esplicito e in modo implicito <xref:System.Windows.Controls.ListViewItem> controlli, vedere <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="d4f4b-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f4b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4f4b-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="d4f4b-111">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="d4f4b-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="d4f4b-112">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="d4f4b-112">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="d4f4b-113">Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath</span><span class="sxs-lookup"><span data-stu-id="d4f4b-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="d4f4b-114">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="d4f4b-114">ListView Overview</span></span>](listview-overview.md)
