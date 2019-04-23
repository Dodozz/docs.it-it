---
title: 'Procedura: Creare una curva di Bézier cubica'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: 36544abc774b7fe82c2ff47483cfedd6fb13e344
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115570"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="1de4b-102">Procedura: Creare una curva di Bézier cubica</span><span class="sxs-lookup"><span data-stu-id="1de4b-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="1de4b-103">In questo esempio viene illustrato come creare una curva di Bézier cubica.</span><span class="sxs-lookup"><span data-stu-id="1de4b-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="1de4b-104">Per creare una curva di Bézier cubica continua, usare il <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.BezierSegment> classi.</span><span class="sxs-lookup"><span data-stu-id="1de4b-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="1de4b-105">Per visualizzare la geometria risulta, usare una <xref:System.Windows.Shapes.Path> elemento, o usarlo con un <xref:System.Windows.Media.GeometryDrawing> o un <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="1de4b-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="1de4b-106">Negli esempi seguenti, una curva di Bézier cubica viene disegnata da (10, 100) a (300, 100).</span><span class="sxs-lookup"><span data-stu-id="1de4b-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="1de4b-107">La curva ha punti di controllo di (100, 0) e (200, 200).</span><span class="sxs-lookup"><span data-stu-id="1de4b-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de4b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="1de4b-108">Example</span></span>  
 <span data-ttu-id="1de4b-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="1de4b-109">[xaml]</span></span>  
  
 <span data-ttu-id="1de4b-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile utilizzare la sintassi di markup abbreviato per descrivere un tracciato.</span><span class="sxs-lookup"><span data-stu-id="1de4b-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="1de4b-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="1de4b-111">[xaml]</span></span>  
  
 <span data-ttu-id="1de4b-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile disegnare una curva di Bézier cubica con il tag object.</span><span class="sxs-lookup"><span data-stu-id="1de4b-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="1de4b-113">L'esempio che segue equivale a quello [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] precedente.</span><span class="sxs-lookup"><span data-stu-id="1de4b-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="1de4b-114">Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la pagina [Geometries Sample (esempio di geometrie)](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="1de4b-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de4b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1de4b-115">See also</span></span>

- [<span data-ttu-id="1de4b-116">Creare un arco ellittico</span><span class="sxs-lookup"><span data-stu-id="1de4b-116">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="1de4b-117">Creare un oggetto LineSegment in un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="1de4b-117">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="1de4b-118">Creare una curva di Bézier cubica</span><span class="sxs-lookup"><span data-stu-id="1de4b-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="1de4b-119">Creare una curva di Bézier quadratica</span><span class="sxs-lookup"><span data-stu-id="1de4b-119">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
