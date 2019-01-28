---
title: Accesso agli attributi tramite reflection (C#)
ms.date: 07/20/2015
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
ms.openlocfilehash: f7c7b89be13022471f4e17bcb6ed9a90bcbc1c54
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660411"
---
# <a name="accessing-attributes-by-using-reflection-c"></a>Accesso agli attributi tramite reflection (C#)
La possibilità di definire attributi personalizzati e inserirli nel codice sorgente sarebbe di scarso valore senza un metodo per recuperare e usare le informazioni. Tramite l'uso di reflection, è possibile recuperare le informazioni definite con gli attributi personalizzati. Il metodo chiave è `GetCustomAttributes`, che restituisce una matrice di oggetti che rappresentano gli equivalenti in fase di esecuzione degli attributi di codice sorgente. Questo metodo ha versioni diverse sottoposte a overload. Per ulteriori informazioni, vedere <xref:System.Attribute>.  
  
 Una specifica di attributo come la seguente:  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 è concettualmente equivalente a questa:  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 Il codice non viene tuttavia eseguito fino a quando non vengono eseguite query su `SampleClass` per gli attributi. La chiamata a `GetCustomAttributes` in `SampleClass` causa la costruzione e l'inizializzazione di un oggetto `Author` come illustrato in precedenza. Se la classe ha altri attributi, gli altri oggetti di attributo vengono costruiti in modo analogo. `GetCustomAttributes` restituisce quindi l'oggetto `Author` e tutti gli altri oggetti di attributo in una matrice. È quindi possibile eseguire l'iterazione di questa matrice, determinare gli attributi applicati in base al tipo di ogni elemento della matrice ed estrarre informazioni dagli oggetti di attributo.  
  
## <a name="example"></a>Esempio  
 Questo è un esempio completo. Un attributo personalizzato viene definito, applicato a varie entità e recuperato tramite reflection.  
  
```csharp  
// Multiuse attribute.  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // Multiuse attribute.  
]  
public class Author : System.Attribute  
{  
    string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
  
        // Default value.  
        version = 1.0;  
    }  
  
    public string GetName()  
    {  
        return name;  
    }  
}  
  
// Class with the Author attribute.  
[Author("P. Ackerman")]  
public class FirstClass  
{  
    // ...  
}  
  
// Class without the Author attribute.  
public class SecondClass  
{  
    // ...  
}  
  
// Class with multiple Author attributes.  
[Author("P. Ackerman"), Author("R. Koch", version = 2.0)]  
public class ThirdClass  
{  
    // ...  
}  
  
class TestAuthorAttribute  
{  
    static void Test()  
    {  
        PrintAuthorInfo(typeof(FirstClass));  
        PrintAuthorInfo(typeof(SecondClass));  
        PrintAuthorInfo(typeof(ThirdClass));  
    }  
  
    private static void PrintAuthorInfo(System.Type t)  
    {  
        System.Console.WriteLine("Author information for {0}", t);  
  
        // Using reflection.  
        System.Attribute[] attrs = System.Attribute.GetCustomAttributes(t);  // Reflection.  
  
        // Displaying output.  
        foreach (System.Attribute attr in attrs)  
        {  
            if (attr is Author)  
            {  
                Author a = (Author)attr;  
                System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version);  
            }  
        }  
    }  
}  
/* Output:  
    Author information for FirstClass  
       P. Ackerman, version 1.00  
    Author information for SecondClass  
    Author information for ThirdClass  
       R. Koch, version 2.00  
       P. Ackerman, version 1.00  
*/  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Guida per programmatori C#](../../../../csharp/programming-guide/index.md)
- [Recupero di informazioni memorizzate negli attributi](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md)
- [Attributi (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md)
- [Creazione di attributi personalizzati (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)
