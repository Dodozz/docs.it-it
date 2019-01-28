---
title: Interfacce generiche - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: d0b9d35a7e814d8790ee57f1169f2b35f7c42536
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564211"
---
# <a name="generic-interfaces-c-programming-guide"></a>Interfacce generiche (Guida per programmatori C#)
Spesso è utile definire interfacce per classi di raccolta generiche o per le classi generiche che rappresentano elementi nella raccolta. Per le classi generiche è preferibile usare interfacce generiche, ad esempio <xref:System.IComparable%601> invece di <xref:System.IComparable>, per evitare operazioni di conversione boxing e unboxing sui tipi valore. La libreria di classi .NET Framework definisce diverse interfacce generiche da usare con le classi di raccolta nello spazio dei nomi <xref:System.Collections.Generic>.  
  
 Quando un'interfaccia viene specificata come vincolo o parametro di tipo, è possibile usare solo i tipi che implementano l'interfaccia. L'esempio di codice seguente mostra una classe `SortedList<T>` che deriva dalla classe `GenericList<T>`. Per altre informazioni, vedere [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md). `SortedList<T>` aggiunge il vincolo `where T : IComparable<T>`. In questo modo, il metodo `BubbleSort` in `SortedList<T>` può usare il metodo <xref:System.IComparable%601.CompareTo%2A> generico negli elementi dell'elenco. In questo esempio gli elementi dell'elenco sono una classe semplice, ovvero `Person`, che implementa `IComparable<Person>`.  
  
 [!code-csharp[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]  
  
 È possibile specificare più interfacce come vincoli su un unico tipo, in questo modo:  
  
 [!code-csharp[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]  
  
 Un'interfaccia può definire più parametri di tipo, in questo modo:  
  
 [!code-csharp[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]  
  
 Le regole di ereditarietà valide per le classi si applicano anche alle interfacce:  
  
 [!code-csharp[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]  
  
 Le interfacce generiche possono ereditare da interfacce non generiche se l'interfaccia generica è controvariante, ovvero usa solo il proprio parametro di tipo come valore restituito. Nella libreria di classi .NET Framework <xref:System.Collections.Generic.IEnumerable%601> eredita da <xref:System.Collections.IEnumerable> perché <xref:System.Collections.Generic.IEnumerable%601> usa solo `T` nel valore restituito di <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> e nel getter proprietà <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.  
  
 Le classi concrete possono implementare interfacce costruite chiuse, in questo modo:  
  
 [!code-csharp[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]  
  
 Le classi generiche possono implementare interfacce generiche o interfacce costruite chiuse purché l'elenco di parametri delle classi specifichi tutti gli argomenti necessari per l'interfaccia, in questo modo:  
  
 [!code-csharp[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]  
  
 Le regole che controllano l'overload dei metodi sono le stesse per i metodi all'interno di classi generiche, struct generici o interfacce generiche. Per altre informazioni, vedere [Metodi generici](../../../csharp/programming-guide/generics/generic-methods.md).  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)
- [interface](../../../csharp/language-reference/keywords/interface.md)
- [Generics](~/docs/standard/generics/index.md)
