---
title: Estensione del markup RelativeSource
ms.date: 03/30/2017
f1_keywords:
- RelativeSource
helpviewer_keywords:
- RelativeSource markup extensions [WPF]
- XAML [WPF], RelativeSource markup extension
ms.assetid: 26be4721-49b5-4717-a92e-7d54ad0d3a81
ms.openlocfilehash: a6a7d615a3a54fbc75bb86b295fdf80433a31dc5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476334"
---
# <a name="relativesource-markupextension"></a>Estensione del markup RelativeSource

Specifica le proprietà di un <xref:System.Windows.Data.RelativeSource> origine dell'associazione da utilizzare all'interno di un [estensione di Markup di associazione](binding-markup-extension.md), o quando si imposta la <xref:System.Windows.Data.Binding.RelativeSource%2A> proprietà di un <xref:System.Windows.Data.Binding> elemento in XAML.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xml
<Binding RelativeSource="{RelativeSource modeEnumValue}" .../>
```

## <a name="xaml-attribute-usage-nested-within-binding-extension"></a>Utilizzo della sintassi XAML per gli attributi (annidati nell'estensione Binding)

```xml
<object property="{Binding RelativeSource={RelativeSource modeEnumValue} ...}" .../>
```

## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource Mode="modeEnumValue"/>
  </Binding.RelativeSource>
</Binding>
```

-oppure-

