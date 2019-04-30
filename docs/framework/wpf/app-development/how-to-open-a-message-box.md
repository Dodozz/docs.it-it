---
title: 'Procedura: Aprire una finestra di messaggio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message boxes [WPF], opening
- opening message boxes [WPF]
ms.assetid: acaad17f-af43-4eca-a004-f1c9e7c6f292
ms.openlocfilehash: cf7534cdee5e17d53e95294573023d660135e395
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947693"
---
# <a name="how-to-open-a-message-box"></a><span data-ttu-id="b5168-102">Procedura: Aprire una finestra di messaggio</span><span class="sxs-lookup"><span data-stu-id="b5168-102">How to: Open a Message Box</span></span>
<span data-ttu-id="b5168-103">In questo esempio viene illustrato come aprire una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="b5168-103">This example shows how to open a message box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5168-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5168-104">Example</span></span>  
 <span data-ttu-id="b5168-105">Una finestra di messaggio è una finestra di dialogo modale predefiniti per la visualizzazione di informazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="b5168-105">A message box is a prefabricated modal dialog box for displaying information to users.</span></span> <span data-ttu-id="b5168-106">Viene aperta una finestra di messaggio chiamando il metodo statico <xref:System.Windows.MessageBox.Show%2A> metodo di <xref:System.Windows.MessageBox> classe.</span><span class="sxs-lookup"><span data-stu-id="b5168-106">A message box is opened by calling the static <xref:System.Windows.MessageBox.Show%2A> method of the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="b5168-107">Quando si <xref:System.Windows.MessageBox.Show%2A> viene chiamato, il messaggio viene passato usando un parametro di stringa.</span><span class="sxs-lookup"><span data-stu-id="b5168-107">When <xref:System.Windows.MessageBox.Show%2A> is called, the message is passed using a string parameter.</span></span> <span data-ttu-id="b5168-108">Diversi overload del <xref:System.Windows.MessageBox.Show%2A> consentono di configurare la modalità in cui verrà visualizzata una finestra di messaggio (vedere <xref:System.Windows.MessageBox>).</span><span class="sxs-lookup"><span data-stu-id="b5168-108">Several overloads of <xref:System.Windows.MessageBox.Show%2A> allow you to configure how a message box will appear (see <xref:System.Windows.MessageBox>).</span></span>  
  
 [!code-csharp[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MessageBoxSnippets/CSharp/Show1Window.xaml.cs#messageboxshow1code)]
 [!code-vb[MessageBoxSnippets#MessageBoxShow1CODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MessageBoxSnippets/visualbasic/show1window.xaml.vb#messageboxshow1code)]  
  
## <a name="see-also"></a><span data-ttu-id="b5168-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5168-109">See also</span></span>

- [<span data-ttu-id="b5168-110">Esempio di MessageBox</span><span class="sxs-lookup"><span data-stu-id="b5168-110">MessageBox Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160023)
