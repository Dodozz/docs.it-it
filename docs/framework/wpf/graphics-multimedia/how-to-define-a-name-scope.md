---
title: 'Procedura: Definire un ambito del nome'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: a03f477dd31909e8cb9dde9cd29da6f38d665758
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086819"
---
# <a name="how-to-define-a-name-scope"></a><span data-ttu-id="5ce09-102">Procedura: Definire un ambito del nome</span><span class="sxs-lookup"><span data-stu-id="5ce09-102">How to: Define a Name Scope</span></span>
<span data-ttu-id="5ce09-103">Per aggiungere un'animazione con <xref:System.Windows.Media.Animation.Storyboard> nel codice, è necessario creare un <xref:System.Windows.NameScope> e registrare i nomi degli oggetti di destinazione con l'elemento che è proprietario di tale ambito dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5ce09-103">To animate with <xref:System.Windows.Media.Animation.Storyboard> in code, you must create a <xref:System.Windows.NameScope> and register the target objects' names with the element that owns that name scope.</span></span> <span data-ttu-id="5ce09-104">Nell'esempio seguente, un <xref:System.Windows.NameScope> viene creato per `myMainPanel`.</span><span class="sxs-lookup"><span data-stu-id="5ce09-104">In the following example, a <xref:System.Windows.NameScope> is created for `myMainPanel`.</span></span> <span data-ttu-id="5ce09-105">Due pulsanti, `button1` e `button2`, vengono aggiunti al pannello di e i relativi nomi registrati.</span><span class="sxs-lookup"><span data-stu-id="5ce09-105">Two buttons, `button1` and `button2`, are added to the panel, and their names registered.</span></span> <span data-ttu-id="5ce09-106">Diverse animazioni e un <xref:System.Windows.Media.Animation.Storyboard> vengono creati.</span><span class="sxs-lookup"><span data-stu-id="5ce09-106">Several animations and a <xref:System.Windows.Media.Animation.Storyboard> are created.</span></span> <span data-ttu-id="5ce09-107">Lo storyboard <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo viene usato per avviare le animazioni.</span><span class="sxs-lookup"><span data-stu-id="5ce09-107">The storyboard's <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method is used to start the animations.</span></span>  
  
 <span data-ttu-id="5ce09-108">In quanto `button1`, `button2`, e `myMainPanel` condividono tutti lo stesso ambito del nome, uno di essi può essere utilizzato con il <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo per avviare le animazioni.</span><span class="sxs-lookup"><span data-stu-id="5ce09-108">Because `button1`, `button2`, and `myMainPanel` all share the same name scope, any one of them can be used with the <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method to start the animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ce09-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="5ce09-109">Example</span></span>  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="5ce09-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ce09-110">See also</span></span>

- [<span data-ttu-id="5ce09-111">Animare una proprietà utilizzando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="5ce09-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="5ce09-112">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="5ce09-112">Animation Overview</span></span>](animation-overview.md)
