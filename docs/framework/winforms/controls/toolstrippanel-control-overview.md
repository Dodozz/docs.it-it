---
title: Cenni preliminari sul controllo ToolStripPanel
ms.date: 03/30/2017
f1_keywords:
- ToolStripPanel
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms], about ToolStripPanel control
ms.assetid: ce54a60c-5eba-4b4c-bd77-cf0748a666cc
ms.openlocfilehash: 694cb88807f718a1f3122ae8cd9d7d4af4e576e1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192602"
---
# <a name="toolstrippanel-control-overview"></a><span data-ttu-id="f8e20-102">Cenni preliminari sul controllo ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="f8e20-102">ToolStripPanel Control Overview</span></span>
<span data-ttu-id="f8e20-103">Oggetto <xref:System.Windows.Forms.ToolStripPanel> fornisce un'unica area per posizionare e raggruppare <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, e <xref:System.Windows.Forms.StatusStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="f8e20-103">A <xref:System.Windows.Forms.ToolStripPanel> provides a single area for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="f8e20-104">Più <xref:System.Windows.Forms.ToolStrip> controlli vengono disposti orizzontalmente o verticalmente in base il <xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A> del <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f8e20-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically or horizontally depending on the <xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A> of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
### <a name="important-toolstrippanel-members"></a><span data-ttu-id="f8e20-105">Membri importanti di ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="f8e20-105">Important ToolStripPanel Members</span></span>  
  
|<span data-ttu-id="f8e20-106">Nome</span><span class="sxs-lookup"><span data-stu-id="f8e20-106">Name</span></span>|<span data-ttu-id="f8e20-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8e20-107">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripPanel.Orientation%2A>|<span data-ttu-id="f8e20-108">Ottiene o imposta un valore che indica l'orientamento orizzontale o verticale del <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f8e20-108">Gets or sets a value indicating the horizontal or vertical orientation of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Renderer%2A>|<span data-ttu-id="f8e20-109">Ottiene o imposta una <xref:System.Windows.Forms.ToolStripRenderer> usato per personalizzare l'aspetto di un <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f8e20-109">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance of a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RenderMode%2A>|<span data-ttu-id="f8e20-110">Ottiene o imposta gli stili di disegno da applicare al <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f8e20-110">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RowMargin%2A>|<span data-ttu-id="f8e20-111">Ottiene o imposta la spaziatura, in pixel, tra il <xref:System.Windows.Forms.ToolStripPanelRow> e il <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f8e20-111">Gets or sets the spacing, in pixels, between the <xref:System.Windows.Forms.ToolStripPanelRow> and the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Rows%2A>|<span data-ttu-id="f8e20-112">Ottiene il <xref:System.Windows.Forms.ToolStripPanelRow> in questo <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f8e20-112">Gets the <xref:System.Windows.Forms.ToolStripPanelRow> in this <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Join%2A>|<span data-ttu-id="f8e20-113">Aggiunge un <xref:System.Windows.Forms.ToolStrip> a un <xref:System.Windows.Forms.ToolStripPanel>.</span><span class="sxs-lookup"><span data-stu-id="f8e20-113">Adds a <xref:System.Windows.Forms.ToolStrip> to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8e20-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8e20-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
- <span data-ttu-id="f8e20-115">[Esempio di ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ms181005(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f8e20-115">[ToolStrip Sample](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ms181005(v=vs.90))</span></span>
