---
title: 'Procedura: Convertire un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 75b8f72647b1597396fde5d21f8378d3ce586a25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672873"
---
# <a name="how-to-translate-an-element"></a>Procedura: Convertire un elemento
In questo esempio viene illustrato come traslare (spostare) un elemento utilizzando un <xref:System.Windows.Media.TranslateTransform>.  
  
 Il <xref:System.Windows.Media.TranslateTransform> classe è particolarmente utile per spostare elementi all'interno di pannelli che non supportano il posizionamento assoluto. Ad esempio, applicando una <xref:System.Windows.Media.TranslateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un elemento, è possibile spostare un elemento all'interno di un <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel>.  
  
 Usare la <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà del <xref:System.Windows.Media.TranslateTransform> per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse x. Usare il <xref:System.Windows.Media.TranslateTransform.Y%2A> proprietà per specificare la quantità, in pixel, per spostare l'elemento lungo l'asse y. Infine, applicare il <xref:System.Windows.Media.TranslateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.  
  
 L'esempio seguente usa un <xref:System.Windows.Media.TranslateTransform> per spostare un pixel elemento 50 a destra e 50 pixel in basso.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
