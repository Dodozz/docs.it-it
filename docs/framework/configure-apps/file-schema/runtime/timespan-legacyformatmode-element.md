---
title: Elemento <TimeSpan_LegacyFormatMode>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e265fd1de6047cd53b0f8d1c20c8a9e87b3e813
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689674"
---
# <a name="timespanlegacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode > elemento

Determina se il runtime deve mantenere il comportamento legacy in operazioni di formattazione con <xref:System.TimeSpan?displayProperty=nameWithType> valori.

\<configuration>\
\<runtime>\
\<TimeSpan_LegacyFormatMode>

## <a name="syntax"></a>Sintassi

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime usa il comportamento della formattazione legacy con <xref:System.TimeSpan?displayProperty=nameWithType> valori.|

## <a name="enabled-attribute"></a>Attributo enabled

|Valore|Descrizione|
|-----------|-----------------|
|`false`|Il runtime non consente di ripristinare il comportamento di formattazione legacy.|
|`true`|Il runtime consente di ripristinare il comportamento di formattazione legacy.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|

## <a name="remarks"></a>Note

A partire da .NET Framework 4, il <xref:System.TimeSpan?displayProperty=nameWithType> struttura implementa il <xref:System.IFormattable> interfaccia e supporta operazioni di formattazione con stringhe di formato standard e personalizzate. Se un metodo di analisi viene rilevato un identificatore di formato non supportato o una stringa di formato, viene generata una <xref:System.FormatException>.

Nelle versioni precedenti di .NET Framework, il <xref:System.TimeSpan> struttura non ha implementato <xref:System.IFormattable> e non supporta le stringhe di formato. Tuttavia, molti sviluppatori ritengono erroneamente che <xref:System.TimeSpan> supportava un set di stringhe di formato e usato nella [operazioni di formattazione composita](../../../../../docs/standard/base-types/composite-formatting.md) con i metodi come <xref:System.String.Format%2A?displayProperty=nameWithType>. In genere, se un tipo implementa <xref:System.IFormattable> e supporta le stringhe, le chiamate ai metodi di formattazione con formato non supportato in genere generano stringhe di formato un <xref:System.FormatException>. Tuttavia, poiché <xref:System.TimeSpan> non ha implementato <xref:System.IFormattable>, il runtime ignorata la stringa di formato e invece chiamato il <xref:System.TimeSpan.ToString?displayProperty=nameWithType> (metodo). Ciò significa che, anche se le stringhe di formato non aveva alcun effetto sull'operazione di formattazione, la loro presenza non ha restituito un <xref:System.FormatException>.

Per i casi in cui il codice legacy passa un metodo e una stringa di formato non valido di formattazione composita, e non è possibile ricompilare tale codice, è possibile usare la `<TimeSpan_LegacyFormatMode>` elemento da ripristinare legacy <xref:System.TimeSpan> comportamento. Quando si imposta la `enabled` attributo di questo elemento per `true`, i risultati dei metodi in una chiamata a di formattazione composita <xref:System.TimeSpan.ToString?displayProperty=nameWithType> anziché <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>e un <xref:System.FormatException> non viene generata.

## <a name="example"></a>Esempio

Nell'esempio seguente crea un <xref:System.TimeSpan> oggetto e tenta di formattarla con il <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> metodo tramite una stringa di formato standard non è supportato.

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

Quando si esegue l'esempio in .NET Framework 3.5 o una versione precedente, viene visualizzato l'output seguente:

```
12:30:45
```

È notevolmente differente dall'output se si esegue l'esempio di .NET Framework 4 o versione successiva:

```
Invalid Format
```

Tuttavia, se si aggiunge il file di configurazione seguente alla directory di esempio e quindi eseguirla l'esempio di .NET Framework 4 o versione successiva, l'output è identico a quello prodotto dall'esempio quando viene eseguita in .NET Framework 3.5.

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
