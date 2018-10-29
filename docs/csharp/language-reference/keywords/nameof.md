---
title: nameof (Riferimenti per C#)
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 726abfd903f37826a247e6e98c0d11f230447550
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035253"
---
# <a name="nameof-c-reference"></a>nameof (Riferimenti per C#)

Usata per ottenere il nome di stringa semplice (non qualificata) di una variabile, un tipo o un membro.  

Quando si segnalano errori nel codice, si associano collegamenti MVC (Model-View-Controller), si attivano eventi di modifica delle proprietà, è spesso necessario acquisire il nome di stringa di un metodo.  Con `nameof` è possibile garantire la validità del codice in caso di ridenominazione delle definizioni.  In precedenza, per fare riferimento alle definizioni era necessario usare valori letterali di stringa. Questo approccio tuttavia non è efficace quando si rinominano elementi del codice poiché gli strumenti non hanno l'indicazione di verificare questi valori letterali di stringa.  
  
 Il formato dell'espressione `nameof` è il seguente:  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a>Casi di utilizzo principali  
 Questi esempi illustrano i casi di utilizzo principali relativi a `nameof`.  
  
 Convalida dei parametri:  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 Collegamenti ad azioni MVC:  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 INotifyPropertyChanged:  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 Proprietà di dipendenza XAML:  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 Registrazione:  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 Attributi:  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a>Esempi  
 Alcuni esempi per C#:  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
class Test {  
    static void Main (string[] args) {  
        Console.WriteLine(nameof(C)); // -> "C"  
        Console.WriteLine(nameof(C.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(C.Method2)); // -> "Method2"  
        Console.WriteLine(nameof(c.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(c.Method2)); // -> "Method2"  
        // Console.WriteLine(nameof(z)); -> "z" [inside of Method2 ok, inside Method1 is a compiler error]  
        Console.WriteLine(nameof(Stuff)); // -> "Stuff"  
        // Console.WriteLine(nameof(T)); -> "T" [works inside of method but not in attributes on the method]  
        Console.WriteLine(nameof(f)); // -> "f"  
        // Console.WriteLine(nameof(f<T>)); -> [syntax error]  
        // Console.WriteLine(nameof(f<>)); -> [syntax error]  
        // Console.WriteLine(nameof(Method2())); -> [error "This expression does not have a name"]  
    }
}
```  
  
## <a name="remarks"></a>Note  
 L'argomento di `nameof` deve essere un nome semplice, un nome qualificato, un accesso di tipo membro, un accesso di base con un membro specificato oppure questo accesso con un membro specificato.  L'espressione dell'argomento identifica una definizione di codice, ma non viene mai valutata.  
  
 Dal momento che l'argomento deve essere un'espressione dal punto di vista sintattico, sono presenti molti elementi non consentiti che non è utile elencare.  Vale la pena di menzionare i seguenti, che sono quelli che producono errori, ovvero tipi predefiniti (ad esempio `int` o `void`), tipi nullable (`Point?`), tipi di matrice (`Customer[,]`), tipi di puntatore (`Buffer*`), alias qualificati (`A::B`) e tipi generici non associati (`Dictionary<,>`), nonché simboli di pre-elaborazione (`DEBUG`) ed etichette (`loop:`).  
  
 Se è necessario ottenere il nome completo, è possibile usare l'espressione `typeof` unitamente a `nameof`.  Ad esempio:
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 Purtroppo `typeof` non è un'espressione costante come `nameof`, quindi non è possibile usare `typeof` in combinazione con `nameof` in tutti i punti in cui è possibile usare `nameof`.  Ad esempio, quanto segue genera un errore di compilazione CS0182:
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 Negli esempi si nota che è possibile usare un nome di tipi e accedere a un nome di metodo di istanza.  Non è necessario disporre di un'istanza del tipo, come richiesto nelle espressioni valutate.  In alcune situazioni può risultare molto comodo usare il nome del tipo ma, dal momento che viene fatto riferimento solo al nome senza usare i dati dell'istanza, non è necessario optare per un'espressione o una variabile di istanza.  
  
 È possibile fare riferimento ai membri di una classe in espressioni di attributo nella classe.  
  
 Non esiste alcun modo per ottenere informazioni sulle firme, ad esempio con "`Method1 (str, str)`".  A tale scopo è possibile usare un'espressione `Expression e = () => A.B.Method1("s1", "s2")` ed estrarre MemberInfo dall'albero delle espressioni risultante.  
  
## <a name="language-specifications"></a>Specifiche del linguaggio  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [typeof](../../../csharp/language-reference/keywords/typeof.md)  
