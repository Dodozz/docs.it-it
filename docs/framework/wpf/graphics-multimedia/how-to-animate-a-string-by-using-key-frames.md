---
title: 'Procedura: Animare una stringa utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 70c5766da2ea91f519756cb47b20d688b33253e0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356232"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Procedura: Animare una stringa utilizzando fotogrammi chiave
In questo esempio illustra come animare una stringa, che in questo esempio è il <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button> controllo, usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button>.  
  
 Tutti i fotogrammi chiave in questo esempio usano un'istanza di <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> classe perché un'animazione di stringa che viene creata con fotogrammi chiave può usare solo i fotogrammi chiave discreti. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> creano salti improvvisi tra valori, vale a dire le modifiche per l'animazione si verificano rapidamente e risultano immediatamente evidenti.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
