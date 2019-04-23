---
title: "Procedura: Aggiungere un'animazione alle conversioni tridimensionali"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 3e27c2d5f0cd44235a1d897b1b8f057808ae6bd8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168272"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="9552b-102">Procedura: Aggiungere un'animazione alle conversioni tridimensionali</span><span class="sxs-lookup"><span data-stu-id="9552b-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="9552b-103">In questo argomento viene illustrato come aggiungere un'animazione a una trasformazione di traslazione impostata su un [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modello.</span><span class="sxs-lookup"><span data-stu-id="9552b-103">This topic demonstrates how to animate a translation transformation set on a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="9552b-104">Il codice seguente viene illustrata l'applicazione di un <xref:System.Windows.Media.Media3D.TranslateTransform3D> dell'oggetto per il <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> proprietà di un <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="9552b-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="9552b-105">Il <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> proprietà di questo oggetto <xref:System.Windows.Media.Media3D.TranslateTransform3D> oggetto animato usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9552b-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="9552b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9552b-106">Example</span></span>  
 <span data-ttu-id="9552b-107">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="9552b-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9552b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9552b-108">See also</span></span>

- [<span data-ttu-id="9552b-109">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="9552b-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="9552b-110">Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="9552b-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="9552b-111">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="9552b-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="9552b-112">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="9552b-112">Transforms Overview</span></span>](transforms-overview.md)
