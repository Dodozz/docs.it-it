---
title: 'Procedura: Disegnare una linea'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: c11dfb9523834ec2e622cb2e62bd6982a1a78fd4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143520"
---
# <a name="how-to-draw-a-line"></a>Procedura: Disegnare una linea
In questo esempio illustra come disegnare linee con il <xref:System.Windows.Shapes.Line> elemento.  
  
 Per disegnare una linea, creare un <xref:System.Windows.Shapes.Line> elemento. Usare relativi <xref:System.Windows.Shapes.Line.X1%2A> e <xref:System.Windows.Shapes.Line.Y1%2A> delle proprietà impostare il punto iniziale; e utilizzare relativo <xref:System.Windows.Shapes.Line.X2%2A> e <xref:System.Windows.Shapes.Line.Y2%2A> proprietà da impostare il punto finale. Infine, impostare relativi <xref:System.Windows.Shapes.Shape.Stroke%2A> e <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> perché non è visibile una riga senza un tratto.  
  
 L'impostazione di <xref:System.Windows.Shapes.Shape.Fill%2A> (elemento) per una riga non ha alcun effetto perché una riga non ha interno.  
  
 L'esempio seguente disegna tre righe all'interno di un <xref:System.Windows.Controls.Canvas> elemento.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Shapes.Line>
- [Esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037)
