---
title: Impostazioni del Registro di sistema per il rendering della grafica
ms.date: 03/30/2017
helpviewer_keywords:
- rendering graphics [WPF], registry settings
- rendering graphics [WPF]
- rendering graphics [WPF], troubleshooting
- troubleshooting graphics rendering [WPF]
- graphics [WPF], rendering
ms.assetid: f4b41b42-327d-407c-b398-3ed5f505df8b
ms.openlocfilehash: 616c74ccd787d9acdcb2a3bbe281c2f43bb49c2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762726"
---
# <a name="graphics-rendering-registry-settings"></a>Impostazioni del Registro di sistema per il rendering della grafica
Questo argomento fornisce una panoramica delle impostazioni del Registro di sistema per il rendering della grafica di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che influiscono sulle applicazioni di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="overview"></a>   
## <a name="when-to-use-graphics-rendering-registry-settings"></a>Quando usare le impostazioni del Registro di sistema per il rendering della grafica  
 Queste impostazioni del Registro di sistema vengono fornite per la risoluzione dei problemi, il debug e supporto per il prodotto. Poiché le modifiche al Registro di sistema influiscono su tutte le applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], l'applicazione non deve mai modificare queste chiavi del Registro di sistema, automaticamente o durante l'installazione.  
  
<a name="xpdmandwddm"></a>   
## <a name="what-are-xpdm-and-wddm"></a>Definizione di XPDM e WDDM  
 Alcune impostazioni del Registro di sistema per il rendering della grafica hanno valori predefiniti diversi, a seconda che la scheda video usi un driver XPDM o WDDM. XPDM è il modello di driver video di [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] e WDDM è il modello di driver video di Windows. WDDM è disponibile nei computer che eseguono [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] e [!INCLUDE[win7](../../../../includes/win7-md.md)]. XPDM è disponibile nei computer che eseguono [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)], [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] e [!INCLUDE[TLA#tla_winnetsvrfam](../../../../includes/tlasharptla-winnetsvrfam-md.md)]. Per altre informazioni su WDDM, vedere [Windows Vista Display Driver Model Design Guide](https://go.microsoft.com/fwlink/?LinkId=178394) (Guida alla progettazione del modello di driver video di Windows).  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a>Impostazioni Registro di sistema  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce quattro impostazioni del Registro di sistema per controllare il rendering di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
|Impostazione|Descrizione|  
|-------------|-----------------|  
|**Opzione di disabilitazione dell'accelerazione hardware**|Specifica se l'accelerazione hardware deve essere abilitata.|  
|**Valore massimo di multicampionamento**|Specifica il grado di multicampionamento del contenuto anti-aliasing [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)].|  
|**Impostazione Data driver video necessaria**|Specifica se il sistema disabilita l'accelerazione hardware per i driver rilasciati prima di novembre 2004.|  
|**Opzione per l'uso di unità di rasterizzazione dei riferimenti**|Specifica se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] deve usare l'unità di rasterizzazione dei riferimenti.|  
  
 A queste impostazioni è possibile accedere tramite qualsiasi utilità di configurazione esterna che possa fare riferimento alle impostazioni del Registro di sistema di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per creare o modificare queste impostazioni, è possibile accedere ai valori direttamente usando l'editor del Registro di sistema di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
<a name="disablehardwareacceleration"></a>   
## <a name="disable-hardware-acceleration-option"></a>Opzione per la disabilitazione dell'accelerazione hardware  
  
|Chiave del Registro di sistema|Tipo valore|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\DisableHWAcceleration`|DWORD|  
  
 L'**opzione di disabilitazione dell'accelerazione hardware** consente di disattivare l'accelerazione hardware per scopi di debug e test. Se in un'applicazione si vedono elementi di rendering, provare a disattivare l'accelerazione hardware. Se l'elemento scompare, potrebbe trattarsi di un problema con il driver video.  
  
 L'**opzione di disabilitazione dell'accelerazione hardware** è un valore DWORD che è 0 o 1. Il valore 1 disabilita l'accelerazione hardware. Il valore 0 consente l'accelerazione hardware, purché il sistema soddisfi i requisiti di accelerazione hardware. Per altre informazioni, vedere [Livelli di rendering della grafica](../advanced/graphics-rendering-tiers.md).  
  
<a name="maxmultisample"></a>   
## <a name="maximum-multisample-value"></a>Valore massimo di multicampionamento  
  
|Chiave del Registro di sistema|Tipo valore|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\MaxMultisampleType`|DWORD|  
  
 Il **valore massimo di multicampionamento** consente di regolare la quantità massima di anti-aliasing del contenuto [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]. Usare questo livello per disabilitare l'anti-aliasing [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] in [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] o per abilitarlo in [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].  
  
 Il **valore massimo di multicampionamento** è un valore DWORD che va da 0 a 16. Il valore 0 specifica che deve essere disabilitato l'anti-aliasing di multicampionamento del contenuto 3D, e un valore pari a 16 tenterà di usare fino a 16x dell'anti-aliasing di multicampionamento, se supportato dalla scheda video. Tenere presente che l'impostazione di questo valore della chiave del Registro di sistema nei computer mediante driver XPDM comporterà l'uso di una grande quantità di memoria video aggiuntiva da parte delle applicazioni, una riduzione delle prestazioni del rendering di [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)], nonché possibili errori di rendering e problemi di stabilità.  
  
 Quando questa chiave del Registro di sistema non è impostata, il valore predefinito di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è 0 per i driver XPDM e 4 per i driver WDDM.  
  
