---
title: 'Procedura: Creare un arco ellittico'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: aae304b9963f3a8e5833b4d8ba0a54777a750225
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003366"
---
# <a name="how-to-create-an-elliptical-arc"></a>Procedura: Creare un arco ellittico
In questo esempio illustra come disegnare un arco ellittico. Per creare un arco ellittico, usare il <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, e <xref:System.Windows.Media.ArcSegment> classi.  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti, viene disegnato un arco ellittico da (10, 100) a (200,100). Ha l'arco un <xref:System.Windows.Media.ArcSegment.Size%2A> di 100 per 50 pixel indipendenti dal dispositivo, un <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> di 45 gradi, un <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> impostazione `true`e un <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> di <xref:System.Windows.Media.SweepDirection.Counterclockwise>.  
  
 [xaml]  
  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile usare la sintassi degli attributi per descrivere un tracciato.  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 [xaml]  
  
 (Si noti che questa sintassi di attributo crea effettivamente una <xref:System.Windows.Media.StreamGeometry>, una versione leggera di una <xref:System.Windows.Media.PathGeometry>. Per altre informazioni, vedere la pagina [Sintassi di markup del tracciato](path-markup-syntax.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile disegnare un arco ellittico in modo esplicito usando tag di oggetti. Di seguito è equivalente al precedente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Questo esempio fa parte di un esempio più esaustivo. Per l'esempio completo, vedere la [esempio di geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).  
  
## <a name="see-also"></a>Vedere anche

- [Creare una curva di Bézier quadratica](how-to-create-a-quadratic-bezier-curve.md)
- [Creare una curva di Bézier cubica](how-to-create-a-cubic-bezier-curve.md)
