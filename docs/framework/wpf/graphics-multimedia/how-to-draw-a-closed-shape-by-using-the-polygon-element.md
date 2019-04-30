---
title: "Procedura: Disegnare una forma chiusa usando l'elemento poligono"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 533c341e2fae528ec896bf38bafa13974af1d127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003236"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="b3492-102">Procedura: Disegnare una forma chiusa usando l'elemento poligono</span><span class="sxs-lookup"><span data-stu-id="b3492-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="b3492-103">Questo esempio illustra come disegnare una forma chiusa utilizzando il <xref:System.Windows.Shapes.Polygon> elemento.</span><span class="sxs-lookup"><span data-stu-id="b3492-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="b3492-104">Per disegnare una forma chiusa, creare un <xref:System.Windows.Shapes.Polygon> elemento e utilizzo relativi <xref:System.Windows.Shapes.Polygon.Points%2A> proprietà per specificare i vertici di una forma.</span><span class="sxs-lookup"><span data-stu-id="b3492-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="b3492-105">Viene automaticamente tracciata una linea che connette il primo e ultimo punto.</span><span class="sxs-lookup"><span data-stu-id="b3492-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="b3492-106">Infine, specificare una <xref:System.Windows.Shapes.Shape.Fill%2A>, un <xref:System.Windows.Shapes.Shape.Stroke%2A>, o entrambi.</span><span class="sxs-lookup"><span data-stu-id="b3492-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3492-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3492-107">Example</span></span>  
 <span data-ttu-id="b3492-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], le sintassi valide per i punti di sono un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="b3492-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="b3492-109">Sebbene l'esempio Usa un' <xref:System.Windows.Controls.Canvas> per contenere i poligoni, è possibile usare gli elementi poligono (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.</span><span class="sxs-lookup"><span data-stu-id="b3492-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="b3492-110">In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="b3492-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
