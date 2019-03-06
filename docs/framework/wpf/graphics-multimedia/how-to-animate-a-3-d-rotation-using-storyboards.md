---
title: 'Procedura: Animare una rotazione tridimensionale utilizzando gli storyboard'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 20f5bf565ded624e4ea7e1e615f09b4c698526bd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357222"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a><span data-ttu-id="dfe32-102">Procedura: Animare una rotazione tridimensionale utilizzando gli storyboard</span><span class="sxs-lookup"><span data-stu-id="dfe32-102">How to: Animate a 3-D Rotation Using Storyboards</span></span>
<span data-ttu-id="dfe32-103">Nell'esempio seguente viene illustrato come far ruotare un oggetto 3D mentre "asse" animando la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> e <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> delle proprietà di un <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto.</span><span class="sxs-lookup"><span data-stu-id="dfe32-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="dfe32-104">Ciò <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> oggetto specifica la trasformazione di rotazione dell'oggetto 3D e l'animazione delle proprietà consente l'effetto di rotazione desiderato.</span><span class="sxs-lookup"><span data-stu-id="dfe32-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="dfe32-105">All'interno dello Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> viene usato per animare la <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> proprietà durante <xref:System.Windows.Media.Animation.Vector3DAnimation> viene usato per animare il <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="dfe32-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfe32-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfe32-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="dfe32-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfe32-107">See also</span></span>
- [<span data-ttu-id="dfe32-108">Aggiungere un'animazione a una rotazione tridimensionale usando Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="dfe32-108">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="dfe32-109">Animare a una rotazione tridimensionale usando i fotogrammi chiave (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="dfe32-109">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="dfe32-110">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="dfe32-110">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="dfe32-111">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="dfe32-111">Storyboards Overview</span></span>](storyboards-overview.md)
