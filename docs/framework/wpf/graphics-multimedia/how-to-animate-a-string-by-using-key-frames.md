---
title: "Procedura: Aggiungere un'animazione a una stringa usando fotogrammi chiave"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 4a37408ad90fda12a95e66c1b44018967b376837
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204172"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="4900d-102">Procedura: Aggiungere un'animazione a una stringa usando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="4900d-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="4900d-103">In questo esempio illustra come animare una stringa, che in questo esempio è il <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button> controllo, usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="4900d-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4900d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4900d-104">Example</span></span>  
 <span data-ttu-id="4900d-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="4900d-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="4900d-106">Tutti i fotogrammi chiave in questo esempio usano un'istanza di <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> classe perché un'animazione di stringa che viene creata con fotogrammi chiave può usare solo i fotogrammi chiave discreti.</span><span class="sxs-lookup"><span data-stu-id="4900d-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="4900d-107">Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> creano salti improvvisi tra valori, vale a dire le modifiche per l'animazione si verificano rapidamente e risultano immediatamente evidenti.</span><span class="sxs-lookup"><span data-stu-id="4900d-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="4900d-108">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="4900d-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4900d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4900d-109">See also</span></span>

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="4900d-110">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="4900d-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="4900d-111">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="4900d-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
