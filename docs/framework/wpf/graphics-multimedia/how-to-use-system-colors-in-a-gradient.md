---
title: 'Procedura: Usare i colori di sistema in una sfumatura'
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 55c99640907a0c372f8c7bbc50b9b45c9f15ef3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769239"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="a8b4d-102">Procedura: Usare i colori di sistema in una sfumatura</span><span class="sxs-lookup"><span data-stu-id="a8b4d-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="a8b4d-103">Per usare un colore di sistema in una sfumatura, si utilizza il  *\<SystemColor >* colore e  *\<SystemColor >* ColorKey proprietà statiche del <xref:System.Windows.SystemColors> classe per ottenere una riferimento al colore, dove  *\<SystemColor >* è il nome del colore di sistema desiderato.</span><span class="sxs-lookup"><span data-stu-id="a8b4d-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="a8b4d-104">Usare la  *\<SystemColor >* ColorKey proprietà quando si desidera creare un riferimento dinamico che viene aggiornato automaticamente quando cambia il tema del sistema.</span><span class="sxs-lookup"><span data-stu-id="a8b4d-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="a8b4d-105">In caso contrario, usare il  *\<SystemColor >* proprietà dei colori.</span><span class="sxs-lookup"><span data-stu-id="a8b4d-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8b4d-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8b4d-106">Example</span></span>  
 <span data-ttu-id="a8b4d-107">L'esempio seguente usa risorse di colore di sistema dinamiche per creare una sfumatura.</span><span class="sxs-lookup"><span data-stu-id="a8b4d-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="a8b4d-108">L'esempio seguente usa risorse di colore di sistema statiche per creare una sfumatura.</span><span class="sxs-lookup"><span data-stu-id="a8b4d-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a8b4d-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8b4d-109">See also</span></span>

- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="a8b4d-110">Disegnare un'area con un pennello di sistema</span><span class="sxs-lookup"><span data-stu-id="a8b4d-110">Paint an Area with a System Brush</span></span>](how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="a8b4d-111">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="a8b4d-111">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
