---
ms.openlocfilehash: 1545c807e3bef675e63e14d01ab82c1131600f39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235704"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear non rimuove i duplicati da SelectedItems

|   |   |
|---|---|
|Dettagli|Se un selettore con selezione multipla abilitata contiene duplicati nella raccolta <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>, lo stesso elemento viene visualizzato più volte.  L'eliminazione di questi elementi dall'origine dati (ad esempio, chiamando Items.Clear) non li rimuove da <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>; viene rimossa solo la prima istanza. Nell'uso successivo di <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>, ad esempio SelectedItems.Clear(), si possono inoltre verificare errori, ad esempio <xref:System.ArgumentException?displayProperty=name>, in quanto <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> contiene elementi che non sono più nell'origine dati.|
|Suggerimento|Se possibile, eseguire l'aggiornamento a .NET Framework 4.6.2.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
