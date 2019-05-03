---
title: "Procedura: Aggiungere un'animazione al colore usando fotogrammi chiave"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: e579c4beb757ccf58eb1b9ca1f3852a5b96cac1a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010026"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Procedura: Aggiungere un'animazione al colore usando fotogrammi chiave
In questo esempio illustra come animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> usando fotogrammi chiave.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà di un <xref:System.Windows.Media.SolidColorBrush>. Questa animazione usa tre fotogrammi chiave nel modo seguente:  
  
1. Durante i primi due secondi, viene utilizzata un'istanza di <xref:System.Windows.Media.Animation.LinearColorKeyFrame> classe a modificare gradualmente il colore da verde a rosso. Fotogrammi chiave lineari come <xref:System.Windows.Media.Animation.LinearColorKeyFrame> creano una transizione lineare uniforme tra i valori.  
  
2. Alla fine del successivo mezzo secondo viene usata un'istanza del <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> classe per modificare rapidamente il colore da rosso a giallo. Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> creano cambiamenti improvvisi tra valori, vale a dire, la modifica di colore in questa parte dell'animazione eseguite più rapidamente e risulta immediatamente evidente.  
  
3. I due secondi finali viene usata un'istanza del <xref:System.Windows.Media.Animation.SplineColorKeyFrame> classe modificare nuovamente il colore, questa volta da giallo a verde. Ad esempio i fotogrammi chiave spline <xref:System.Windows.Media.Animation.SplineColorKeyFrame> creano una transizione variabile tra i valori a seconda dei valori del <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> proprietà. In questo esempio, il cambio di colore inizia lentamente, quindi accelera in modo esponenziale verso la fine del segmento temporale.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
