---
title: 'Procedura: Applicare la correzione gamma a una sfumatura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: 7290b7901714e9b71bda3f85f930f5331b8fd4ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077329"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="4d6af-102">Procedura: Applicare la correzione gamma a una sfumatura</span><span class="sxs-lookup"><span data-stu-id="4d6af-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="4d6af-103">È possibile abilitare la correzione gamma per un pennello sfumato lineare impostando la proprietà del pennello <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="4d6af-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="4d6af-104">È possibile disabilitare la correzione gamma impostando il <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="4d6af-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="4d6af-105">La correzione gamma è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4d6af-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d6af-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d6af-106">Example</span></span>  
 <span data-ttu-id="4d6af-107">L'esempio crea un pennello sfumato lineare e tale utilizzato per riempire i due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="4d6af-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="4d6af-108">Il primo rettangolo viene riempito senza la correzione gamma e il secondo rettangolo viene riempito con la correzione gamma.</span><span class="sxs-lookup"><span data-stu-id="4d6af-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="4d6af-109">La figura seguente mostra i due rettangoli colorati.</span><span class="sxs-lookup"><span data-stu-id="4d6af-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="4d6af-110">Il rettangolo superiore che non dispone di correzione gamma, viene visualizzato scuro al centro.</span><span class="sxs-lookup"><span data-stu-id="4d6af-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="4d6af-111">Il rettangolo nella parte inferiore che include la correzione gamma, sembra avere ulteriori intensità uniforme.</span><span class="sxs-lookup"><span data-stu-id="4d6af-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="4d6af-112">![Sfumatura](./media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="4d6af-112">![Gradient](./media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d6af-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4d6af-113">Compiling the Code</span></span>  
 <span data-ttu-id="4d6af-114">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4d6af-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6af-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d6af-115">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [<span data-ttu-id="4d6af-116">Utilizzo di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="4d6af-116">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
