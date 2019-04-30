---
title: Stili e modelli di Window
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: ebd21829591b8fefe87aeba0b86280f18eff4f06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62023832"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="03884-102">Stili e modelli di Window</span><span class="sxs-lookup"><span data-stu-id="03884-102">Window Styles and Templates</span></span>
<span data-ttu-id="03884-103">In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Window> controllo.</span><span class="sxs-lookup"><span data-stu-id="03884-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="03884-104">È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="03884-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="03884-105">Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="03884-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="03884-106">Elementi di finestra</span><span class="sxs-lookup"><span data-stu-id="03884-106">Window Parts</span></span>  
 <span data-ttu-id="03884-107">Il <xref:System.Windows.Window> controllo non dispone di parti denominate.</span><span class="sxs-lookup"><span data-stu-id="03884-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="03884-108">Gli stati della finestra</span><span class="sxs-lookup"><span data-stu-id="03884-108">Window States</span></span>  
 <span data-ttu-id="03884-109">La tabella seguente elenca gli stati visivi il <xref:System.Windows.Window> controllo.</span><span class="sxs-lookup"><span data-stu-id="03884-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="03884-110">Nome VisualState</span><span class="sxs-lookup"><span data-stu-id="03884-110">VisualState Name</span></span>|<span data-ttu-id="03884-111">Nome VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="03884-111">VisualStateGroup Name</span></span>|<span data-ttu-id="03884-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03884-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="03884-113">Valido</span><span class="sxs-lookup"><span data-stu-id="03884-113">Valid</span></span>|<span data-ttu-id="03884-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="03884-114">ValidationStates</span></span>|<span data-ttu-id="03884-115">Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.</span><span class="sxs-lookup"><span data-stu-id="03884-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="03884-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="03884-116">InvalidFocused</span></span>|<span data-ttu-id="03884-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="03884-117">ValidationStates</span></span>|<span data-ttu-id="03884-118">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="03884-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="03884-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="03884-119">InvalidUnfocused</span></span>|<span data-ttu-id="03884-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="03884-120">ValidationStates</span></span>|<span data-ttu-id="03884-121">Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.</span><span class="sxs-lookup"><span data-stu-id="03884-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="03884-122">Esempio di ControlTemplate finestra</span><span class="sxs-lookup"><span data-stu-id="03884-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="03884-123">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Window> controllo.</span><span class="sxs-lookup"><span data-stu-id="03884-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="03884-124">Il <xref:System.Windows.Controls.ControlTemplate> utilizza uno o più delle seguenti risorse.</span><span class="sxs-lookup"><span data-stu-id="03884-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="03884-125">Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="03884-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03884-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03884-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="03884-127">Stili e modelli di Control</span><span class="sxs-lookup"><span data-stu-id="03884-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="03884-128">Personalizzazione dei controlli</span><span class="sxs-lookup"><span data-stu-id="03884-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="03884-129">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="03884-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="03884-130">Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="03884-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
