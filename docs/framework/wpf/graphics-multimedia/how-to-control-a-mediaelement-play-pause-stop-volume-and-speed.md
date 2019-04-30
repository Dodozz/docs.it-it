---
title: 'Procedura: Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: bb7319fc7ccec0220cbd79a32d5d015f9f2422d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984046"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="d0c10-102">Procedura: Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)</span><span class="sxs-lookup"><span data-stu-id="d0c10-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="d0c10-103">Nell'esempio seguente viene illustrato come controllare la riproduzione dei supporti tramite un <xref:System.Windows.Controls.MediaElement>.</span><span class="sxs-lookup"><span data-stu-id="d0c10-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="d0c10-104">Nell'esempio viene creato un semplice lettore multimediale che consente di riprodurre, sospendere, arrestare e andare avanti e indietro nei supporti, nonché imposta la proporzione di volume e velocità.</span><span class="sxs-lookup"><span data-stu-id="d0c10-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0c10-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0c10-105">Example</span></span>  
 <span data-ttu-id="d0c10-106">Il codice seguente crea l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="d0c10-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0c10-107">Il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà di <xref:System.Windows.Controls.MediaElement> deve essere impostata su `Manual` affinché sia in grado di arrestare in modo interattivo, sospendere e riprodurre i contenuti multimediali.</span><span class="sxs-lookup"><span data-stu-id="d0c10-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="d0c10-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0c10-108">Example</span></span>  
 <span data-ttu-id="d0c10-109">Il codice seguente implementa la funzionalità dei controlli dell'interfaccia utente di esempio.</span><span class="sxs-lookup"><span data-stu-id="d0c10-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="d0c10-110">Il <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, e <xref:System.Windows.Controls.MediaElement.Stop%2A> metodi vengono utilizzati rispettivamente play, sospendere e arrestare i contenuti multimediali.</span><span class="sxs-lookup"><span data-stu-id="d0c10-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="d0c10-111">Modifica il <xref:System.Windows.Controls.MediaElement.Position%2A> proprietà del <xref:System.Windows.Controls.MediaElement> consente di spostarsi nel supporto.</span><span class="sxs-lookup"><span data-stu-id="d0c10-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="d0c10-112">Infine, il <xref:System.Windows.Controls.MediaElement.Volume%2A> e <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> proprietà vengono utilizzate per regolare la velocità di volume e la riproduzione dei contenuti multimediali.</span><span class="sxs-lookup"><span data-stu-id="d0c10-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d0c10-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0c10-113">See also</span></span>

- [<span data-ttu-id="d0c10-114">Controllare un MediaElement usando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="d0c10-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