<a name="requiredvideodriverdatesetting"></a>   
## <a name="required-video-driver-date-setting"></a>Impostazione Data driver video necessaria  
  
|Chiave del Registro di sistema|Tipo valore|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\RequiredVideoDriverDate`|Stringa|  
  
 Nel novembre 2004, [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] ha rilasciato una nuova versione delle linee guida per il test dei driver; i driver creati dopo questa data sono maggiormente stabili. Per impostazione predefinita, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa la pipeline di accelerazione hardware per questi driver ed esegue il fallback al rendering del software per driver XPDM pubblicati prima di tale data.  
  
 L'**impostazione Data driver video necessaria** consente di specificare una data alternativa minima per i driver XPDM. È necessario specificare solo una data precedente a novembre 2004 se si è certi che il driver video è sufficientemente stabile per supportare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 L'impostazione necessaria per il driver video accetta una stringa nel formato seguente:  
  
| |  
|-|  
|*AAAA* `/` *MM* `/` *GG*|  
  
 Dove *AAAA* è l'anno a quattro cifre, *MM* è il mese a due cifre, e *GG* è il giorno a due cifre. Se questo valore non è impostato, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa novembre 2004 come data necessaria del driver video.  
  
<a name="usereferencerasterizeroption"></a>   
## <a name="use-reference-rasterizer-option"></a>Opzione per l'uso di unità di rasterizzazione dei riferimenti  
  
|Chiave del Registro di sistema|Tipo valore|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\UseReferenceRasterizer`|DWORD|  
  
 L'**opzione per l'uso di unità di rasterizzazione dei riferimenti** consente di forzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una modalità di rendering dell'hardware simulato per il debug: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entra in modalità hardware, ma usa l'unità di rasterizzazione software dei riferimenti [!INCLUDE[TLA#tla_d3d](../../../../includes/tlasharptla-d3d-md.md)], d3dref9. dll, invece di un dispositivo hardware effettivo.  
  
 L'unità di rasterizzazione dei riferimenti è molto lenta, ma ignora il driver video per evitare eventuali problemi di rendering causati da problemi del driver. Per questo motivo, usare l'unità di rasterizzazione dei riferimenti per determinare se i problemi di rendering sono causati dal driver video. Il file d3dref9. dll deve essere in una posizione a cui l'applicazione può accedere, ad esempio una posizione qualsiasi nel percorso di sistema o nella directory locale dell'applicazione.  
  
 L'**opzione per l'uso di unità di rasterizzazione dei riferimenti** accetta un valore DWORD. Il valore 0 indica che l'unità di rasterizzazione dei riferimenti non viene usata. Qualsiasi altro valore diverso da zero forza [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a usare l'unità di rasterizzazione dei riferimenti.  
  
## <a name="see-also"></a>Vedere anche

- [Livelli di rendering della grafica](../advanced/graphics-rendering-tiers.md)
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
