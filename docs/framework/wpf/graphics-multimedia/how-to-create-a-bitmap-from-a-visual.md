---
title: 'Procedura: Creare una bitmap da un oggetto visivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: a622d99f7c477f8654526ed399f1eb37288682fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189887"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a><span data-ttu-id="1e276-102">Procedura: Creare una bitmap da un oggetto visivo</span><span class="sxs-lookup"><span data-stu-id="1e276-102">How to: Create a Bitmap from a Visual</span></span>
<span data-ttu-id="1e276-103">Questo esempio viene illustrato come creare una bitmap da un <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="1e276-103">This example shows how you can create a bitmap from a <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="1e276-104">Oggetto <xref:System.Windows.Media.DrawingVisual> viene eseguito il rendering con <xref:System.Windows.Media.FormattedText>.</span><span class="sxs-lookup"><span data-stu-id="1e276-104">A <xref:System.Windows.Media.DrawingVisual> is rendered with <xref:System.Windows.Media.FormattedText>.</span></span> <span data-ttu-id="1e276-105">Il <xref:System.Windows.Media.Visual> viene quindi eseguito il rendering di <xref:System.Windows.Media.Imaging.RenderTargetBitmap> crea una bitmap del testo specificato.</span><span class="sxs-lookup"><span data-stu-id="1e276-105">The <xref:System.Windows.Media.Visual> is then rendered to the <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creating a bitmap of the given text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e276-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e276-106">Example</span></span>  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a><span data-ttu-id="1e276-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e276-107">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="1e276-108">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="1e276-108">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="1e276-109">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="1e276-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="1e276-110">Uso degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="1e276-110">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
