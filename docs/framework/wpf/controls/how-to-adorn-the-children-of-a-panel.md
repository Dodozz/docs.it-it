---
title: 'Procedura: Adornare gli elementi figlio di un oggetto Panel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: ae039243ded93eb2bc7f85f9f07fad1dbe0eac2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544978"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="0e08b-102">Procedura: Adornare gli elementi figlio di un oggetto Panel</span><span class="sxs-lookup"><span data-stu-id="0e08b-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="0e08b-103">Questo esempio illustra come associare programmaticamente uno strumento decorativo agli elementi figlio di un elemento specificato <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="0e08b-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e08b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e08b-104">Example</span></span>  
 <span data-ttu-id="0e08b-105">Per associare uno strumento decorativo agli elementi figlio di un <xref:System.Windows.Controls.Panel>, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="0e08b-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0e08b-106">Dichiarare una nuova <xref:System.Windows.Documents.AdornerLayer> oggetto e chiamare il `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> metodo per trovare un livello dello strumento decorativo per l'elemento cui figli rappresentino da decorare.</span><span class="sxs-lookup"><span data-stu-id="0e08b-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="0e08b-107">Enumerare gli elementi figlio dell'elemento padre e chiamata di <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare uno strumento decorativo a ogni elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="0e08b-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="0e08b-108">Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) per gli elementi figlio di un <xref:System.Windows.Controls.StackPanel> denominate *myStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="0e08b-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="0e08b-109">Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="0e08b-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e08b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e08b-110">See also</span></span>
- [<span data-ttu-id="0e08b-111">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="0e08b-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
