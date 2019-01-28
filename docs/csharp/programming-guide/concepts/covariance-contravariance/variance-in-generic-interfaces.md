---
title: Varianza nelle interfacce generiche (C#)
ms.date: 07/20/2015
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: b713cb4f2b13c54a4a60c522bbef492a5962cdc3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601792"
---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="bf057-102">Varianza nelle interfacce generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="bf057-102">Variance in Generic Interfaces (C#)</span></span>
<span data-ttu-id="bf057-103">In .NET framework 4 è stato introdotto il supporto della varianza per diverse interfacce generiche esistenti.</span><span class="sxs-lookup"><span data-stu-id="bf057-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="bf057-104">Il supporto della varianza consente la conversione implicita delle classi che implementano tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="bf057-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="bf057-105">Le interfacce seguenti sono ora varianti:</span><span class="sxs-lookup"><span data-stu-id="bf057-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="bf057-106"><xref:System.Collections.Generic.IEnumerable%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="bf057-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="bf057-107"><xref:System.Collections.Generic.IEnumerator%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="bf057-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="bf057-108"><xref:System.Linq.IQueryable%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="bf057-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="bf057-109"><xref:System.Linq.IGrouping%602> (`TKey` e `TElement` sono covarianti)</span><span class="sxs-lookup"><span data-stu-id="bf057-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="bf057-110"><xref:System.Collections.Generic.IComparer%601> (T è controvariante)</span><span class="sxs-lookup"><span data-stu-id="bf057-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="bf057-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T è controvariante)</span><span class="sxs-lookup"><span data-stu-id="bf057-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="bf057-112"><xref:System.IComparable%601> (T è controvariante)</span><span class="sxs-lookup"><span data-stu-id="bf057-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="bf057-113">La covarianza consente a un metodo di avere un tipo restituito più derivato rispetto a quello definito dal parametro di tipo generico dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="bf057-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="bf057-114">Per illustrare la funzionalità di covarianza, considerare le seguenti interfacce generiche: `IEnumerable<Object>` e `IEnumerable<String>`.</span><span class="sxs-lookup"><span data-stu-id="bf057-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="bf057-115">L'interfaccia `IEnumerable<String>` non eredita l'interfaccia`IEnumerable<Object>`.</span><span class="sxs-lookup"><span data-stu-id="bf057-115">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="bf057-116">Tuttavia, il tipo `String` eredita il tipo `Object` e in alcuni casi è opportuno assegnare gli oggetti di ogni interfaccia all'altra.</span><span class="sxs-lookup"><span data-stu-id="bf057-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="bf057-117">Queste operazioni sono illustrate nell'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="bf057-117">This is shown in the following code example.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="bf057-118">Nelle versioni precedenti di .NET Framework, questo codice causa un errore di compilazione in C# con `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="bf057-118">In earlier versions of the .NET Framework, this code causes a compilation error in C# with `Option Strict On`.</span></span> <span data-ttu-id="bf057-119">Ora è invece possibile usare `strings` anziché `objects`, come illustrato nell'esempio precedente, poiché l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> è covariante.</span><span class="sxs-lookup"><span data-stu-id="bf057-119">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="bf057-120">La controvarianza consente a un metodo di avere tipi di argomenti meno derivati rispetto a quelli specificati dal parametro generico dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="bf057-120">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="bf057-121">Per illustrare la controvarianza, si supponga di aver creato una classe `BaseComparer` per confrontare le istanze della classe `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="bf057-121">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="bf057-122">La classe `BaseComparer` implementa l'interfaccia `IEqualityComparer<BaseClass>`.</span><span class="sxs-lookup"><span data-stu-id="bf057-122">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="bf057-123">Poiché l'interfaccia `BaseClass` è ora controvariante, è possibile usare <xref:System.Collections.Generic.IEqualityComparer%601> per confrontare le istanze delle classi che ereditano la classe `BaseComparer`.</span><span class="sxs-lookup"><span data-stu-id="bf057-123">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="bf057-124">Queste operazioni sono illustrate nell'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="bf057-124">This is shown in the following code example.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
class BaseClass { }  
class DerivedClass : BaseClass { }  
  
// Comparer class.  
class BaseComparer : IEqualityComparer<BaseClass>   
{  
    public int GetHashCode(BaseClass baseInstance)  
    {  
        return baseInstance.GetHashCode();  
    }  
    public bool Equals(BaseClass x, BaseClass y)  
    {  
        return x == y;  
    }  
}  
class Program  
{  
    static void Test()  
    {  
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();  
  
        // Implicit conversion of IEqualityComparer<BaseClass> to   
        // IEqualityComparer<DerivedClass>.  
        IEqualityComparer<DerivedClass> childComparer = baseComparer;  
    }  
}  
```  
  
 <span data-ttu-id="bf057-125">Per altri esempi, vedere [Uso della varianza nelle interfacce per le raccolte generiche (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="bf057-125">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="bf057-126">La varianza nelle interfacce generiche è supportata solo per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="bf057-126">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="bf057-127">I tipi di valore non supportano la varianza.</span><span class="sxs-lookup"><span data-stu-id="bf057-127">Value types do not support variance.</span></span> <span data-ttu-id="bf057-128">Ad esempio, non è possibile convertire `IEnumerable<int>` in modo implicito in `IEnumerable<object>` perché i valori integer sono rappresentati da un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="bf057-128">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>  
  
```csharp  
IEnumerable<int> integers = new List<int>();  
// The following statement generates a compiler errror,  
// because int is a value type.  
// IEnumerable<Object> objects = integers;  
```  
  
 <span data-ttu-id="bf057-129">È anche importante ricordare che le classi che implementano le interfacce varianti sono comunque invariabili.</span><span class="sxs-lookup"><span data-stu-id="bf057-129">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="bf057-130">Ad esempio, sebbene <xref:System.Collections.Generic.List%601> implementi l'interfaccia covariante <xref:System.Collections.Generic.IEnumerable%601>, non è possibile convertire `List<Object>` in `List<String>` in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="bf057-130">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<Object>` to `List<String>`.</span></span> <span data-ttu-id="bf057-131">come illustra l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="bf057-131">This is illustrated in the following code example.</span></span>  
  
```csharp  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf057-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf057-132">See also</span></span>

- [<span data-ttu-id="bf057-133">Uso della varianza nelle interfacce per le raccolte generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="bf057-133">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="bf057-134">Creazione di interfacce generiche varianti (C#)</span><span class="sxs-lookup"><span data-stu-id="bf057-134">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)
- [<span data-ttu-id="bf057-135">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="bf057-135">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="bf057-136">Varianza nei delegati (C#)</span><span class="sxs-lookup"><span data-stu-id="bf057-136">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
