---
title: Formattazione e stile di base nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: 5e967c1bbe54095cc11e48b014600158da7fe6a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189890"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="27d5f-102">Formattazione e stile di base nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="27d5f-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="27d5f-103">Il `DataGridView` controllo rende più semplice definire l'aspetto di base di celle e la formattazione dei valori delle celle.</span><span class="sxs-lookup"><span data-stu-id="27d5f-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="27d5f-104">È possibile definire l'aspetto e impostando le proprietà di formattazione stili per le singole celle, per le celle delle righe e colonne specifiche o per tutte le celle nel controllo di `DataGridViewCellStyle` oggetti accessibili tramite diversi `DataGridView` proprietà del controllo.</span><span class="sxs-lookup"><span data-stu-id="27d5f-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="27d5f-105">Inoltre, è possibile modificare questi stili dinamicamente in base ai fattori quali il valore di cella tramite la gestione di `CellFormatting` evento.</span><span class="sxs-lookup"><span data-stu-id="27d5f-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27d5f-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="27d5f-106">In This Section</span></span>  
 [<span data-ttu-id="27d5f-107">Procedura: Modificare gli stili dei bordi e delle linee della griglia nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27d5f-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="27d5f-108">Viene descritto come impostare `DataGridView` le proprietà che definiscono l'aspetto del bordo del controllo e linee di separazione tra le celle.</span><span class="sxs-lookup"><span data-stu-id="27d5f-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="27d5f-109">Stili della cella nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="27d5f-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27d5f-110">Viene descritto il `DataGridViewCellStyle` classe e la proprietà di quel tipo di interazione per definire la visualizzazione delle celle nel controllo.</span><span class="sxs-lookup"><span data-stu-id="27d5f-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="27d5f-111">Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27d5f-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27d5f-112">Viene descritto come utilizzare `DataGridViewCellStyle` proprietà per definire l'aspetto predefinito di celle in righe e colonne specifiche e in tutto il controllo.</span><span class="sxs-lookup"><span data-stu-id="27d5f-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="27d5f-113">Procedura: Formattare i dati nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27d5f-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27d5f-114">Viene descritto come formattare i valori visualizzati nelle celle utilizzando `DataGridViewCellStyle` proprietà.</span><span class="sxs-lookup"><span data-stu-id="27d5f-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="27d5f-115">Procedura: Impostare gli stili di carattere e colore nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27d5f-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27d5f-116">Viene descritto come utilizzare il `DefaultCellStyle` proprietà da impostare base Visualizza caratteristiche per tutte le celle nel controllo.</span><span class="sxs-lookup"><span data-stu-id="27d5f-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="27d5f-117">Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27d5f-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27d5f-118">Viene descritto come creare un effetto simile al ledger del controllo utilizzando le righe alterne che vengono visualizzate in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="27d5f-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="27d5f-119">Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27d5f-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="27d5f-120">Viene descritto come utilizzare il `RowTemplate` proprietà per impostare le proprietà di riga che verranno usate per tutte le righe nel controllo.</span><span class="sxs-lookup"><span data-stu-id="27d5f-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="27d5f-121">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="27d5f-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="27d5f-122">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="27d5f-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="27d5f-123">Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridViewCellStyle> classe.</span><span class="sxs-lookup"><span data-stu-id="27d5f-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="27d5f-124">Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento.</span><span class="sxs-lookup"><span data-stu-id="27d5f-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="27d5f-125">Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="27d5f-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="27d5f-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="27d5f-126">Related Sections</span></span>  
 [<span data-ttu-id="27d5f-127">Personalizzazione del controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="27d5f-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="27d5f-128">Fornisce argomenti che descrivono come disegnare celle e righe personalizzate di <xref:System.Windows.Forms.DataGridView> e come creare tipi di cella, colonna e riga derivati.</span><span class="sxs-lookup"><span data-stu-id="27d5f-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="27d5f-129">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="27d5f-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="27d5f-130">Fornisce argomenti che descrivono comunemente usate le proprietà di cella, riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="27d5f-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d5f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27d5f-131">See also</span></span>

- [<span data-ttu-id="27d5f-132">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="27d5f-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
