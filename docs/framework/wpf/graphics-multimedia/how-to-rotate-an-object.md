---
title: 'Procedura: Ruotare un oggetto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: d1c4700a5dc8f6ed99043552999d8f014116da8f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189665"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="bf1ba-102">Procedura: Ruotare un oggetto</span><span class="sxs-lookup"><span data-stu-id="bf1ba-102">How to: Rotate an Object</span></span>
<span data-ttu-id="bf1ba-103">Questo esempio spiega come ruotare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="bf1ba-104">Nell'esempio viene creata una <xref:System.Windows.Media.RotateTransform> e quindi specifica relativa <xref:System.Windows.Media.RotateTransform.Angle%2A> espresso in gradi.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="bf1ba-105">L'esempio seguente ruota un <xref:System.Windows.Shapes.Polyline> 45 gradi rispetto all'angolo superiore sinistro dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf1ba-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf1ba-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="bf1ba-107">Il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> delle proprietà del <xref:System.Windows.Media.RotateTransform> specificare il punto in cui viene ruotato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="bf1ba-108">Il punto centrale viene espresso nello spazio delle coordinate dell'elemento trasformato.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="bf1ba-109">Per impostazione predefinita, la rotazione viene applicata a (0,0), ovvero l'angolo superiore sinistro dell'oggetto da trasformare.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="bf1ba-110">L'esempio seguente ruota un <xref:System.Windows.Shapes.Polyline> oggetto in senso orario 45 gradi intorno al punto (25,50).</span><span class="sxs-lookup"><span data-stu-id="bf1ba-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="bf1ba-111">La figura seguente mostra il risultato ottenuto applicando una <xref:System.Windows.Media.Transform> ai due oggetti.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="bf1ba-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="bf1ba-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="bf1ba-113">Due oggetti che ruotano di 45 gradi da centri di rotazione diversi</span><span class="sxs-lookup"><span data-stu-id="bf1ba-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="bf1ba-114">Il <xref:System.Windows.Shapes.Polyline> negli esempi precedenti è un <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="bf1ba-115">Quando si applica una <xref:System.Windows.Media.Transform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un <xref:System.Windows.UIElement>, è possibile usare i <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà per specificare un'origine per ogni <xref:System.Windows.Media.Transform> che applicano all'elemento.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="bf1ba-116">Poiché il <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà utilizza coordinate relative, è possibile applicare una trasformazione al centro dell'elemento, anche se non si conosce la dimensione.</span><span class="sxs-lookup"><span data-stu-id="bf1ba-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="bf1ba-117">Per altre informazioni e per un esempio, vedere [specificare l'origine di una trasformazione utilizzando valori relativi](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span><span class="sxs-lookup"><span data-stu-id="bf1ba-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="bf1ba-118">Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="bf1ba-118">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf1ba-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf1ba-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="bf1ba-120">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="bf1ba-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="bf1ba-121">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="bf1ba-121">How-to Topics</span></span>](transformations-how-to-topics.md)
