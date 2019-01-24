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
# <a name="how-to-animate-an-ellipsegeometry"></a><span data-ttu-id="54cf5-102">Procedura: Aggiungere un'animazione a un oggetto EllipseGeometry</span><span class="sxs-lookup"><span data-stu-id="54cf5-102">How to: Animate an EllipseGeometry</span></span>
<span data-ttu-id="54cf5-103">In questo esempio illustra come animare un <xref:System.Windows.Media.Geometry> all'interno di un <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="54cf5-103">This example shows how to animate a <xref:System.Windows.Media.Geometry> within a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="54cf5-104">Nell'esempio seguente, un <xref:System.Windows.Media.Animation.PointAnimation> viene usato per animare la <xref:System.Windows.Media.EllipseGeometry.Center%2A> di un <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="54cf5-104">In the following example, a <xref:System.Windows.Media.Animation.PointAnimation> is used to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> of an <xref:System.Windows.Media.EllipseGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54cf5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="54cf5-105">Example</span></span>  
 [!code-xaml[animatepath_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="54cf5-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54cf5-106">See also</span></span>
- [<span data-ttu-id="54cf5-107">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="54cf5-107">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="54cf5-108">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="54cf5-108">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