```xml
<Binding>
  <Binding.RelativeSource>
    <RelativeSource
      Mode="FindAncestor"
      AncestorType="{x:Type typeName}"
      AncestorLevel="intLevel"
    />
  </Binding.RelativeSource>
</Binding>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`modeEnumValue`|Uno dei seguenti:<br /><br /> -Il token di stringa `Self`; corrisponde a un <xref:System.Windows.Data.RelativeSource> creato con relativo <xref:System.Windows.Data.RelativeSource.Mode%2A> impostata su <xref:System.Windows.Data.RelativeSourceMode.Self>.<br />-Il token di stringa `TemplatedParent`; corrisponde a un <xref:System.Windows.Data.RelativeSource> creato con relativo <xref:System.Windows.Data.RelativeSource.Mode%2A> impostata su <xref:System.Windows.Data.RelativeSourceMode.TemplatedParent>.<br />-Il token di stringa `PreviousData`; corrisponde a un <xref:System.Windows.Data.RelativeSource> creato con relativo <xref:System.Windows.Data.RelativeSource.Mode%2A> impostata su <xref:System.Windows.Data.RelativeSourceMode.PreviousData>.<br />-Vedere di seguito per informazioni su `FindAncestor` modalità.|
|`FindAncestor`|Token stringa `FindAncestor`. L'utilizzo di questo token consente di accedere a una modalità in cui `RelativeSource` specifica un tipo predecessore e facoltativamente un livello predecessore. Corrisponde a un oggetto <xref:System.Windows.Data.RelativeSource> creato con la proprietà <xref:System.Windows.Data.RelativeSource.Mode%2A> impostata su <xref:System.Windows.Data.RelativeSourceMode.FindAncestor>.|
|`typeName`|Obbligatorio per la modalità `FindAncestor`. Nome di un tipo che riempie la proprietà <xref:System.Windows.Data.RelativeSource.AncestorType%2A>.|
|`intLevel`|Facoltativo per la modalità `FindAncestor`. Livello predecessore (valutato nella direzione padre dell'albero logico).|

## <a name="remarks"></a>Note

`{RelativeSource TemplatedParent}` gli utilizzi dell'associazione sono una tecnica fondamentale che risolve un concetto più ampio di separazione dell'interfaccia utente di un controllo e per la logica di un controllo. Ciò consente l'associazione dall'interno della definizione del modello al padre basato su modelli (istanza dell'oggetto in fase di esecuzione alla quale è applicato il modello). In questo caso, il [estensione di Markup TemplateBinding](templatebinding-markup-extension.md) è in realtà una sintassi abbreviata per l'espressione di associazione seguente: `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding` o `{RelativeSource TemplatedParent}` utilizzi sono entrambi rilevanti solo all'interno di XAML che definisce un modello. Per altre informazioni, vedere [estensione di Markup TemplateBinding](templatebinding-markup-extension.md)

`{RelativeSource FindAncestor}` viene usata principalmente in modelli di controllo o composizioni di interfaccia utente Self-contained prevedibile, nei casi in cui un controllo è sempre previsto in un struttura ad albero visuale di un determinato tipo di predecessore. Ad esempio, gli elementi di un controllo di elementi potrebbero utilizzare `FindAncestor` per associarsi alle proprietà del relativo predecessore padre del controllo di elementi. In alternativa, gli elementi che fanno parte della composizione del controllo in un modello possono utilizzare le associazioni `FindAncestor` agli elementi padre nella stessa struttura della composizione.

Nella sintassi dell'elemento oggetto per la modalità `FindAncestor` illustrata nelle sezioni sulla sintassi XAML, la sintassi del secondo elemento oggetto viene utilizzata specificamente per la modalità `FindAncestor`. La modalità `FindAncestor` richiede un valore <xref:System.Windows.Data.RelativeSource.AncestorType%2A>. È necessario impostare <xref:System.Windows.Data.RelativeSource.AncestorType%2A> come un attributo con un [estensione di Markup X:Type](../../xaml-services/x-type-markup-extension.md) riferimento al tipo di predecessore da cercare. Il valore <xref:System.Windows.Data.RelativeSource.AncestorType%2A> viene utilizzato quando la richiesta di associazione viene elaborata in fase di esecuzione.

Per la modalità `FindAncestor`, la proprietà facoltativa <xref:System.Windows.Data.RelativeSource.AncestorLevel%2A> consente di rendere meno ambigua la ricerca del predecessore laddove vi sono più predecessori di questo tipo nella struttura ad albero dell'elemento.

Per ulteriori informazioni su come utilizzare la modalità `FindAncestor`, vedere <xref:System.Windows.Data.RelativeSource>.

`{RelativeSource Self}` è utile per scenari in cui una proprietà di un'istanza deve dipendere dal valore di un'altra proprietà della stessa istanza e alcuna relazione di proprietà di dipendenza generale (ad esempio, la coercizione) già esiste tra queste due proprietà. Sebbene sia raro che esistano due proprietà su un oggetto in modo che i valori letteralmente identici (e dello stesso tipo), è anche possibile applicare una `Converter` parametro per un'associazione con `{RelativeSource Self}`e usare il convertitore per la conversione tra origine e tipi di destinazione. Un altro scenario `{RelativeSource Self}` come parte di un <xref:System.Windows.MultiDataTrigger>.

Ad esempio, nel codice XAML seguente viene definito un elemento <xref:System.Windows.Shapes.Rectangle> in modo che, indipendentemente dal valore inserito per <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.Shapes.Rectangle> sia sempre un quadrato: `<Rectangle Width="200" Height="{Binding RelativeSource={RelativeSource Self}, Path=Width}" .../>`

`{RelativeSource PreviousData}` è utile nei modelli di dati o nei casi in cui le associazioni utilizzano una raccolta come origine dati. È possibile usare `{RelativeSource PreviousData}` per evidenziare le relazioni tra gli elementi di dati adiacenti nella raccolta. Una tecnica correlata consiste nel porre un oggetto <xref:System.Windows.Data.MultiBinding> tra l'elemento corrente e quello precedente nell'origine dati e utilizzare un convertitore su quell'associazione per determinare la differenza tra i due elementi e le relative proprietà.

Nell'esempio riportato di seguito, il primo <xref:System.Windows.Controls.TextBlock> in un modello di elementi visualizza il numero corrente. La seconda <xref:System.Windows.Controls.TextBlock> binding è una <xref:System.Windows.Data.MultiBinding> che nominalmente presenta due <xref:System.Windows.Data.Binding> costituenti: il record corrente e un'associazione che utilizza intenzionalmente il record di dati precedente utilizzando `{RelativeSource PreviousData}`. Quindi, un convertitore applicato a <xref:System.Windows.Data.MultiBinding> calcola la differenza e la restituisce all'associazione.

```xml
<ListBox Name="fibolist">
    <ListBox.ItemTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
            <TextBlock Text="{Binding}"/>
            <TextBlock>, difference = </TextBlock>
                <TextBlock>
                    <TextBlock.Text>
                        <MultiBinding Converter="{StaticResource DiffConverter}">
                            <Binding/>
                            <Binding RelativeSource="{RelativeSource PreviousData}"/>
                        </MultiBinding>
                    </TextBlock.Text>
                </TextBlock>
            </StackPanel>
        </DataTemplate>
    </ListBox.ItemTemplate>
```

Descrizione dell'associazione dati come concetto non viene trattato in questo caso, vedere [Panoramica sul Data Binding](../data/data-binding-overview.md).

Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'implementazione del processore XAML, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.Data.RelativeSource> classe.

`RelativeSource` è un'estensione di markup. Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà. Tutte le estensioni di markup in uso XAML il `{` e `}` caratteri nella sintassi degli attributi, vale a dire la convenzione mediante il quale un processore XAML riconosce che l'attributo deve essere elaborato da un'estensione di markup. Per altre informazioni, vedere [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md)
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Panoramica sulle dichiarazioni di associazione](../data/binding-declarations-overview.md)
- [Estensione di markup x:Type](../../xaml-services/x-type-markup-extension.md)
