---
title: 'Procedura: Utilizzare chiavi di caratteri del sistema'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: aec3ba8b84836d068b7efcfe53b34b126334b8de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628708"
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="7fe39-102">Procedura: Utilizzare chiavi di caratteri del sistema</span><span class="sxs-lookup"><span data-stu-id="7fe39-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="7fe39-103">Le risorse di sistema espongono diverse metriche di sistema come risorse per consentire agli sviluppatori di creare oggetti visivi coerenti con le impostazioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="7fe39-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="7fe39-104"><xref:System.Windows.SystemFonts> è una classe che contiene i valori del tipo di carattere di sistema e le risorse del tipo di carattere di sistema associati ai valori, ad esempio, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> e <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fe39-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="7fe39-105">Le metriche dei tipi di carattere del sistema possono essere usate come risorse statiche o dinamiche.</span><span class="sxs-lookup"><span data-stu-id="7fe39-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="7fe39-106">Usare una risorsa dinamica per aggiornare automaticamente la metrica del tipo di carattere durante l'esecuzione dell'applicazione; in caso contrario, usare una risorsa statica.</span><span class="sxs-lookup"><span data-stu-id="7fe39-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fe39-107">Le risorse dinamiche hanno la parola chiave *chiave* accodato al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7fe39-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="7fe39-108">L'esempio seguente illustra come accedere alle risorse dinamiche dei tipi di carattere del sistema e usarle per applicare uno stile a un pulsante o personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="7fe39-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="7fe39-109">Ciò [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riportato di seguito viene creato uno stile pulsante che assegna <xref:System.Windows.SystemFonts> valori a un pulsante.</span><span class="sxs-lookup"><span data-stu-id="7fe39-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fe39-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fe39-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="7fe39-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fe39-111">See also</span></span>
- [<span data-ttu-id="7fe39-112">Disegnare un'area con un pennello di sistema</span><span class="sxs-lookup"><span data-stu-id="7fe39-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="7fe39-113">Utilizzare SystemParameters</span><span class="sxs-lookup"><span data-stu-id="7fe39-113">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
- [<span data-ttu-id="7fe39-114">Utilizzare la classe SystemFonts</span><span class="sxs-lookup"><span data-stu-id="7fe39-114">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
