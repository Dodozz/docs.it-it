---
title: Inizializzatori di oggetto e di raccolte - Guida per programmatori C#
ms.custom: seodec18
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: bd49834c45f6e07a99be5a1f4293e938eed2cc77
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267718"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a>Inizializzatori di oggetto e di raccolte (Guida per programmatori C#)

C# consente di creare un'istanza di un oggetto o di una raccolta e di eseguire le assegnazioni di membri in un'unica istruzione.

## <a name="object-initializers"></a>Inizializzatori di oggetto

Gli inizializzatori di oggetto consentono di assegnare valori a qualsiasi proprietà o campo accessibile di un oggetto in fase di creazione senza dover richiamare un costruttore seguito da righe di istruzioni di assegnazione. La sintassi dell'inizializzatore di oggetto consente di specificare gli argomenti per un costruttore o di omettere gli argomenti (e la sintassi di parentesi).  Nell'esempio seguente viene illustrato come usare un inizializzatore di oggetto con un tipo denominato, `Cat` e come richiamare il costruttore senza parametri. Si noti l'uso di proprietà implementate automaticamente nella classe `Cat`. Per altre informazioni, vedere [Proprietà implementate automaticamente](auto-implemented-properties.md).  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  
 
La sintassi degli inizializzatori di oggetto consente di creare un'istanza e dopo assegna l'oggetto appena creato, con le relative proprietà assegnate, alla variabile nell'assegnazione.

A partire da C# 6, gli inizializzatori di oggetto possono impostare gli indicizzatori, oltre ad assegnare campi e proprietà. Si consideri questa classe `Matrix` di base:

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

È possibile inizializzare la matrice di identità con il codice seguente:

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

Qualsiasi indicizzatore accessibile che contiene un setter accessibile è utilizzabile come espressione in un inizializzatore di oggetto, indipendentemente dal numero o dai tipi degli argomenti. Gli argomenti di indice formano il lato sinistro dell'assegnazione e il valore corrisponde al lato destro dell'espressione.  Questi, ad esempio sono tutti validi se `IndexersExample` ha gli indicizzatori appropriati:

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

Perché la compilazione del codice precedente riesca, il tipo `IndexersExample` deve avere i membri seguenti:

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a>Inizializzatori di oggetto con tipi anonimi

Anche se gli inizializzatori di oggetto possono essere usati in qualsiasi contesto, sono particolarmente utili nelle espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Le espressioni di query si avvalgono di frequente di [tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) che possono essere inizializzati solo con un inizializzatore di oggetto, come illustrato nella dichiarazione seguente.  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

I tipi anonimi consentono alla clausola `select` in un'espressione di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] di trasformare gli oggetti della sequenza originale in oggetti i cui valori e la cui forma potrebbero essere diversi dall'originale. Questo è utile se si desidera archiviare solo una parte delle informazioni di ogni oggetto di una sequenza. Nell'esempio seguente, si supponga che un oggetto prodotto (`p`) contenga diversi campi e metodi e che si sia interessati a creare solo una sequenza di oggetti che contengono il nome e il prezzo unitario del prodotto.  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

Quando questa query verrà eseguita, la variabile `productInfos` conterrà una sequenza di oggetti a cui sarà possibile accedere in un'istruzione `foreach` come illustrato in questo esempio:  

```csharp
foreach(var p in productInfos){...}  
```

Ogni oggetto nel nuovo tipo anonimo dispone di due proprietà pubbliche che ricevono gli stessi nomi delle proprietà o dei campi nell'oggetto originale. È inoltre possibile rinominare un campo mentre si crea un tipo anonimo. Nell'esempio seguente il campo `UnitPrice` viene rinominato in `Price`.  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a>Inizializzatori di raccolta

Gli inizializzatori di raccolta consentono di specificare uno o più inizializzatori di elemento quando si inizializza un tipo di raccolta che implementa <xref:System.Collections.IEnumerable> e ha un metodo `Add` con una firma appropriata come metodo di istanza o metodo di estensione. Gli inizializzatori di elemento possono essere valori semplici, espressioni o inizializzatori di oggetto. Se si usa un inizializzatore di insieme, non è necessario specificare più chiamate, in quanto le chiamate vengono aggiunte dal compilatore automaticamente.  
  
L'esempio seguente illustrati due inizializzatori di insieme semplici:  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

Nell'inizializzatore di raccolta riportato di seguito vengono utilizzati inizializzatori di oggetto per inizializzare oggetti della classe `Cat` definiti in un esempio precedente. Si noti che i singoli inizializzatori di oggetto sono racchiusi tra parentesi e separati da virgole.  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
È possibile specificare [null](../../language-reference/keywords/null.md) come elemento in un inizializzatore di insieme se il metodo `Add` della raccolta lo consente.  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 È possibile specificare elementi indicizzati se la raccolta supporta l'indicizzazione in lettura/scrittura.
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

L'esempio precedente genera codice che chiama <xref:System.Collections.Generic.Dictionary%602.Item(%600)> per impostare i valori. A partire da C# 6, è possibile inizializzare dizionari e altri contenitori associativi usando la sintassi seguente. Si noti che anziché la sintassi degli indicizzatori, con le parentesi e un'assegnazione, viene usato un oggetto con più valori:

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

Questo esempio di inizializzatore chiama <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> per aggiungere i tre elementi nel dizionario. Questi due modi diversi di inizializzazione delle raccolte associative hanno un comportamento leggermente diverso a causa delle chiamate di metodo generate dal compilatore. Con la classe `Dictionary` funzionano entrambe le varianti. È possibile che altri tipi supportino l'uno o l'altro in base all'API pubblica usata.

## <a name="examples"></a>Esempi

L'esempio seguente unisce i concetti di inizializzatori di oggetto e di insieme.

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

L'esempio seguente illustra un oggetto che implementa <xref:System.Collections.IEnumerable> e contiene un metodo `Add` con più parametri. Usa un inizializzatore di insieme con più elementi per ogni voce nell'elenco corrispondente alla firma del metodo `Add`.

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

I metodi `Add` possono usare la parola chiave `params` per accettare un numero variabile di argomenti, come illustrato nell'esempio seguente. Questo esempio illustra anche l'implementazione personalizzata di un indicizzatore per l'inizializzazione di un insieme tramite indici.

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Espressioni di query LINQ](../linq-query-expressions/index.md)
- [Tipi anonimi](anonymous-types.md)
