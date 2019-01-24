---
title: "Procedura: Aggiungere un'animazione a una rotazione tridimensionale tramite quaternioni"
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: df51db324bffc038bc585b6d977a82d54feefb3b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550929"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="010f7-102">Procedura: Aggiungere un'animazione a una rotazione tridimensionale tramite quaternioni</span><span class="sxs-lookup"><span data-stu-id="010f7-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="010f7-103">In questo esempio illustra come animare una rotazione di un oggetto 3D tramite quaternioni.</span><span class="sxs-lookup"><span data-stu-id="010f7-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="010f7-104">Il codice seguente mostra una <xref:System.Windows.Media.Media3D.QuaternionRotation3D> utilizzato come valore per il <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> proprietà di un <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="010f7-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="010f7-105">Ciò <xref:System.Windows.Media.Media3D.QuaternionRotation3D> viene aggiunta un'animazione con una <xref:System.Windows.Media.Animation.QuaternionAnimation> all'interno di un <xref:System.Windows.Media.Animation.Storyboard> usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="010f7-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="010f7-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="010f7-106">Example</span></span>  
 <span data-ttu-id="010f7-107">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="010f7-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="010f7-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="010f7-108">See also</span></span>
- [<span data-ttu-id="010f7-109">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="010f7-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="010f7-110">Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="010f7-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="010f7-111">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="010f7-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="010f7-112">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="010f7-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [<span data-ttu-id="010f7-113">Animare una rotazione tridimensionale usando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="010f7-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="010f7-114">Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="010f7-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
