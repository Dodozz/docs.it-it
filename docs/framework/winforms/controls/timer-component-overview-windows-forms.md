---
title: Cenni preliminari sul componente Timer (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: a13afba026f1f9eed095817c65637bb6a091c7f0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725285"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="83842-102">Cenni preliminari sul componente Timer (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="83842-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="83842-103">Il componente <xref:System.Windows.Forms.Timer> di Windows Form genera un evento a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="83842-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="83842-104">Questo componente è progettato per l'ambiente Windows Form.</span><span class="sxs-lookup"><span data-stu-id="83842-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="83842-105">Per informazioni su un timer adatto a un ambiente server, vedere [Introduzione ai timer basati su server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="83842-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="83842-106">Le proprietà di chiave, metodi ed eventi</span><span class="sxs-lookup"><span data-stu-id="83842-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="83842-107">La lunghezza degli intervalli viene definita per il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà, il cui valore è espresso in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="83842-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="83842-108">Quando il componente è abilitato, il <xref:System.Windows.Forms.Timer.Tick> l'evento viene generato ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="83842-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="83842-109">Si tratta in cui si aggiungerà codice da eseguire.</span><span class="sxs-lookup"><span data-stu-id="83842-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="83842-110">Per altre informazioni, vedere [Procedura: Eseguire routine a intervalli predefiniti con il componente Timer di Windows Form](run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="83842-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="83842-111">I metodi principali dei <xref:System.Windows.Forms.Timer> componente vengono <xref:System.Windows.Forms.Timer.Start%2A> e <xref:System.Windows.Forms.Timer.Stop%2A>, che attivano il timer e disattivare.</span><span class="sxs-lookup"><span data-stu-id="83842-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="83842-112">Quando il timer è disattivato, viene reimpostato; non è possibile sospendere un <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="83842-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83842-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83842-113">See also</span></span>
- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="83842-114">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="83842-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="83842-115">Limitazioni della proprietà Interval del componente Timer di Windows Form</span><span class="sxs-lookup"><span data-stu-id="83842-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
