---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804277"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a>HtmlTextWriter non esegue correttamente il rendering dell'elemento `<br/>`

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6, la chiamata di <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> e <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento <code>&lt;BR /&gt;</code> inserirà correttamente solo un <code>&lt;BR /&gt;</code> (invece di due)|
|Suggerimento|Se un'app dipende dal tag <code>&lt;BR /&gt;</code> aggiuntivo, il metodo <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> deve essere chiamato una seconda volta. Si noti che questa modifica di comportamento influisce solo sulle app destinate a .NET Framework 4.6 o versioni successive, quindi è possibile in alternativa selezionare una versione precedente di .NET Framework come destinazione per ottenere il comportamento precedente.|
|Ambito|Microsoft Edge|
|Versione|4.6|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|
