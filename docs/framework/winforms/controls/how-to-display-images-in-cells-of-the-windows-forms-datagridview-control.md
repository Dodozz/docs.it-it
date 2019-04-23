---
title: 'Procedura: Visualizzare immagini nelle celle del controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: 90aaff419ecc2c890a8b3802f3aaf12092febb73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082997"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="cda9f-102">Procedura: Visualizzare immagini nelle celle del controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cda9f-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cda9f-103">E un'immagine è uno dei valori che è possibile visualizzare in una riga di dati.</span><span class="sxs-lookup"><span data-stu-id="cda9f-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="cda9f-104">Spesso, questi elementi grafici assumono la forma della fotografia di un dipendente o un logo aziendale.</span><span class="sxs-lookup"><span data-stu-id="cda9f-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="cda9f-105">L'inserimento delle immagini è semplice quando si visualizzano i dati all'interno di <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="cda9f-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="cda9f-106">Il <xref:System.Windows.Forms.DataGridView> qualsiasi formato di immagine supportato da e gestisce in modo nativo il <xref:System.Drawing.Image> formato utilizzato da alcuni database dell'immagine di classe, nonché di OLE.</span><span class="sxs-lookup"><span data-stu-id="cda9f-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="cda9f-107">Se il <xref:System.Windows.Forms.DataGridView> origine dati del controllo ha una colonna di immagini, questi verranno visualizzati automaticamente dal <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="cda9f-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="cda9f-108">Esempio di codice seguente viene illustrato come estrarre un'icona da una risorsa incorporata e convertirlo in una bitmap da visualizzare in ogni cella della colonna di tipo image.</span><span class="sxs-lookup"><span data-stu-id="cda9f-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="cda9f-109">Per un altro esempio che sostituisce i valori delle celle testuali con immagini corrispondenti, vedere [come: Personalizzare la formattazione dei dati nel controllo DataGridView Windows Form](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="cda9f-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda9f-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="cda9f-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cda9f-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="cda9f-111">Compiling the Code</span></span>  
 <span data-ttu-id="cda9f-112">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cda9f-112">This example requires:</span></span>  
  
-   <span data-ttu-id="cda9f-113">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="cda9f-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="cda9f-114">Una risorsa icona incorporata denominata `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="cda9f-114">An embedded icon resource named `tree.ico`.</span></span>  
  
-   <span data-ttu-id="cda9f-115">Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cda9f-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda9f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cda9f-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="cda9f-117">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cda9f-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="cda9f-118">Procedura: Personalizzare la formattazione dei dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="cda9f-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
