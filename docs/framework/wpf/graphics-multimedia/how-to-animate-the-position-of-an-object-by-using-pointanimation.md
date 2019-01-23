---
title: 'Procedura: Animare la posizione di un oggetto utilizzando PointAnimation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: e359e712f533c861a694c53848ca0eaeb289eb21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495553"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="b00a4-102">Procedura: Animare la posizione di un oggetto utilizzando PointAnimation</span><span class="sxs-lookup"><span data-stu-id="b00a4-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="b00a4-103">Questo esempio illustra come usare il <xref:System.Windows.Media.Animation.PointAnimation> classe per animare un oggetto lungo un <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="b00a4-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b00a4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b00a4-104">Example</span></span>  
 <span data-ttu-id="b00a4-105">L'esempio seguente sposta un'ellisse un <xref:System.Windows.Shapes.Path> da un punto dello schermo a un altro.</span><span class="sxs-lookup"><span data-stu-id="b00a4-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="b00a4-106">Nell'esempio viene animata la posizione di un <xref:System.Windows.Media.EllipseGeometry> usando <xref:System.Windows.Media.Animation.PointAnimation> per aggiungere un'animazione la <xref:System.Windows.Media.EllipseGeometry.Center%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b00a4-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b00a4-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b00a4-107">See also</span></span>
- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [<span data-ttu-id="b00a4-108">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="b00a4-108">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="b00a4-109">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="b00a4-109">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [<span data-ttu-id="b00a4-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b00a4-110">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)
- [<span data-ttu-id="b00a4-111">Animazione e temporizzazione</span><span class="sxs-lookup"><span data-stu-id="b00a4-111">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [<span data-ttu-id="b00a4-112">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b00a4-112">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
