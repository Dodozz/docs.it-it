---
title: "Procedura: Aggiungere un'animazione a un oggetto EllipseGeometry"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], EllipseGeometry objects [WPF]
- EllipseGeometry objects [WPF], animating
- graphics [WPF], animation
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
ms.openlocfilehash: dd92de2cf32a11b81f991939b614a899a25ff4ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564994"
---
# <a name="how-to-animate-an-ellipsegeometry"></a>Procedura: Aggiungere un'animazione a un oggetto EllipseGeometry
In questo esempio illustra come animare un <xref:System.Windows.Media.Geometry> all'interno di un <xref:System.Windows.Shapes.Path> elemento. Nell'esempio seguente, un <xref:System.Windows.Media.Animation.PointAnimation> viene usato per animare la <xref:System.Windows.Media.EllipseGeometry.Center%2A> di un <xref:System.Windows.Media.EllipseGeometry>.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[animatepath_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Cenni preliminari sulle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
