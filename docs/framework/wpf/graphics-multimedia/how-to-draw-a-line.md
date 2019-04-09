---
title: 'Procedura: Disegnare una linea'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: c11dfb9523834ec2e622cb2e62bd6982a1a78fd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143520"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="7ace2-102">Procedura: Disegnare una linea</span><span class="sxs-lookup"><span data-stu-id="7ace2-102">How to: Draw a Line</span></span>
<span data-ttu-id="7ace2-103">In questo esempio illustra come disegnare linee con il <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="7ace2-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="7ace2-104">Per disegnare una linea, creare un <xref:System.Windows.Shapes.Line> elemento.</span><span class="sxs-lookup"><span data-stu-id="7ace2-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="7ace2-105">Usare relativi <xref:System.Windows.Shapes.Line.X1%2A> e <xref:System.Windows.Shapes.Line.Y1%2A> delle proprietà impostare il punto iniziale; e utilizzare relativo <xref:System.Windows.Shapes.Line.X2%2A> e <xref:System.Windows.Shapes.Line.Y2%2A> proprietà da impostare il punto finale.</span><span class="sxs-lookup"><span data-stu-id="7ace2-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="7ace2-106">Infine, impostare relativi <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> perché non è visibile una riga senza un tratto.</span><span class="sxs-lookup"><span data-stu-id="7ace2-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="7ace2-107">L'impostazione di <xref:System.Windows.Shapes.Shape.Fill%2A> (elemento) per una riga non ha alcun effetto perché una riga non ha interno.</span><span class="sxs-lookup"><span data-stu-id="7ace2-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="7ace2-108">L'esempio seguente disegna tre righe all'interno di un <xref:System.Windows.Controls.Canvas> elemento.</span><span class="sxs-lookup"><span data-stu-id="7ace2-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ace2-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ace2-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="7ace2-110">In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="7ace2-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ace2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ace2-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="7ace2-112">Esempio di elementi forma</span><span class="sxs-lookup"><span data-stu-id="7ace2-112">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
