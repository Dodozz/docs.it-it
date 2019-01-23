---
title: 'Procedura: Eseguire un hit test in un oggetto Viewport3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 0906fc0da363f9b4022eea863ec1140c8eeb2da2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494240"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a><span data-ttu-id="30530-102">Procedura: Eseguire un hit test in un oggetto Viewport3D</span><span class="sxs-lookup"><span data-stu-id="30530-102">How to: Hit Test in a Viewport3D</span></span>
<span data-ttu-id="30530-103">Questo esempio illustra come eseguire un hit test per gli oggetti visivi 3D in un <xref:System.Windows.Controls.Viewport3D>.</span><span class="sxs-lookup"><span data-stu-id="30530-103">This example shows how to hit test for 3D Visuals in a <xref:System.Windows.Controls.Viewport3D>.</span></span>  
  
 <span data-ttu-id="30530-104">Poiché <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> restituisce informazioni 2D e 3D, è possibile scorrere i risultati del test per leggere i risultati solo 3D.</span><span class="sxs-lookup"><span data-stu-id="30530-104">Because <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> returns 2D and 3D information, it is possible to iterate through the test results to read only 3D results.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <span data-ttu-id="30530-105">Il <xref:System.Windows.Media.HitTestResultBehavior> nel codice seguente determina come vengono elaborati i risultati dell'hit test.</span><span class="sxs-lookup"><span data-stu-id="30530-105">The <xref:System.Windows.Media.HitTestResultBehavior> in the following code determines how the hit test results are processed.</span></span>  <span data-ttu-id="30530-106">`UpdateResultInfo` e `UpdateMaterial` sono metodi definiti in locale.</span><span class="sxs-lookup"><span data-stu-id="30530-106">`UpdateResultInfo` and `UpdateMaterial` are locally defined methods.</span></span>  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a><span data-ttu-id="30530-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30530-107">See also</span></span>
- [<span data-ttu-id="30530-108">3D esempio di Hit Testing</span><span class="sxs-lookup"><span data-stu-id="30530-108">3-D Hit Testing Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159959)
