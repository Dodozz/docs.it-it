---
title: Parametri di tipo generico - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 096fce3affb9461c57ae9c0ffd57367d1b4349df
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423428"
---
# <a name="generic-type-parameters-c-programming-guide"></a>Parametri di tipo generico (Guida per programmatori C#)

In una definizione di tipo o metodo generico un parametro di tipo è un segnaposto per un determinato tipo specificato da un client durante la creazione di un'istanza del tipo generico. Una classe generica, ad esempio `GenericList<T>`, elencata in [Introduzione ai generics](../../../csharp/programming-guide/generics/index.md), non può essere usata in quanto tale perché non è effettivamente un tipo, ma è piuttosto un progetto iniziale per un tipo. Per usare `GenericList<T>`, il codice client deve dichiarare un tipo costruito e crearne un'istanza specificando un argomento tipo racchiuso tra parentesi angolari. L'argomento tipo per questa classe specifica può essere qualsiasi tipo riconosciuto dal compilatore. È possibile creare un numero qualsiasi di istanze del tipo costruito, ognuna con un argomento tipo diverso, in questo modo:  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
In ognuna di queste istanze di `GenericList<T>` ogni occorrenza di `T` nella classe viene sostituita in fase di esecuzione con l'argomento tipo. Per mezzo di questa sostituzione, sono stati creati tre oggetti efficienti e indipendenti dai tipi separati usando un'unica definizione di classe. Per altre informazioni su come viene eseguita questa sostituzione da CLR, vedere [Generics nel runtime](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## <a name="type-parameter-naming-guidelines"></a>Linee guida per la denominazione dei parametri di tipo  
  
- **Assegnare** ai parametri di tipo generico nomi descrittivi, a meno che un nome di una sola lettera non sia già completamente comprensibile, senza che sia necessario un nome descrittivo più lungo.  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- **Provare** a usare T come nome del parametro di tipo per i tipi con parametro di tipo di una sola lettera.  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- **Aggiungere** ai nomi di parametro di tipo descrittivi il prefisso "T".  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- **Provare** a indicare i vincoli applicati a un parametro di tipo nel nome del parametro. Ad esempio, assegnare a un parametro vincolato a `ISession` il nome `TSession`.

La regola di analisi codice [CA1715](/visualstudio/code-quality/ca1715-identifiers-should-have-correct-prefix) può essere usata per garantire che i parametri di tipo vengano denominati in modo appropriato.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Generics](../../../csharp/programming-guide/generics/index.md)
- [Differenze tra modelli C++ e generics C#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
