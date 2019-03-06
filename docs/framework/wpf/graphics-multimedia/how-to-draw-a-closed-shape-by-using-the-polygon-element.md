---
title: "Procedura: Disegnare una forma chiusa utilizzando l'elemento poligono"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 533c341e2fae528ec896bf38bafa13974af1d127
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360039"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Procedura: Disegnare una forma chiusa utilizzando l'elemento poligono
Questo esempio illustra come disegnare una forma chiusa utilizzando il <xref:System.Windows.Shapes.Polygon> elemento. Per disegnare una forma chiusa, creare un <xref:System.Windows.Shapes.Polygon> elemento e utilizzo relativi <xref:System.Windows.Shapes.Polygon.Points%2A> proprietà per specificare i vertici di una forma. Viene automaticamente tracciata una linea che connette il primo e ultimo punto. Infine, specificare una <xref:System.Windows.Shapes.Shape.Fill%2A>, un <xref:System.Windows.Shapes.Shape.Stroke%2A>, o entrambi.  
  
## <a name="example"></a>Esempio  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], le sintassi valide per i punti di sono un elenco delimitato da spazi di coppie di coordinate x e y separate da virgole.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Sebbene l'esempio Usa un' <xref:System.Windows.Controls.Canvas> per contenere i poligoni, è possibile usare gli elementi poligono (e tutti gli altri elementi forma) con qualsiasi <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> che supporta il contenuto non di testo.  
  
 In questo esempio fa parte di un esempio più esaustivo; per l'esempio completo, vedere [esempio di elementi forma](https://go.microsoft.com/fwlink/?LinkID=160037).
