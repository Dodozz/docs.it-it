---
title: 'Procedura: Eseguire una query sui metadati di un assembly tramite reflection (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: c4cdce49-b1c8-4420-b12a-9ff7e6671368
ms.openlocfilehash: 7c209e2524ea6931e0d8f0084a32ea6921adc26e
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025353"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-c"></a>Procedura: Eseguire una query sui metadati di un assembly tramite reflection (LINQ) (C#)

L'API di reflection della libreria di classi .NET Framework consente di esaminare i metadati in un assembly .NET e creare raccolte di tipi, membri dei tipi, parametri e così via, che si trovano in tale assembly. Poiché queste raccolte supportano l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>, è possibile eseguire query su tali raccolte tramite LINQ.  
  
Nell'esempio seguente viene illustrato come LINQ può essere usato con il processo di reflection per recuperare metadati specifici sui metodi che corrispondono a un criterio di ricerca specificato. In questo caso la query individuerà i nomi di tutti i metodi dell'assembly che restituiscono tipi enumerabili, ad esempio matrici.  
  
## <a name="example"></a>Esempio  
  
```csharp  
using System;
using System.Linq;
using System.Reflection;  

class ReflectionHowTO  
{  
    static void Main()  
    {  
        Assembly assembly = Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089");  
        var pubTypesQuery = from type in assembly.GetTypes()  
                    where type.IsPublic  
                        from method in type.GetMethods()  
                        where method.ReturnType.IsArray == true 
                            || ( method.ReturnType.GetInterface(  
                                typeof(System.Collections.Generic.IEnumerable<>).FullName ) != null  
                            && method.ReturnType.FullName != "System.String" )  
                        group method.ToString() by type.ToString();  

        foreach (var groupOfMethods in pubTypesQuery)  
        {  
            Console.WriteLine("Type: {0}", groupOfMethods.Key);  
            foreach (var method in groupOfMethods)  
            {  
                Console.WriteLine("  {0}", method);  
            }  
        }  

        Console.WriteLine("Press any key to exit... ");  
        Console.ReadKey();  
    }  
}
```  

L'esempio usa il metodo <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> per restituire una matrice di tipi nell'assembly specificato. Il filtro [where](../../../../csharp/language-reference/keywords/where-clause.md) viene applicato in modo che vengano restituiti solo i tipi pubblici. Per ogni tipo pubblico, viene generata una sottoquery usando la matrice <xref:System.Reflection.MethodInfo> restituita dalla chiamata a <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>. Questi risultati vengono filtrati per restituire solo i metodi il cui tipo restituito è una matrice oppure un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601>. Infine, questi risultati vengono raggruppati usando il nome del tipo come chiave.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
