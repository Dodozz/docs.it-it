---
title: Direttiva using - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: b58467953096c26d13f4c837f13548876e645f08
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240320"
---
# <a name="using-directive-c-reference"></a>Direttiva using (Riferimenti per C#)
La direttiva `using` ha tre usi:  
  
-   Consentire l'uso di tipi in uno spazio dei nomi in modo da non dover qualificare l'uso di un tipo in tale spazio dei nomi:  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   Consentire l'accesso ai membri statici e ai tipi nidificati di un tipo senza dover qualificare l'accesso con il nome del tipo. 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    Per altre informazioni, vedere la [direttiva using static](using-static.md).

-   Creare un alias per uno spazio dei nomi o un tipo. Si tratta di una *direttiva alias using*.  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 La parola chiave `using` viene usata anche per creare *istruzioni using*, che garantiscono che gli oggetti <xref:System.IDisposable>, ad esempio file e tipi di carattere, vengano gestiti correttamente. Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).  
  
## <a name="using-static-type"></a>Tipo using static  
 È possibile accedere ai membri statici di un tipo senza dover qualificare l'accesso con il nome del tipo:  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a>Note  
 L'ambito di una direttiva `using` è limitato al file in cui viene visualizzata.
 
 La direttiva `using` può essere visualizzata:
- All'inizio del file del codice sorgente, prima di eventuali definizioni di spazio dei nomi o tipo.
- In qualsiasi spazio dei nomi, ma prima di un spazio dei nomi o di tipi dichiarati nello spazio dei nomi.

In caso contrario, viene generato l'errore del compilatore [CS1529](../../misc/cs1529.md).
  
 Creare una direttiva alias `using` per semplificare la qualifica di un identificatore in uno spazio dei nomi o un tipo. In una direttiva `using` è necessario usare lo spazio dei nomi o il tipo completo indipendentemente dalle direttive `using` che la precedono. Non è possibile usare alcun alias `using` nella dichiarazione di una direttiva `using`. Ad esempio, il codice seguente genera un errore del compilatore:
 ```csharp
 using s = System.Text;
 using s.RegularExpressions; 
 ```
  
 Creare una direttiva `using` per usare i tipi in uno spazio dei nomi senza dover specificare tale spazio dei nomi. Una direttiva `using` non offre accesso ad alcuno spazio dei nomi annidato nello spazio dei nomi specificato.  
  
 Gli spazi dei nomi sono disponibili in due categorie: definiti dall'utente e definiti dal sistema. Gli spazi dei nomi definiti dall'utente vengono definiti nel codice. Per un elenco di spazi dei nomi definiti dal sistema, vedere [Browser API .NET](https://docs.microsoft.com/dotnet/api/).  
  
 Per esempi relativi ai metodi di riferimento in altri assembly, vedere [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md) (Creazione e uso degli assembly usando la riga di comando).  
  
## <a name="example-1"></a>Esempio 1  
  
 Nell'esempio seguente viene illustrato come definire e usare un alias `using` per uno spazio dei nomi.  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 Una direttiva alias using non può contenere un tipo generico aperto nella parte destra. Ad esempio, non è possibile creare un alias using per List\<T>, ma è possibile crearne uno per List\<int>.  
  
## <a name="example-2"></a>Esempio 2  
  
 Nell'esempio seguente viene illustrato come definire una direttiva `using` e un alias `using` per una classe:  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Uso degli spazi dei nomi](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [Parole chiave per gli spazi dei nomi](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md)  
- [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md)
