---
title: "Procedura: Disegnare un'area con una sfumatura radiale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: c3bcc11dea4b1f223f629415591ab03588881dde
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379783"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="4a946-102">Procedura: Disegnare un'area con una sfumatura radiale</span><span class="sxs-lookup"><span data-stu-id="4a946-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="4a946-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.RadialGradientBrush> classe disegnare un'area con una sfumatura radiale.</span><span class="sxs-lookup"><span data-stu-id="4a946-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a946-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a946-104">Example</span></span>  
 <span data-ttu-id="4a946-105">L'esempio seguente usa un <xref:System.Windows.Media.RadialGradientBrush> per disegnare un rettangolo con una sfumatura radiale che effettua la transizione da giallo a rosso a blu al verde limone.</span><span class="sxs-lookup"><span data-stu-id="4a946-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="4a946-106">Nella figura seguente illustra la sfumatura dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="4a946-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="4a946-107">È stata evidenziata della sfumatura.</span><span class="sxs-lookup"><span data-stu-id="4a946-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="4a946-108">![Cursori sfumatura in una sfumatura radiale](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="4a946-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a946-109">Gli esempi in questo argomento usano il sistema di coordinate predefinito per l'impostazione di punti di controllo.</span><span class="sxs-lookup"><span data-stu-id="4a946-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="4a946-110">Il sistema di coordinate è relativo a un rettangolo: 0 indica lo 0% del rettangolo di selezione, mentre 1 indica il 100% del rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="4a946-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="4a946-111">È possibile modificare il sistema di coordinate impostando il <xref:System.Windows.Media.GradientBrush.MappingMode%2A> il valore della proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="4a946-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="4a946-112">Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione.</span><span class="sxs-lookup"><span data-stu-id="4a946-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="4a946-113">I valori vengono interpretati direttamente nello spazio locale.</span><span class="sxs-lookup"><span data-stu-id="4a946-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="4a946-114">Per ulteriori <xref:System.Windows.Media.RadialGradientBrush> esempi, vedere la [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="4a946-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="4a946-115">Per altre informazioni su sfumature e altri tipi di pennelli, vedere [disegno con colori a tinta unita e sfumature Panoramica](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4a946-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
