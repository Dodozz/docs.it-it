---
title: Istruzioni - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- statements [C#], about statements
- C# language, statements
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
ms.openlocfilehash: 232368d2b019b8c265bbb48bd197776f9e03a132
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971507"
---
# <a name="statements-c-programming-guide"></a>Istruzioni (Guida per programmatori C#)
Le azioni accettate da un programma vengono espresse in istruzioni. Le azioni comuni includono la dichiarazione di variabili, l'assegnazione di valori, le chiamate ai metodi, il ciclo delle raccolte e la creazione di rami tra blocchi di codice, a seconda di una data condizione. L'ordine in cui vengono le istruzioni eseguite in un programma viene chiamato "flusso di controllo" o "flusso di esecuzione". Il flusso di controllo può variare ogni volta che viene eseguito un programma, a seconda della reazione del programma all'input ricevuto in fase di esecuzione.  
  
 Un'istruzione può essere costituito da una singola riga di codice che termina con un punto e virgola o da una serie di istruzioni a riga singola in un blocco. Un blocco di istruzioni è racchiuso tra parentesi {} e può contenere blocchi annidati. Il codice seguente mostra due esempi di istruzioni a riga singola e un blocco di istruzioni a più righe:  
  
 [!code-csharp[csProgGuideStatements#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#1)]  
  
## <a name="types-of-statements"></a>Tipi di istruzioni  
 Nella tabella seguente sono elencati i vari tipi di istruzioni in C# e le parole chiave associate, con link ad argomenti contenenti maggiori informazioni:  
  
|Category|Parole chiave C#/note|  
|--------------|---------------------------|  
|[Istruzioni di dichiarazione](#declaration-statements)|Un'istruzione di dichiarazione introduce una nuova variabile o costante. Una dichiarazione di variabile può facoltativamente assegnare un valore alla variabile. In una dichiarazione di costante, l'assegnazione è necessaria.|  
|[Istruzioni di espressione](expressions.md)|Le istruzioni di espressione che calcolano un valore devono archiviare il valore in una variabile. Per altre informazioni, vedere [Istruzioni di espressione](#expression-statements).|  
|[Istruzioni di selezione](../../../csharp/language-reference/keywords/selection-statements.md)|Le istruzioni di selezione consentono di creare un ramo tra le diverse sezioni di codice, in base a una o più condizioni specificate. Per altre informazioni, vedere i seguenti argomenti:<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|[Istruzioni di iterazione](../../../csharp/language-reference/keywords/iteration-statements.md)|Le istruzioni di iterazione consentono di eseguire un ciclo tra le raccolte come matrici o eseguono ripetutamente lo stesso set di istruzioni finché non viene soddisfatta una condizione specificata. Per altre informazioni, vedere i seguenti argomenti:<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|[Istruzioni di salto](../../../csharp/language-reference/keywords/jump-statements.md)|Le istruzioni di salto trasferiscono il controllo a un'altra sezione di codice. Per altre informazioni, vedere i seguenti argomenti:<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|[Istruzioni di gestione delle eccezioni](../../../csharp/language-reference/keywords/exception-handling-statements.md)|Le istruzioni di gestione delle eccezioni consentono di recuperare condizioni eccezionali che si verificano in fase di esecuzione. Per altre informazioni, vedere i seguenti argomenti:<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try-catch](../../../csharp/language-reference/keywords/try-catch.md), [try-finally](../../../csharp/language-reference/keywords/try-finally.md), [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[Checked e Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|Le istruzioni Checked e Unchecked consentono di specificare se le operazioni numeriche possono provocare un overflow quando il risultato viene archiviato in una variabile troppo piccola per contenere il valore risultante. Per altre informazioni, vedere [checked](../../../csharp/language-reference/keywords/checked.md) e [unchecked](../../../csharp/language-reference/keywords/unchecked.md).|  
|Istruzione `await`|Se si contrassegna un metodo con il modificatore [async](../../../csharp/language-reference/keywords/async.md) , è possibile usare l'operatore [await](../../../csharp/language-reference/keywords/await.md) nel metodo. Quando il controllo raggiunge un'espressione `await` nel metodo asincrono, il controllo torna al chiamante e l'avanzamento nel metodo viene sospeso fino al completamento dell'attività attesa. Una volta completata l'attività, l'esecuzione del metodo può riprendere.<br /><br /> Per un esempio semplice, vedere la sezione "Metodi asincroni" in [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md). Per altre informazioni, vedere [Programmazione asincrona con async e await](../../../csharp/programming-guide/concepts/async/index.md).|  
|Istruzione `yield return`|Un iteratore esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o una matrice. Un iteratore usa l'istruzione [yield return](../../../csharp/language-reference/keywords/yield.md) per restituire un elemento per volta. Quando viene raggiunta un'istruzione `yield return`, la posizione corrente nel codice viene memorizzata. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamato l'iteratore.<br /><br /> Per altre informazioni, vedere [Iteratori](../../../csharp/programming-guide/concepts/iterators.md).|  
|Istruzione `fixed`|L'istruzione fixed impedisce che il Garbage Collector esegua la rilocazione di una variabile mobile. Per altre informazioni, vedere [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).|  
|Istruzione `lock`|L'istruzione lock consente di limitare l'accesso ai blocchi di codice a un solo thread per volta. Per altre informazioni, vedere [lock](../../../csharp/language-reference/keywords/lock-statement.md).|  
|Istruzioni con etichetta|È possibile assegnare un'etichetta a un'istruzione e quindi usare la parola chiave [goto](../../../csharp/language-reference/keywords/goto.md) per passare all'istruzione con etichetta. Vedere l'esempio nell'argomento seguente.|  
|[Istruzione vuota](#the-empty-statement)|L'istruzione vuota è costituita da un singolo punto e virgola. Non esegue alcuna operazione e può essere usata in posizioni in cui è richiesta un'istruzione ma non deve essere eseguita alcuna azione.|  
  
## <a name="declaration-statements"></a>Istruzioni di dichiarazione

Il codice seguente illustra esempi di dichiarazioni di variabili con e senza un'assegnazione iniziale e una dichiarazione di costante con le inizializzazioni necessarie.

 [!code-csharp[csProgGuideStatements#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#23)]

## <a name="expression-statements"></a>Istruzioni di espressione

Il codice seguente illustra esempi di istruzioni di espressione, tra cui assegnazione, creazione di oggetti con assegnazione, e la chiamata al metodo.

 [!code-csharp[csProgGuideStatements#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#24)]

## <a name="the-empty-statement"></a>Istruzione vuota

Gli esempi seguenti illustrano due usi di un'istruzione vuota:

 [!code-csharp[csProgGuideStatements#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#25)]

## <a name="embedded-statements"></a>Istruzioni incorporate

 Alcune istruzioni, fra cui [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) e [foreach](../../../csharp/language-reference/keywords/foreach-in.md), dispongono sempre di un'istruzione incorporata che le segue. Questa istruzione incorporata può essere una singola istruzione o più istruzioni racchiuse tra parentesi {} in un blocco di istruzioni. Anche le istruzioni incorporate a riga singola possono essere racchiuse tra parentesi {}, come illustrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideStatements#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#26)]  
  
 Un'istruzione incorporata non racchiusa tra parentesi {} non può essere un'istruzione di dichiarazione o un'istruzione con etichetta. Questa operazione è illustrata nell'esempio seguente:  
  
 [!code-csharp[csProgGuideStatements#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#27)]  
  
 Inserire l'istruzione incorporata in un blocco per correggere l'errore:  
  
 [!code-csharp[csProgGuideStatements#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#28)]  
  
## <a name="nested-statement-blocks"></a>Blocchi di istruzioni annidate  
 I blocchi di istruzioni possono essere annidati, come illustrato nel codice seguente:  
  
 [!code-csharp[csProgGuideStatements#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#29)]  
  
## <a name="unreachable-statements"></a>Istruzioni non raggiungibili  
 Se il compilatore determina che il flusso di controllo non può raggiungere mai una particolare istruzione in nessuna circostanza, genererà l'avviso CS0162, come illustrato nell'esempio seguente:  
  
 [!code-csharp[csProgGuideStatements#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#22)]  
  
## <a name="related-sections"></a>Sezioni correlate  
  
-   [Parole chiave per le istruzioni](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
-   [Espressioni](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
-   [Operatori](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
