---
title: Stringhe interpolate (Visual Basic)
ms.date: 10/31/2017
ms.openlocfilehash: 408f3232258b3b4c7fe6ec160149f8ac70b84b03
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610678"
---
# <a name="interpolated-strings-visual-basic-reference"></a>Stringhe interpolate (riferimenti di Visual Basic)

Vengono usate per la costruzione di stringhe.  Una stringa interpolata è simile a una stringa di modello che contiene *espressioni interpolate*.  Una stringa interpolata restituisce una stringa che sostituisce le espressioni interpolate in essa contenute con le rappresentazioni di stringa. Questa funzionalità è disponibile in Visual Basic 14 e versioni successive.

Gli argomenti di una stringa interpolata sono più facili da comprendere rispetto a una [stringa di formato composito](../../../../standard/base-types/composite-formatting.md#composite-format-string).  Ad esempio, la stringa interpolata

```vb
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```

contiene due espressioni interpolate, '{name}' e '{hours: hh}'. La stringa di formato composito equivalente è:

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours);
```

La struttura di una stringa interpolata è:

```vb
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."
```

dove:

- *field-width* è un intero con segno che indica il numero di caratteri nel campo. Se è positivo, il campo viene allineato a destra; se è negativo, viene allineato a sinistra.

- *format-string* è una stringa di formato appropriata per il tipo di oggetto formattato. Ad esempio, per un <xref:System.DateTime> valore, può trattarsi di un [stringa di formato data e ora standard](~/docs/standard/base-types/standard-date-and-time-format-strings.md) , ad esempio "D" o "d".

> [!IMPORTANT]
> Tra `$` e il simbolo `"` all'inizio della stringa non possono essere presenti spazi vuoti, In questo modo, un errore del compilatore.

È possibile usare una stringa interpolata ovunque sia possibile usare un valore letterale stringa.  La stringa interpolata viene valutata ogni volta che si esegue codice con la stringa interpolata. Ciò consente di separare la definizione e la valutazione di una stringa interpolata.

Per includere una parentesi graffa ("{" o "}") in una stringa interpolata, digitarne due, ovvero "{{" o "}}".  Per altri dettagli, vedere la sezione Conversioni implicite.

Se la stringa interpolata contiene altri caratteri con un significato speciale in una stringa interpolata, ad esempio virgolette doppie ("), due punti (:) o virgola (,), è necessario specificare il carattere di escape se si presentano nel testo letterale, oppure inserirli in un'espressione racchiusa tra parentesi se sono elementi del linguaggio inclusi in un'espressione interpolata. Nell'esempio seguente viene specificato il carattere di escape delle virgolette per includerle nella stringa di risultato e si usano le parentesi per delimitare l'espressione `(age == 1 ? "" : "s")` in modo che i due punti non vengano interpretati come l'inizio di una stringa di formato.

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]

## <a name="implicit-conversions"></a>Conversioni implicite

Da una stringa interpolata vengono effettuate tre conversioni di tipo implicito:

1. Conversione di una stringa interpolata in una <xref:System.String>. L'esempio seguente restituisce una stringa in cui le espressioni di stringa interpolata sono state sostituite con le rappresentazioni di stringa. Ad esempio:

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]

   Questo è il risultato finale di un'interpretazione della stringa. Tutte le occorrenze delle parentesi graffe doppie ("{{" e "}}") vengono convertite in parentesi graffe singole.

2. Conversione di una stringa interpolata in una variabile <xref:System.IFormattable> che consente di creare più stringhe risultato con contenuto specifico delle impostazioni cultura da una singola istanza di <xref:System.IFormattable>. Ciò è utile per includere elementi quali i formati numerici e di data corretti per singole impostazioni cultura.  Tutte le occorrenze di parentesi graffe doppie ("{{" e "}}") rimangono tali finché la stringa non viene formattata in modo implicito o esplicito chiamando il metodo <xref:System.Object.ToString>.  Tutte le espressioni di interpolazione contenute vengono convertite in {0}, {1}e così via.

   Nell'esempio seguente viene usata la reflection per visualizzare i membri, nonché i valori di campi e le proprietà di una variabile <xref:System.IFormattable> creata da una stringa interpolata. Viene anche passata la variabile <xref:System.IFormattable> al metodo <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>.

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]

   Si noti che la stringa interpolata può essere controllata solo tramite reflection. Se viene passata a un metodo di formattazione delle stringhe, ad esempio <xref:System.Console.WriteLine(System.String)>, gli elementi di formato vengono risolti e viene restituita la stringa risultato.

3. Conversione di una stringa interpolata in una <xref:System.FormattableString> variabile che rappresenta una stringa di formato composito. Grazie all'esame della stringa di formato composito e del modo in cui viene eseguito il rendering come stringa di risultato, è ad esempio possibile attuare misure di protezione contro attacchi di tipo injection durante la creazione di una query. Oggetto <xref:System.FormattableString> include anche:

      - Un overload <xref:System.FormattableString.ToString> che produce una stringa risultato per <xref:System.Globalization.CultureInfo.CurrentCulture>.

      - Oggetto <xref:System.FormattableString.Invariant%2A> metodo che genera una stringa per il <xref:System.Globalization.CultureInfo.InvariantCulture>.

      - Un metodo <xref:System.FormattableString.ToString(System.IFormatProvider)> che produce una stringa risultato per impostazioni cultura specifiche.

    Tutte le occorrenze delle parentesi graffe doppie ("{{" e "}}") rimangono invariate tra parentesi graffe doppie finché non viene formattata.  Tutte le espressioni di interpolazione contenute vengono convertite in {0}, {1}e così via.

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]

## <a name="see-also"></a>Vedere anche

- <xref:System.IFormattable?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- [Riferimenti per il linguaggio Visual Basic](index.md)
