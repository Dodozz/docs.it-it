---
title: 'Procedura: Usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: b56a307ed31fc8f7573215eac70350ac5e4b9de1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772115"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="748de-102">Procedura: Usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili</span><span class="sxs-lookup"><span data-stu-id="748de-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="748de-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.ResourceDictionary> per assemblare risorse stringa localizzabili per applicazioni Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="748de-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="748de-104">Per usare un oggetto ResourceDictionary per gestire le risorse di tipo stringa localizzabili</span><span class="sxs-lookup"><span data-stu-id="748de-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1. <span data-ttu-id="748de-105">Creare un <xref:System.Windows.ResourceDictionary> che contiene le stringhe da localizzare.</span><span class="sxs-lookup"><span data-stu-id="748de-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="748de-106">Il codice seguente illustra un esempio.</span><span class="sxs-lookup"><span data-stu-id="748de-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="748de-107">Questo codice definisce una risorsa, stringa `localizedMessage`, di tipo <xref:System.String>, dal <xref:System> dello spazio dei nomi in mscorlib. dll.</span><span class="sxs-lookup"><span data-stu-id="748de-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2. <span data-ttu-id="748de-108">Aggiungere il <xref:System.Windows.ResourceDictionary> all'applicazione, usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="748de-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. <span data-ttu-id="748de-109">Usare la risorsa stringa dal markup, usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="748de-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. <span data-ttu-id="748de-110">Usare la risorsa di tipo stringa dal code-behind, usando un codice analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="748de-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. <span data-ttu-id="748de-111">Localizzare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="748de-111">Localize the application.</span></span> <span data-ttu-id="748de-112">Per altre informazioni, vedere [localizzare un'applicazione](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="748de-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>
