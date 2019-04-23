---
title: "Procedura: Usare l'elemento Image"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 967159894e25721bdf380f851712e91d76088f87
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205303"
---
# <a name="how-to-use-the-image-element"></a>Procedura: Usare l'elemento Image
Questo esempio illustra come includere immagini in un'applicazione usando il <xref:System.Windows.Controls.Image> elemento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel. In questo esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], per definire l'immagine vengono usate sia la sintassi degli attributi e che la sintassi di tag di proprietà. Per altre informazioni sulla sintassi di attributo e di proprietà, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md). Oggetto <xref:System.Windows.Media.Imaging.BitmapImage> viene usato per definire i dati di origine dell'immagine e viene definito in modo esplicito per l'esempio di sintassi di tag di proprietà. Inoltre, il <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> del <xref:System.Windows.Media.Imaging.BitmapImage> è impostato per la stessa larghezza il <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Controls.Image>. In questo modo per il rendering dell'immagine viene usata la quantità minima di memoria.  
  
> [!NOTE]
>  In generale, se si desidera specificare le dimensioni di un'immagine di rendering, specificare solo il <xref:System.Windows.FrameworkElement.Width%2A> o il <xref:System.Windows.FrameworkElement.Height%2A> ma non entrambi. Se si specifica solo uno di questi oggetti, le proporzioni dell'immagine vengono mantenute. In caso contrario, l'immagine potrebbe apparire inaspettatamente allungata o distorta. Per controllare l'immagine del comportamento di adattamento, usare il <xref:System.Windows.Controls.Image.Stretch%2A> e <xref:System.Windows.Controls.Image.StretchDirection%2A> proprietà.  
  
> [!NOTE]
>  Quando si specifica la dimensione di un'immagine con uno <xref:System.Windows.FrameworkElement.Width%2A> oppure <xref:System.Windows.FrameworkElement.Height%2A>, è necessario impostare anche uno <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> alla rispettiva dimensione stessa.  
  
 Il <xref:System.Windows.Controls.Image.Stretch%2A> proprietà determina come l'origine dell'immagine viene adattata per riempire l'elemento image. Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Media.Stretch>.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel usando il codice.  
  
> [!NOTE]
>  L'impostazione <xref:System.Windows.Media.Imaging.BitmapImage> delle proprietà devono essere eseguite all'interno di un <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> e <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> blocco.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla creazione dell'immagine](../graphics-multimedia/imaging-overview.md)
