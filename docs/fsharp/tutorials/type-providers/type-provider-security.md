---
title: Sicurezza dei provider di tipi
description: Informazioni sulla sicurezza del provider di tipo in F#, incluse le procedure modificare le impostazioni del trust per un provider di tipi.
ms.date: 05/16/2016
ms.openlocfilehash: 26f95ad3950b37a668c497f293b9941ed13a18c7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641843"
---
# <a name="type-provider-security"></a>Sicurezza dei provider di tipi

Provider di tipi sono assembly (DLL) fa riferimento il F# project o script che contengono codice per la connessione alle origini dati esterne e della superficie di attacco questo tipo di informazioni per il F# digitare "ambiente". In genere, viene eseguito solo codice negli assembly di riferimento quando si compila e quindi eseguire il codice (o nel caso di uno script, inviare il codice per F# interattivo). Tuttavia, un assembly del provider di tipo verrà eseguito all'interno di Visual Studio quando viene semplicemente il codice viene visualizzato nell'editor. Ciò accade perché i provider di tipo devono eseguire per aggiungere informazioni aggiuntive per l'editor, ad esempio le descrizioni comandi informazioni rapide, i completamenti IntelliSense e così via. Di conseguenza, vi sono considerazioni sulla sicurezza aggiuntiva per il tipo di assembly del provider, perché vengono eseguiti automaticamente all'interno del processo di Visual Studio.

## <a name="security-warning-dialog"></a>Avviso di sicurezza

Quando si usa un assembly del provider di tipo specifico per la prima volta, Visual Studio visualizza una finestra di dialogo di sicurezza in cui si segnala che il provider di tipi sta per eseguire. Prima di Visual Studio carica il provider di tipi, offre la possibilità di decidere se considerare attendibile questo provider specifico. Se si considera attendibile l'origine del provider del tipo, quindi selezionare "Mi fido di questo provider di tipi". Se si ritiene attendibile l'origine del provider del tipo, quindi selezionare "non considerare attendibile questo provider di tipi." Concessione dell'attendibilità del provider consente di eseguire all'interno di Visual Studio e fornire IntelliSense e le funzionalità di compilazione. Ma se il provider di tipo stesso è dannoso, che esegue il codice potrebbe compromettere il computer.

Se il progetto contiene codice che fa riferimento a provider di tipi che si è scelto nella finestra di dialogo non considerare attendibile, quindi in fase di compilazione, il compilatore segnalerà un errore che indica che il provider di tipi non è considerato attendibile. Tutti i tipi che dipendono dal provider di tipo non trusted sono indicati da sottolineature rosse. È consigliabile esaminare il codice nell'editor.

Se si decide di modificare l'impostazione di attendibilità direttamente in Visual Studio, eseguire la procedura seguente.

### <a name="to-change-the-trust-settings-for-type-providers"></a>Per modificare le impostazioni del trust di provider di tipi

1. Nel `Tools` dal menu `Options`, espandere il `F# Tools` nodo.

2. Selezionare `Type Providers`, nell'elenco di provider di tipi, selezionare la casella di controllo per i provider di tipi è attendibile e deselezionare la casella di controllo per quelli non attendibili.

## <a name="see-also"></a>Vedere anche

- [Provider di tipi](index.md)
