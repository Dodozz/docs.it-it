---
title: 'Procedura: Impostare il titolo di una finestra da una pagina'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054003"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="a2931-102">Procedura: Impostare il titolo di una finestra da una pagina</span><span class="sxs-lookup"><span data-stu-id="a2931-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="a2931-103">In questo esempio viene illustrato come impostare il titolo della finestra in cui un <xref:System.Windows.Controls.Page> è ospitato.</span><span class="sxs-lookup"><span data-stu-id="a2931-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2931-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2931-104">Example</span></span>  
 <span data-ttu-id="a2931-105">Una pagina è possibile modificare il titolo della finestra che la ospita impostando il <xref:System.Windows.Controls.Page.WindowTitle%2A> proprietà, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a2931-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  <span data-ttu-id="a2931-106">L'impostazione di <xref:System.Windows.Controls.Page.Title%2A> non modifica il valore del titolo della finestra proprietà di una pagina.</span><span class="sxs-lookup"><span data-stu-id="a2931-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="a2931-107">Al contrario, <xref:System.Windows.Controls.Page.Title%2A> specifica il nome di una voce di pagina nella cronologia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="a2931-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
