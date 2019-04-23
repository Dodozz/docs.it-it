---
ms.openlocfilehash: 3e9a1009167d8a765bc401d64a574bd123736ccd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774058"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a>Consentire i caratteri di controllo bidirezionali Unicode negli URI

|   |   |
|---|---|
|Dettagli|La specifica Unicode include vari caratteri di controllo speciali, usati per indicare l'orientamento del testo. Nelle versioni precedenti di .NET Framework tali caratteri venivano erroneamente rimossi da tutti gli URI, anche se erano presenti con il formato di codifica con percentuali appropriato. Per una maggior conformità con [RFC 3987](https://tools.ietf.org/html/rfc3987), ora tali caratteri sono consentiti negli URI. Se vengono rilevati come non codificati in un URI, i caratteri vengono codificati con simboli di percentuale. Se sono già codificati con simboli di percentuale, vengono lasciati invariati.|
|Suggerimento|Per le applicazioni destinate alle versioni di .NET Framework a partire da 4.7.2 il supporto dei caratteri Unicode bidirezionali è abilitato per impostazione predefinita. Se questa modifica non è opportuna, è possibile disabilitarla aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'app:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Per le applicazioni che sono destinate a versioni precedenti di .NET Framework ma vengono eseguite con versioni a partire da .NET Framework 4.7.2, il supporto per i caratteri Unicode bidirezionali è disabilitato per impostazione predefinita. È possibile abilitarlo aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'app:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.2|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
