---
title: Costruttori statici - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: f053a74fcb87971506b83ca8ca2076517ddddf56
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307099"
---
# <a name="static-constructors-c-programming-guide"></a>Costruttori statici (Guida per programmatori C#)
Un costruttore statico consente di inizializzare gli eventuali dati [static](../../../csharp/language-reference/keywords/static.md) oppure di eseguire un'operazione specifica che deve essere effettuata una sola volta. Viene chiamato automaticamente prima che ne venga creata la prima istanza o venga fatto riferimento a qualsiasi membro statico.  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
 
## <a name="remarks"></a>Osservazioni
I costruttori statici hanno le proprietà seguenti:  
  
- Un costruttore statico non accetta modificatori di accesso e non ha parametri.  

- Una classe o struct può avere solo un costruttore statico.

- I costruttori statici non possono essere ereditati e non è possibile eseguirne l'overload.

- Un costruttore statico non può essere chiamato direttamente ed è progettato esclusivamente per essere chiamato da Common Language Runtime (CLR). Viene richiamato automaticamente.

- L'utente non può controllare in alcun modo il momento in cui il costruttore statico viene eseguito nel programma.
  
- Un costruttore statico viene chiamato automaticamente per inizializzare la [classe](../../../csharp/language-reference/keywords/class.md) prima che ne venga creata la prima istanza o venga fatto riferimento a qualsiasi membro statico. Un costruttore statico verrà eseguito prima di un costruttore di istanza. Si noti che il costruttore statico di un tipo viene chiamato quando un metodo statico assegnato a un evento o un delegato viene chiamato, e non quando tale metodo viene assegnato. Gli eventuali inizializzatori variabili di campo statico presenti nella classe del costruttore statico verranno eseguiti nell'ordine testuale in cui appaiono nella dichiarazione della classe subito prima dell'esecuzione del costruttore statico.

- Se non si specifica un costruttore statico per inizializzare campi statici, tutti i campi statici vengono inizializzati sul relativo valore predefinito come indicato nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md). 
  
- Se un costruttore statico genera un'eccezione, il runtime non lo chiamerà una seconda volta e il tipo rimarrà non inizializzato per la durata del dominio dell'applicazione in cui il programma è in esecuzione. Viene più comunemente generata un'eccezione <xref:System.TypeInitializationException> quando un costruttore statico non è in grado di creare un'istanza di un tipo o per un'eccezione non gestita che si verifica all'interno di un costruttore statico. Per i costruttori statici impliciti che non sono definiti in modo esplicito nel codice sorgente, la risoluzione dei problemi può richiedere l'ispezione del codice IL (Intermediate Language).

- La presenza di un costruttore statico impedisce l'aggiunta dell'attributo di tipo <xref:System.Reflection.TypeAttributes.BeforeFieldInit>. Ciò limita l'ottimizzazione in fase di esecuzione.

- Un campo dichiarato come `static readonly` può essere assegnato solo come parte della relativa dichiarazione o in un costruttore statico. Quando non è richiesto un costruttore statico esplicito, inizializzare i campi statici in fase di dichiarazione, anziché tramite un costruttore statico per una migliore ottimizzazione in fase di esecuzione.

> [!Note]
> Anche se non è direttamente accessibile, la presenza di un costruttore statico esplicito deve essere documentata per facilitare la risoluzione dei problemi relativi alle eccezioni di inizializzazione.

### <a name="usage"></a>Utilizzo

- In genere, i costruttori statici sono usati per scrivere voci nel file di log, quando alla classe è associato un file di log.  
- I costruttori statici risultano utili anche durante la creazione di classi wrapper per il codice non gestito, quando il costruttore può chiamare il metodo `LoadLibrary`.  

- I costruttori statici sono anche un modo pratico per applicare controlli di runtime al parametro di tipo che non può essere controllato in fase di compilazione tramite i vincoli (vincoli del parametro di tipo).

## <a name="example"></a>Esempio
 In questo esempio la classe `Bus` ha un costruttore statico. Quando viene creata la prima istanza di `Bus` (`bus1`), il costruttore statico viene chiamato per inizializzare la classe. L'output dell'esempio verifica che il costruttore statico venga eseguito una sola volta, anche se vengono create due istanze di `Bus`, e che venga eseguito prima del costruttore di istanze.  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]
 
## <a name="c-language-specification"></a>Specifiche del linguaggio C#
Per altre informazioni, vedere la sezione [Costruttori statici](~/_csharplang/spec/classes.md#static-constructors) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md)
- [Linee guida per la progettazione di costruttori](../../../standard/design-guidelines/constructor.md#type-constructor-guidelines)
- [Avviso di sicurezza - CA2121: I costruttori statici devono essere privati](https://docs.microsoft.com/en-us/visualstudio/code-quality/ca2121-static-constructors-should-be-private)
