---
title: Come gestire le versioni delle dipendenze di pacchetto per .NET Core 1.0
description: Informazioni sulla gestione delle versioni delle dipendenze dei pacchetti per le app e le librerie .NET Core.
author: cartermp
ms.date: 06/20/2016
ms.custom: seodec18
ms.openlocfilehash: 7d7133ddb8717db1b830e531955454925c31a728
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168611"
---
# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a>Come gestire le versioni delle dipendenze di pacchetto per .NET Core 1.0

Questo articolo descrive ciò che è necessario sapere sulle versioni dei pacchetti per le librerie e le applicazioni .NET Core.

## <a name="glossary"></a>Glossario

**Correzione**: correggere le dipendenze significa usare la stessa "famiglia" di pacchetti rilasciati su NuGet per .NET Core 1.0.

**Metapacchetto**: pacchetto NuGet che rappresenta un set di pacchetti NuGet.

**Trimming**: rimozione dei pacchetti che non dipendono da un metapacchetto.  Queste informazioni sono importanti per gli autori di pacchetti NuGet.  Per altre informazioni, vedere [Riduzione delle dipendenze dei pacchetti con project.json](../deploying/reducing-dependencies.md). 

## <a name="fix-your-dependencies-to-net-core-10"></a>Correggere le dipendenze in base a .NET Core 1.0

Per ripristinare i pacchetti e scrivere codice in modo affidabile, è importante correggere le dipendenze relative alle versioni dei pacchetti distribuiti insieme a .NET Core 1.0.  Questo significa che ogni pacchetto deve avere una sola versione senza altri qualificatori.

**Esempi di pacchetti corretti in base alla versione 1.0**

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

**Esempi di pacchetti NON corretti in base alla versione 1.0**

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a>Perché questa correzione è importante?

Se si correggono le dipendenze in base ai dati distribuiti con .NET Core 1.0, i pacchetti potranno interagire tra loro senza problemi. Questo comportamento non è invece garantito se i pacchetti che non vengono corretti in questo modo.

### <a name="scenarios"></a>Scenari

Anche se è disponibile un lungo elenco di tutti i pacchetti e delle relative versioni rilasciate con .NET Core 1.0, può non essere necessario esaminare l'elenco se il codice rientra in determinati scenari.

**Esistono solo dipendenze da** `NETStandard.Library`**?**

In questo caso, è necessario correggere il pacchetto `NETStandard.Library` in base alla versione `1.6`.  Poiché si tratta di un metapacchetto curato, anche la chiusura del pacchetto viene corretta in base alla versione 1.0.

**Esistono solo dipendenze da** `Microsoft.NETCore.App`**?**

In questo caso, è necessario correggere il pacchetto `Microsoft.NETCore.App` in base alla versione `1.0.0`.  Poiché si tratta di un metapacchetto curato, anche la chiusura del pacchetto viene corretta in base alla versione 1.0.

**Si esegue il [trimming](../deploying/reducing-dependencies.md) delle dipendenze dei metapacchetti** `NETStandard.Library` **o** `Microsoft.NETCore.App` **?**

In questo caso, è necessario verificare che il metapacchetto iniziale venga corretto in base alla versione 1.0.  Anche i singoli pacchetti da cui rimangono dipendenze dopo il trimming vengono corretti in base alla versione 1.0.

**Esistono dipendenze da pacchetti esterni a metapacchetti** `NETStandard.Library` **o** `Microsoft.NETCore.App` **?**

In questo caso, è necessario correggere le altre dipendenze in base alla versione 1.0.  Vedere le versioni di pacchetto e i numeri di build corretti alla fine di questo articolo.

### <a name="a-note-on-using-a-splat-string--when-versioning"></a>Nota sull'uso di una stringa con carattere jolly (\*) per il versionamento

È possibile che sia stato adottato uno schema di versionamento che usa una stringa con carattere jolly (\*) simile alla seguente: `"System.Collections":"4.0.11-*"`.

**Non usare stringhe di questo tipo**.  In tal caso, infatti, è possibile che vengano ripristinati pacchetti da diverse build, alcune delle quali possono non presentare alcuna corrispondenza con .NET Core 1.0.  Ciò può quindi causare l'incompatibilità di alcuni pacchetti.

## <a name="packages-and-version-numbers-organized-by-metapackage"></a>Pacchetti e numeri di versione organizzati per metapacchetto

[Elenco di tutti i pacchetti .NET Standard e relative versioni per 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt)

[Elenco di tutti i pacchetti di runtime e relative versioni per 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt)

[Elenco di tutti i pacchetti di applicazioni .NET Core e relative versioni per 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt)
