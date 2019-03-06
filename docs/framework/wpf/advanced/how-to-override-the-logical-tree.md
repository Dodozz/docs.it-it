---
title: "Procedura: Eseguire l'override dell'albero logico"
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375219"
---
# <a name="how-to-override-the-logical-tree"></a><span data-ttu-id="6ffe6-102">Procedura: Eseguire l'override dell'albero logico</span><span class="sxs-lookup"><span data-stu-id="6ffe6-102">How to: Override the Logical Tree</span></span>
<span data-ttu-id="6ffe6-103">Benché nella maggior parte dei casi non sia necessario, gli autori di controlli avanzati hanno la possibilità di eseguire l'override dell'albero logico.</span><span class="sxs-lookup"><span data-stu-id="6ffe6-103">Although it is not necessary in most cases, advanced control authors have the option to override the logical tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ffe6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ffe6-104">Example</span></span>  
 <span data-ttu-id="6ffe6-105">In questo esempio viene illustrato come creare una sottoclasse <xref:System.Windows.Controls.StackPanel> all'override dell'albero logico, in questo caso per imporre un comportamento che il pannello può avere solo e verrà eseguito solo il rendering di un singolo elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="6ffe6-105">This example describes how to subclass <xref:System.Windows.Controls.StackPanel> to override the logical tree, in this case to enforce a behavior that the panel may only have and will only render a single child element.</span></span> <span data-ttu-id="6ffe6-106">Benché non si tratti necessariamente di un comportamento utile, viene presentato come mezzo per illustrare lo scenario di override del normale albero logico di un elemento.</span><span class="sxs-lookup"><span data-stu-id="6ffe6-106">This isn't necessarily a practically desirable behavior, but is shown here as a means of illustrating the scenario for overriding an element's normal logical tree.</span></span>  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 <span data-ttu-id="6ffe6-107">Per altre informazioni sull'albero logico, vedere [Strutture ad albero in WPF](trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="6ffe6-107">For more information on the logical tree, see [Trees in WPF](trees-in-wpf.md).</span></span>
