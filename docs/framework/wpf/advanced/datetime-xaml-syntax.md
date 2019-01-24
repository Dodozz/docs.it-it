---
title: Sintassi DateTime XAML
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: c443451a0fd9fffec97377efc611e0ccfe534f06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606725"
---
# <a name="datetime-xaml-syntax"></a>Sintassi DateTime XAML
Alcuni controlli, ad esempio <xref:System.Windows.Controls.Calendar> e <xref:System.Windows.Controls.DatePicker>, hanno proprietà che usano il <xref:System.DateTime> tipo. Anche se una data o un'ora iniziale per questi controlli viene in genere specificata nel code-behind in fase di esecuzione, è possibile specificare una data o un'ora iniziale in XAML. Il parser XAML WPF gestisce analisi di <xref:System.DateTime> i valori usando una sintassi del testo XAML predefinita. In questo argomento vengono descritte le specifiche del <xref:System.DateTime> sintassi del testo XAML.  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Quando usare la sintassi DateTime XAML  
 Impostare le date in XAML non è sempre necessario e può anche non essere appropriato. Ad esempio, è possibile usare il <xref:System.DateTime.Now%2A?displayProperty=nameWithType> proprietà per l'inizializzazione di una data in fase di esecuzione oppure è stato possibile eseguire tutte le modifiche alla data di un calendario nel code-behind in base all'input utente. Tuttavia, esistono scenari in cui è possibile per le date come hardcoded in un <xref:System.Windows.Controls.Calendar> e <xref:System.Windows.Controls.DatePicker> in un modello di controllo. Il <xref:System.DateTime> sintassi XAML deve essere utilizzata per questi scenari.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>La sintassi DateTime di XAML è un comportamento nativo  
 <xref:System.DateTime> è una classe definita nelle librerie di classi base di CLR. A causa di librerie di classi base correlazione tra il resto di CLR, non è possibile applicare <xref:System.ComponentModel.TypeConverterAttribute> alla classe e usare un convertitore di tipi per elaborare le stringhe da XAML e convertirle in <xref:System.DateTime> nel modello a oggetti fase di esecuzione. Non esiste una classe `DateTimeConverter` che fornisce il comportamento di conversione. Il comportamento di conversione descritto in questo argomento è nativo del parser XAML WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Stringhe di formato per la sintassi DateTime XAML  
 È possibile specificare il formato di un <xref:System.DateTime> con una stringa di formato. Le stringhe di formato formalizzano la sintassi del testo che può essere usata per creare un valore. <xref:System.DateTime> i valori per i controlli WPF utilizzano in genere solo i componenti della data di <xref:System.DateTime> e non i componenti della fase.  
  
 Quando si specifica un <xref:System.DateTime> in XAML, è possibile usare una delle stringhe di formato in modo intercambiabile.  
  
 È anche possibile usare formati e stringhe di formato non illustrati in maniera specifica in questo argomento. Tecnicamente, il XAML per qualsiasi <xref:System.DateTime> valore è specificato e analizzato dal parser XAML WPF Usa una chiamata interna a <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, pertanto è possibile usare qualsiasi stringa accettata da <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> per il XAML di input. Per altre informazioni, vedere <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  La sintassi DateTime XAML Usa sempre `en-us` come il <xref:System.Globalization.CultureInfo> per la conversione nativa. Non è influenzato dal <xref:System.Windows.FrameworkElement.Language%2A> valore o `xml:lang` valore in XAML, in quanto la conversione di tipo a livello di attributo XAML funziona senza quel contesto. Non tentare di interpolare le stringhe di formato mostrate qui a causa di variazioni relative alla lingua, come l'ordine di visualizzazione di giorno e mese. Le stringhe di formato mostrate qui sono le stringhe di formato esatte usate durante l'analisi del codice XAML indipendentemente dalle altre impostazioni cultura.  
  
 Le sezioni seguenti descrivono alcune delle comuni <xref:System.DateTime> stringhe di formato.  
  
### <a name="short-date-pattern-d"></a>Schema di data breve ("d")  
 Di seguito viene illustrato il formato di data breve per un <xref:System.DateTime> in XAML:  
  
 `M/d/YYYY`  
  
 Questo è il formato più semplice che specifica tutte le informazioni necessarie per gli utilizzi tipici per i controlli WPF e non è influenzato dalle differenze di fuso orario rispetto a un componente relativo all'ora, quindi è consigliato rispetto altri formati.  
  
 Ad esempio, per specificare la data del 1 giugno 2010, usare la stringa seguente:  
  
 `3/1/2010`  
  
 Per altre informazioni, vedere <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Schema di data/ora ordinabile ("s")  
 Di seguito è riportato l'ordinabile <xref:System.DateTime> modello in XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Ad esempio, per specificare la data del 1 giugno 2010, usare la stringa seguente (tutti i componenti relativi all'ora vengono immessi come 0):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Schema RFC1123 ("r")  
 Il modello RFC1123 è utile perché potrebbe essere un input di stringa da altri generatori di data che usano il modello RFC1123 per via delle impostazioni cultura invariabili. Di seguito viene illustrata la specifica RFC1123 <xref:System.DateTime> modello in XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Ad esempio, per specificare la data del 1 giugno 2010, usare la stringa seguente (tutti i componenti relativi all'ora vengono immessi come 0):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Altri formati e modelli  
 Come affermato in precedenza, una <xref:System.DateTime> in XAML può essere specificato come qualsiasi stringa accettabile come input per <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Ciò include gli altri formati formalizzati (ad esempio <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) e i formati che non sono formalizzati come un particolare <xref:System.Globalization.DateTimeFormatInfo> form. Ad esempio, il modulo `YYYY/mm/dd` è accettabile come input per <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Questo argomento non tenta di descrivere tutti i possibili formati che funzionano e invece consiglia il formato di data breve come pratica standard.  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
