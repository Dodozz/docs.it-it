---
title: 'Procedura: Implementare una classe leggera con proprietà implementate automaticamente - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: f9884f353e58ff6119e3bc3b95aa55f0f60d0ad5
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398503"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a>Procedura: Implementare una classe leggera con proprietà implementate automaticamente (Guida per programmatori C#)

Questo esempio mostra come creare una classe leggera non modificabile che serve solo a incapsulare un set di proprietà implementate automaticamente. Usare questo genere di costrutto invece di una struct quando è necessario usare la semantica del tipo riferimento.

È possibile creare una proprietà non modificabile in due modi:
- È possibile dichiarare la funzione di accesso [set](../../../csharp/language-reference/keywords/set.md) come [privata](../../../csharp/language-reference/keywords/private.md).  La proprietà è impostabile solo all'interno del tipo è, ma non è modificabile per i consumer.

  Quando si dichiara una funzione di accesso `set` privata, non è possibile usare un inizializzatore di oggetto per inizializzare la proprietà. È necessario usare un costruttore o un metodo factory.
- È possibile dichiarare solo la funzione di accesso [get](../../../csharp/language-reference/keywords/get.md), che rende la proprietà non modificabile ovunque tranne che nel costruttore del tipo.

## <a name="example"></a>Esempio

Il seguente esempio mostra due modi per implementare una classe non modificabile con proprietà implementate automaticamente. Ogni modo dichiara una delle proprietà con una funzione di accesso `set` privata e una delle proprietà solo con `get`.  La prima classe usa un costruttore solo per inizializzare le proprietà e la seconda classe usa un metodo factory statico che chiama un costruttore.

```csharp
// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// constructor to initialize its properties.
class Contact
{
    // Read-only properties.
    public string Name { get; }
    public string Address { get; private set; }

    // Public constructor.
    public Contact(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }
}

// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// static method and private constructor to initialize its properties.
public class Contact2
{
    // Read-only properties.
    public string Name { get; private set; }
    public string Address { get; }

    // Private constructor.
    private Contact2(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }

    // Public factory method.
    public static Contact2 CreateContact(string name, string address)
    {
        return new Contact2(name, address);
    }
}

public class Program
{
    static void Main()
    {
        // Some simple data sources.
        string[] names = {"Terry Adams","Fadi Fakhouri", "Hanying Feng",
                            "Cesar Garcia", "Debra Garcia"};
        string[] addresses = {"123 Main St.", "345 Cypress Ave.", "678 1st Ave",
                                "12 108th St.", "89 E. 42nd St."};

        // Simple query to demonstrate object creation in select clause.
        // Create Contact objects by using a constructor.
        var query1 = from i in Enumerable.Range(0, 5)
                    select new Contact(names[i], addresses[i]);

        // List elements cannot be modified by client code.
        var list = query1.ToList();
        foreach (var contact in list)
        {
            Console.WriteLine("{0}, {1}", contact.Name, contact.Address);
        }

        // Create Contact2 objects by using a static factory method.
        var query2 = from i in Enumerable.Range(0, 5)
                        select Contact2.CreateContact(names[i], addresses[i]);

        // Console output is identical to query1.
        var list2 = query2.ToList();

        // List elements cannot be modified by client code.
        // CS0272:
        // list2[0].Name = "Eugene Zabokritski";

        // Keep the console open in debug mode.
        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }
}

/* Output:
    Terry Adams, 123 Main St.
    Fadi Fakhouri, 345 Cypress Ave.
    Hanying Feng, 678 1st Ave
    Cesar Garcia, 12 108th St.
    Debra Garcia, 89 E. 42nd St.
*/
```

Il compilatore crea campi sottostanti per ogni proprietà implementate automaticamente. I campi non sono accessibili direttamente dal codice sorgente.

## <a name="see-also"></a>Vedere anche

- [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [struct](../../../csharp/language-reference/keywords/struct.md)
- [Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
