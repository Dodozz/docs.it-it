---
title: 'Procedura: Impostare il colore di un oggetto Pen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: ee2d3f8cdf6dd10ca2a9ff0dd3e66b164c84f21b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637007"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="c63d4-102">Procedura: Impostare il colore di un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="c63d4-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="c63d4-103">Questo esempio viene modificato il colore di un preesistenti <xref:System.Drawing.Pen> oggetto</span><span class="sxs-lookup"><span data-stu-id="c63d4-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="c63d4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c63d4-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c63d4-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c63d4-105">Compiling the Code</span></span>  
 <span data-ttu-id="c63d4-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c63d4-106">This example requires:</span></span>  
  
- <span data-ttu-id="c63d4-107">Oggetto <xref:System.Drawing.Pen> oggetto denominato `myPen`.</span><span class="sxs-lookup"><span data-stu-id="c63d4-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c63d4-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c63d4-108">Robust Programming</span></span>  
 <span data-ttu-id="c63d4-109">È necessario chiamare <xref:System.Drawing.Pen.Dispose%2A> sugli oggetti che utilizzano le risorse di sistema (ad esempio <xref:System.Drawing.Pen> oggetti) al termine del loro utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c63d4-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c63d4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c63d4-110">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="c63d4-111">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="c63d4-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="c63d4-112">Procedura: Creare un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="c63d4-112">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="c63d4-113">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="c63d4-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="c63d4-114">Penne, linee e rettangoli in GDI+</span><span class="sxs-lookup"><span data-stu-id="c63d4-114">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
