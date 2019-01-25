---
title: 'Procedura: Animare una stringa utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 4cadc1e7e4b7ee70e3a71ddaf433327a7561125d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670833"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="ee084-102">Procedura: Animare una stringa utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="ee084-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="ee084-103">In questo esempio illustra come animare una stringa, che in questo esempio è il <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button> controllo, usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="ee084-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee084-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee084-104">Example</span></span>  
 <span data-ttu-id="ee084-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="ee084-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="ee084-106">Tutti i fotogrammi chiave in questo esempio usano un'istanza di <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> classe perché un'animazione di stringa che viene creata con fotogrammi chiave può usare solo i fotogrammi chiave discreti.</span><span class="sxs-lookup"><span data-stu-id="ee084-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="ee084-107">Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> creano salti improvvisi tra valori, vale a dire le modifiche per l'animazione si verificano rapidamente e risultano immediatamente evidenti.</span><span class="sxs-lookup"><span data-stu-id="ee084-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="ee084-108">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="ee084-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee084-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee084-109">See also</span></span>
- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="ee084-110">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="ee084-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="ee084-111">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="ee084-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
