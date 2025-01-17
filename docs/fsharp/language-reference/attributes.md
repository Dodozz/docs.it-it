---
title: Attributi
description: Informazioni su come F# attributi abilitano i metadati da applicare a un costrutto di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: fed4c549b95d6d3701ab81cf5d62add411c16038
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642032"
---
# <a name="attributes"></a>Attributi

Gli attributi abilitano i metadati da applicare a un costrutto di programmazione.

## <a name="syntax"></a>Sintassi

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>Note

Nella sintassi precedente, il *destinazione* è facoltativo e, se presente, specifica il tipo di entità del programma a cui si applica l'attributo. I valori validi per *destinazione* vengono visualizzati nella tabella riportata più avanti in questo documento.

Il *-nome dell'attributo* fa riferimento al nome (possibilmente qualificato con spazi dei nomi) di un tipo di attributo valido, con o senza il suffisso `Attribute` che in genere viene usato nei nomi di tipo di attributo. Ad esempio, il tipo `ObsoleteAttribute` può essere abbreviato semplicemente `Obsolete` in questo contesto.

Il *argomenti* include gli argomenti del costruttore per il tipo di attributo. Se un attributo ha un costruttore predefinito, è possono omettere l'elenco di argomenti e le parentesi. Gli attributi supportano entrambi gli argomenti posizionali e gli argomenti denominati. *Gli argomenti posizionali* sono argomenti che vengono usati nell'ordine in cui vengono visualizzati. Argomenti denominati possono essere utilizzati se l'attributo ha le proprietà pubbliche. È possibile impostare tali informazioni tramite la sintassi seguente nell'elenco di argomenti.

```
*property-name* = *property-value*
```

Le inizializzazioni tali proprietà possono essere in qualsiasi ordine, ma devono seguire gli argomenti posizionali. Ecco un esempio di un attributo che usa argomenti posizionali e inizializzazioni delle proprietà.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

In questo esempio, l'attributo è `DllImportAttribute`, qui utilizzato nella sua forma abbreviata. Il primo argomento è un parametro posizionale e la seconda è una proprietà.

Gli attributi sono un costrutto di programmazione .NET che consente a un oggetto noto come un *attributo* da associare a un tipo o altro elemento del programma. L'elemento del programma a cui viene applicato un attributo è noto come il *destinazione dell'attributo*. L'attributo contiene in genere i metadati relativi al valore di destinazione. In questo contesto, i metadati può essere tutti i dati sul tipo diverso da relativi campi e i membri.

Gli attributi F# può essere applicato a costrutti di programmazione seguenti: funzioni, metodi, assembly, moduli, tipi (classi, record, strutture, interfacce, delegati, enumerazioni, unioni e così via), costruttori, proprietà, campi, i parametri, parametri di tipo e i valori restituiti. Atributy nejsou povolené. su `let` associazioni all'interno di classi, le espressioni o espressioni del flusso di lavoro.

In genere, la dichiarazione di attributo viene visualizzata direttamente prima della dichiarazione dell'attributo di destinazione. Più dichiarazioni di attributo sono utilizzabile tra loro, come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

È possibile eseguire una query degli attributi in fase di esecuzione usando la reflection .NET.

È possibile dichiarare più attributi singolarmente, come nell'esempio di codice precedente, oppure è possibile dichiararli in un set di parentesi, se si usa un punto e virgola per separare i singoli attributi e i costruttori, come illustrato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

In genere, gli attributi includono il `Obsolete` attributo, gli attributi per considerazioni sulla sicurezza, gli attributi per il supporto COM, gli attributi relativi alla proprietà del codice e gli attributi che indica se un tipo può essere serializzato. Nell'esempio seguente viene illustrato l'utilizzo del `Obsolete` attributo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

Per le destinazioni degli attributi `assembly` e `module`, applicare gli attributi a un livello superiore `do` binding dell'assembly. È possibile includere la parola `assembly` o `module` nella dichiarazione di attributo, come indicato di seguito.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

Se si omette l'attributo di destinazione per un attributo applicato a un `do` binding, il F# compilatore prova a determinare l'attributo di destinazione appropriato per quell'attributo. Molte classi di attributo dispongono di un attributo di tipo `System.AttributeUsageAttribute` che include informazioni sulle possibili destinazioni supportate per l'attributo. Se il `System.AttributeUsageAttribute` indica che l'attributo supporta le funzioni come destinazione, l'attributo proviene da applicare al punto di ingresso principale del programma. Se il `System.AttributeUsageAttribute` indica che l'attributo supporta gli assembly come destinazioni, il compilatore prende l'attributo da applicare all'assembly. La maggior parte degli attributi non si applicano a entrambe le funzioni e assembly, ma in casi in cui avviene l'attributo non viene eseguito da applicare alla funzione principale del programma. Se l'attributo di destinazione viene specificato in modo esplicito, l'attributo viene applicato alla destinazione specificata.

Sebbene non sia in genere necessario specificare l'attributo di destinazione in modo esplicito, i valori validi per *destinazione* in un attributo vengono visualizzate nella tabella seguente, insieme a esempi di utilizzo.

<table>
  <tr>
    <th>Attributo di destinazione</td>
    <th>Esempio</td> 
  </tr>
  <tr>
    <td>assembly</td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]<code></pre></td> 
  </tr>
  <tr>
    <td>return</td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1<code></pre></td> 
  </tr>
  <tr>
    <td>campo</td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int<code></pre></td> 
  </tr>
  <tr>
    <td>proprietà</td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x<code></pre></td> 
  </tr>
  <tr>
    <td>param</td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10<code></pre></td> 
  </tr>
  <tr>
    <td>tipo</td>
    <td>
        <pre lang="fsharp"><code>
        [&lt;type: StructLayout(Sequential)&gt;] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        <code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
