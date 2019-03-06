---
title: Refactoring in funzioni Pure (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
ms.openlocfilehash: 0a37b30278c850256355612cec09a4c017c7adc2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379718"
---
# <a name="refactoring-into-pure-functions-visual-basic"></a>Refactoring in funzioni Pure (Visual Basic)

Per le trasformazioni funzionali pure, è fondamentale comprendere come eseguire il refactoring del codice usando funzioni pure.

Come accennato in precedenza, una funzione pura prevede due caratteristiche utili:

- Non ha effetti collaterali. La funzione non cambia le variabili o i dati di qualsiasi tipo all'esterno della funzione.

- È coerente. Dato lo stesso set di dati di input, restituirà sempre lo stesso valore di output.

 Per passare alla programmazione funzionale, è possibile eseguire il refactoring del codice esistente per eliminare inutili effetti collaterali e dipendenze esterne. In questo modo, è possibile creare versioni di funzioni pure del codice esistente.

In questo argomento vengono descritte le caratteristiche presenti e non presenti in una funzione pura. [Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) esercitazione viene illustrato come modificare un documento WordprocessingML e vengono forniti due esempi di come eseguire il refactoring tramite una funzione pura.

## <a name="eliminating-side-effects-and-external-dependencies"></a>Eliminazione di effetti collaterali e dipendenze esterne

Negli esempi seguenti vengono confrontate due funzioni non pure e una funzione pura.

### <a name="non-pure-function-that-changes-a-class-member"></a>Funzione non pura che modifica un membro di classe

Nel codice seguente la funzione `HyphenatedConcat` non è una funzione pura perché modifica il membro dati `aMember` nella classe:

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

L'output del codice è il seguente:

```
StringOne-StringTwo
```

Si noti che è irrilevante se i dati modificati hanno `public` oppure `private` è l'accesso, o un `shared` membro o un membro di istanza. Una funzione pura non modifica i dati all'eterno della funzione.

### <a name="non-pure-function-that-changes-an-argument"></a>Funzione non pura che modifica un argomento

Inoltre, la versione seguente di questa stessa funzione non è pura, perché modifica il contenuto del parametro, `sb`.

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

Questa versione del programma produce lo stesso output della prima versione, perché la funzione `HyphenatedConcat` ha modificato il valore (stato) del primo parametro richiamando la funzione del membro <xref:System.Text.StringBuilder.Append%2A>. Si noti che questa modifica si verifica nonostante il fatto che `HyphenatedConcat` usa il passaggio di parametri in base a chiamata per valore.

> [!IMPORTANT]
> Per i tipi di riferimenti, se un parametro viene passato per valore, il risultato è una copia del riferimento a un oggetto passato. Questa copia è ancora associata agli stessi dati di istanza del riferimento originale, finché la variabile di riferimento non viene assegnata a un nuovo oggetto. La chiamata per riferimento non è necessariamente richiesta affinché una funzione modifichi un parametro.

### <a name="pure-function"></a>Funzione pura

Nella versione successiva del programma viene illustrato come implementare la funzione `HyphenatedConcat` come funzione pura.

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

Anche in questo caso, la versione produce la stessa riga di output: `StringOne-StringTwo` Si noti che per mantenere il valore concatenato, viene archiviato nella variabile intermedia `s2`.

Un approccio che può risultare utile consiste nello scrivere funzioni localmente non pure, ossia che dichiarano e modificano variabili locali, ma globalmente pure. Tali funzioni presentano molte caratteristiche utili in termini di componibilità, ma evitano alcune delle complessità dei linguaggi di programmazione funzionali, ad esempio la necessità di usare la ricorsione quando con un semplice ciclo si otterrebbe lo stesso risultato.

## <a name="standard-query-operators"></a>Operatori di query standard

Una caratteristica importante degli operatori di query standard è che vengono implementati come funzioni pure.

Per altre informazioni, vedere [panoramica degli operatori di Query Standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

## <a name="see-also"></a>Vedere anche

- [Introduzione alle trasformazioni funzionali Pure (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Differenze tra programmazione funzionale e Programmazione imperativa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
