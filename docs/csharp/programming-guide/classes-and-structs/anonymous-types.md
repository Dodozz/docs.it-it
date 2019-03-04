---
title: Tipi anonimi - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#]
- C# Language, anonymous types
ms.assetid: 59c9d7a4-3b0e-475e-b620-0ab86c088e9b
ms.openlocfilehash: 165793155aabac23245b352959be3188b0a5a6e5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971169"
---
# <a name="anonymous-types-c-programming-guide"></a>Tipi anonimi (Guida per programmatori C#)
I tipi anonimi offrono un modo pratico per incapsulare un set di proprietà di sola lettura in un singolo oggetto, senza dover definire prima un tipo in modo esplicito. Il nome del tipo viene generato dal compilatore e non è disponibile a livello di codice sorgente. Il tipo di ogni proprietà è dedotto dal compilatore.  
  
 Per creare tipi anonimi, si usa l'operatore [new](../../../csharp/language-reference/keywords/new.md) insieme a un inizializzatore di oggetto. Per altre informazioni sugli inizializzatori di oggetto, vedere [Inizializzatori di oggetto e di raccolte](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
 L'esempio seguente mostra un tipo anonimo inizializzato con due proprietà denominate `Amount` e `Message`.  
  
```csharp  
var v = new { Amount = 108, Message = "Hello" };  
  
// Rest the mouse pointer over v.Amount and v.Message in the following  
// statement to verify that their inferred types are int and string.  
Console.WriteLine(v.Amount + v.Message);  
```  
  
 I tipi anonimi vengono in genere usati nella clausola [select](../../../csharp/language-reference/keywords/select-clause.md) di un'espressione di query per restituire un subset delle proprietà da ogni oggetto della sequenza di origine. Per altre informazioni, vedere le [espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
 I tipi anonimi contengono una o più proprietà pubbliche di sola lettura. Non sono validi altri tipi di membri della classe, ad esempio metodi o eventi. L'espressione usata per inizializzare una proprietà non può essere `null`, una funzione anonima o un tipo di puntatore.  
  
 Lo scenario più comune consiste nell'inizializzare un tipo anonimo con proprietà di un altro tipo. Nell'esempio seguente si presuppone l'esistenza di una classe denominata `Product`. La classe `Product` include le proprietà `Color` e `Price`, insieme ad altre proprietà non pertinenti. La variabile `products` è una raccolta di oggetti `Product`. La dichiarazione di tipo anonimo inizia con la parola chiave `new`. La dichiarazione inizializza un nuovo tipo che usa solo due proprietà della classe `Product`. In questo modo la query restituisce una quantità di dati inferiore.  
  
 Se nel tipo anonimo non si specificano i nomi dei membri, il compilatore assegna ai membri di tipo anonimo lo stesso nome della proprietà usata per inizializzarli. Per una proprietà inizializzata con un'espressione è necessario fornire un nome, come illustrato nell'esempio seguente. Nell'esempio seguente i nomi delle proprietà del tipo anonimo sono `Color` e `Price`.  
  
 [!code-csharp[csRef30Features#81](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csRef30Features/CS/csref30.cs#81)]  
  
 In genere, quando si usa un tipo anonimo per inizializzare una variabile, è necessario dichiarare la variabile come locale tipizzata in modo implicito tramite [var](../../../csharp/language-reference/keywords/var.md). Il nome del tipo non può essere specificato nella dichiarazione di variabile, perché solo il compilatore ha accesso al nome sottostante del tipo anonimo. Per altre informazioni su `var`, vedere [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 È possibile creare una matrice di elementi tipizzati in modo anonimo combinando una variabile locale tipizzata in modo implicito e una matrice tipizzata in modo implicito, come illustrato nell'esempio seguente.  
  
```csharp  
var anonArray = new[] { new { name = "apple", diam = 4 }, new { name = "grape", diam = 1 }};  
```  
  
## <a name="remarks"></a>Osservazioni  
 I tipi anonimi sono tipi [class](../../../csharp/language-reference/keywords/class.md) che derivano da un tipo [object](../../../csharp/language-reference/keywords/object.md) e dei quali non può essere eseguito il cast ad alcun tipo, eccetto al tipo [object](../../../csharp/language-reference/keywords/object.md). Il compilatore fornisce un nome per qualsiasi tipo anonimo, anche se l'applicazione non può accedervi. Dal punto di vista di Common Language Runtime, un tipo anonimo non è diverso da qualsiasi altro tipo di riferimento.  
  
 Se due o più inizializzatori di oggetti anonimi in un assembly specificano una sequenza di proprietà nello stesso ordine e con gli stessi nomi e tipi, il compilatore considera gli oggetti come istanze dello stesso tipo. Condividono le stesse informazioni sul tipo generate dal compilatore.  
  
 Non è possibile dichiarare un campo, una proprietà, un evento o il tipo restituito di un metodo specificando un tipo anonimo. In modo analogo, non è possibile dichiarare un parametro formale di un metodo, una proprietà, un costruttore o un indicizzatore specificando un tipo anonimo. Per passare un tipo anonimo o una raccolta contenente tipi anonimi come argomento a un metodo, è possibile dichiarare il parametro come oggetto di tipo. In questo modo si annulla tuttavia lo scopo della tipizzazione forte. Se è necessario archiviare i risultati delle query o passarli oltre i limiti del metodo, si consideri l'uso di uno struct o una classe con nome normale invece di un tipo anonimo.  
  
 I metodi <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A> nei tipi anonimi sono definiti in termini di metodi delle proprietà `Equals` e `GetHashCode`, di conseguenza due istanze dello stesso tipo anonimo sono uguali solo se tutte le relative proprietà sono uguali.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
- [Nozioni di base su LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
