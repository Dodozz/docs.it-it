---
title: Clausola where (Riferimento C#)
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 4b9a5169baa07f2b0363778afbea64ba34eee1d8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238669"
---
# <a name="where-clause-c-reference"></a>Clausola where (Riferimento C#)
La clausola `where` viene usata in un'espressione di query per specificare quali elementi dell'origine dati verranno restituiti nell'espressione di query. Viene applicata una condizione booleana (*predicato*) a ogni elemento di origine (a cui fa riferimento la variabile di intervallo) e viene restituita quella per cui la condizione specificata è vera. Una singola espressione di query può contenere più clausole `where` e una singola clausola può contenere più sottoespressioni di predicato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente la clausola `where` esclude tutti i numeri tranne quelli minori di cinque. Se si rimuove la clausola `where`, vengono restituiti tutti i numeri dell'origine dati. L'espressione `num < 5` è il predicato che viene applicato a ogni elemento.  
  
 [!code-csharp[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]  
  
## <a name="example"></a>Esempio  
 In una singola clausola `where` è possibile specificare tutti i predicati necessari usando gli operatori [ && ](../../../csharp/language-reference/operators/conditional-and-operator.md) e [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md). Nell'esempio seguente la query specifica due predicati per selezionare solo i numeri pari minori di cinque.  
  
 [!code-csharp[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]  
  
## <a name="example"></a>Esempio  
 Una clausola `where` può contenere uno o più metodi che restituiscono valori booleani. Nell'esempio seguente la clausola `where` usa un metodo per determinare se il valore corrente della variabile di intervallo è pari o dispari.  
  
 [!code-csharp[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]  
  
## <a name="remarks"></a>Note  
 La clausola `where` è un meccanismo di filtro. Può essere posizionata praticamente ovunque in un'espressione di query, ma non può essere la prima o l'ultima clausola. Una clausola `where` la può apparire prima o dopo una clausola [group](../../../csharp/language-reference/keywords/group-clause.md) a seconda se gli elementi di origine devono essere filtrati prima o dopo essere stati raggruppati.  
  
 Se un predicato specificato non è valido per gli elementi nell'origine dati, si verificherà un errore in fase di compilazione. Questo è uno dei vantaggi del controllo efficace del tipo offerto da [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].  
  
 In fase di compilazione, la parola chiave `where` viene convertita in una chiamata al metodo <xref:System.Linq.Enumerable.Where%2A> dell'operatore query standard.  
  
## <a name="see-also"></a>Vedere anche

- [Parole chiave di query (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
- [Clausola from](../../../csharp/language-reference/keywords/from-clause.md)  
- [Clausola select](../../../csharp/language-reference/keywords/select-clause.md)  
- [Filtraggio dei dati](../../programming-guide/concepts/linq/filtering-data.md)  
- [Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
- [Nozioni di base su LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
