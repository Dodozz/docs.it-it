---
title: 'Procedura: Utilizzare il layout automatico per creare un pulsante'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 501341f0e71e6e5a224c51e4ae01c68ce6b845cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543487"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="dc723-102">Procedura: Utilizzare il layout automatico per creare un pulsante</span><span class="sxs-lookup"><span data-stu-id="dc723-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="dc723-103">Questo esempio descrive come usare un approccio basato sul layout automatico per la creazione di un pulsante in un'applicazione localizzabile.</span><span class="sxs-lookup"><span data-stu-id="dc723-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="dc723-104">Localizzazione di un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] può essere un processo molto tempo.</span><span class="sxs-lookup"><span data-stu-id="dc723-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="dc723-105">Spesso sono necessari il ridimensionamento e il riposizionamento degli elementi, oltre alla traduzione del testo.</span><span class="sxs-lookup"><span data-stu-id="dc723-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="dc723-106">In precedenza ogni lingua che un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] richiedeva delle modifiche è stato adattato.</span><span class="sxs-lookup"><span data-stu-id="dc723-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="dc723-107">Ora con le funzionalità di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è possibile progettare elementi che riducono la necessità di modifiche.</span><span class="sxs-lookup"><span data-stu-id="dc723-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="dc723-108">L'approccio alla scrittura di applicazioni che è possibile ridimensionare e riposizionare con maggiore semplicità viene definito `automatic layout`.</span><span class="sxs-lookup"><span data-stu-id="dc723-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
 <span data-ttu-id="dc723-109">I seguenti due [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempi di creano applicazioni che creano un pulsante, uno con testo in lingua inglese e uno con testo in spagnolo.</span><span class="sxs-lookup"><span data-stu-id="dc723-109">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="dc723-110">Il codice è lo stesso ad eccezione del testo. Il pulsante si regola per adattarsi al testo.</span><span class="sxs-lookup"><span data-stu-id="dc723-110">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc723-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc723-111">Example</span></span>  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="dc723-112">La figura seguente mostra l'output degli esempi di codice.</span><span class="sxs-lookup"><span data-stu-id="dc723-112">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="dc723-113">![Lo stesso pulsante con testo in lingue diverse](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="dc723-113">![The same button with text in different languages](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="dc723-114">Pulsante a ridimensionamento automatico</span><span class="sxs-lookup"><span data-stu-id="dc723-114">Auto Resizable Button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc723-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc723-115">See also</span></span>
- [<span data-ttu-id="dc723-116">Cenni preliminari sull'utilizzo del layout automatico</span><span class="sxs-lookup"><span data-stu-id="dc723-116">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)
- [<span data-ttu-id="dc723-117">Usare una griglia per il layout automatico</span><span class="sxs-lookup"><span data-stu-id="dc723-117">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
