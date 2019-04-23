---
title: 'Procedura: Creare uno StackPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121810"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="c2608-102">Procedura: Creare uno StackPanel</span><span class="sxs-lookup"><span data-stu-id="c2608-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="c2608-103">In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="c2608-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2608-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2608-104">Example</span></span>  
 <span data-ttu-id="c2608-105">Oggetto <xref:System.Windows.Controls.StackPanel> consente di sovrapporre gli elementi in una direzione specificata.</span><span class="sxs-lookup"><span data-stu-id="c2608-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="c2608-106">Usando le proprietà definite su <xref:System.Windows.Controls.StackPanel>, il contenuto può fluire in verticale, ovvero l'impostazione predefinita, orizzontalmente o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="c2608-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="c2608-107">Nell'esempio seguente in uno stack verticale cinque <xref:System.Windows.Controls.TextBlock> controlli, ognuno con un diverso <xref:System.Windows.Controls.Border> e <xref:System.Windows.Controls.Border.Background%2A>, usando <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="c2608-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="c2608-108">Gli elementi figlio che contengono non è specificata alcuna <xref:System.Windows.FrameworkElement.Width%2A> adattata per riempire la finestra padre; tuttavia, gli elementi figlio che hanno un determinato <xref:System.Windows.FrameworkElement.Width%2A>, sono centrati nella finestra.</span><span class="sxs-lookup"><span data-stu-id="c2608-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="c2608-109">La direzione predefinita in un <xref:System.Windows.Controls.StackPanel> è verticale.</span><span class="sxs-lookup"><span data-stu-id="c2608-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="c2608-110">Flusso di controllo contenuto in un <xref:System.Windows.Controls.StackPanel>, usare il <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c2608-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="c2608-111">È possibile controllare l'allineamento orizzontale tramite il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c2608-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2608-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2608-112">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="c2608-113">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="c2608-113">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="c2608-114">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="c2608-114">How-to Topics</span></span>](stackpanel-how-to-topics.md)
