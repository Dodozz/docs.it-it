---
title: Inherits (istruzione) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 18e35bab219003439136bc5d88f4b2f0ea6cdd1c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965748"
---
# <a name="inherits-statement"></a><span data-ttu-id="182a5-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="182a5-102">Inherits Statement</span></span>
<span data-ttu-id="182a5-103">Fa sì che la classe corrente o l'interfaccia in modo che erediti da un'altra classe o un set di interfacce di attributi, le variabili, proprietà, procedure ed eventi.</span><span class="sxs-lookup"><span data-stu-id="182a5-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="182a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="182a5-104">Syntax</span></span>  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="182a5-105">Parti</span><span class="sxs-lookup"><span data-stu-id="182a5-105">Parts</span></span>  
  
|<span data-ttu-id="182a5-106">Termine</span><span class="sxs-lookup"><span data-stu-id="182a5-106">Term</span></span>|<span data-ttu-id="182a5-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="182a5-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="182a5-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="182a5-108">Required.</span></span> <span data-ttu-id="182a5-109">Il nome della classe da cui deriva questa classe.</span><span class="sxs-lookup"><span data-stu-id="182a5-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="182a5-110">-oppure-</span><span class="sxs-lookup"><span data-stu-id="182a5-110">-or-</span></span><br /><br /> <span data-ttu-id="182a5-111">I nomi delle interfacce da cui deriva questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="182a5-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="182a5-112">Utilizzare le virgole per separare più nomi.</span><span class="sxs-lookup"><span data-stu-id="182a5-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="182a5-113">Note</span><span class="sxs-lookup"><span data-stu-id="182a5-113">Remarks</span></span>  
 <span data-ttu-id="182a5-114">Se usato, il `Inherits` istruzione deve essere la prima riga non vuota e non di commento in una definizione di classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="182a5-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="182a5-115">Deve seguire immediatamente la `Class` o `Interface` istruzione.</span><span class="sxs-lookup"><span data-stu-id="182a5-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="182a5-116">È possibile usare `Inherits` solo in una classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="182a5-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="182a5-117">Ciò significa che il contesto della dichiarazione di un'ereditarietà non può essere un file di origine, lo spazio dei nomi, struttura, modulo, procedura o blocco.</span><span class="sxs-lookup"><span data-stu-id="182a5-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="182a5-118">Regole</span><span class="sxs-lookup"><span data-stu-id="182a5-118">Rules</span></span>  
  
-   <span data-ttu-id="182a5-119">**Ereditarietà della classe.**</span><span class="sxs-lookup"><span data-stu-id="182a5-119">**Class Inheritance.**</span></span> <span data-ttu-id="182a5-120">Se una classe Usa il `Inherits` istruzione, è possibile specificare una sola classe base.</span><span class="sxs-lookup"><span data-stu-id="182a5-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="182a5-121">Una classe non può ereditare da una classe annidata al suo interno.</span><span class="sxs-lookup"><span data-stu-id="182a5-121">A class cannot inherit from a class nested within it.</span></span>  
  
-   <span data-ttu-id="182a5-122">**Ereditarietà dell'interfaccia.**</span><span class="sxs-lookup"><span data-stu-id="182a5-122">**Interface Inheritance.**</span></span> <span data-ttu-id="182a5-123">Se un'interfaccia viene utilizzata la `Inherits` istruzione, è possibile specificare uno o più interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="182a5-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="182a5-124">È possibile ereditare da due interfacce, anche se ognuno definisce un membro con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="182a5-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="182a5-125">Se in questo caso, il codice di implementazione deve usare la qualificazione di nomi per specificare quale membro che sta implementando.</span><span class="sxs-lookup"><span data-stu-id="182a5-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="182a5-126">Un'interfaccia non può ereditare da un'altra interfaccia con un livello di accesso più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="182a5-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="182a5-127">Ad esempio, un `Public` interfaccia non può ereditare da un `Friend` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="182a5-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="182a5-128">Un'interfaccia non può ereditare da un'interfaccia annidata al suo interno.</span><span class="sxs-lookup"><span data-stu-id="182a5-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="182a5-129">Un esempio di ereditarietà della classe in .NET Framework è la <xref:System.ArgumentException> classe che eredita dal <xref:System.SystemException> classe.</span><span class="sxs-lookup"><span data-stu-id="182a5-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="182a5-130">Ciò fornisce <xref:System.ArgumentException> tutte le proprietà predefinite e le procedure necessarie per le eccezioni di sistema, ad esempio il <xref:System.Exception.Message%2A> proprietà e il <xref:System.Exception.ToString%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="182a5-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="182a5-131">Un esempio di ereditarietà dell'interfaccia in .NET Framework è la <xref:System.Collections.ICollection> interfaccia che eredita dal <xref:System.Collections.IEnumerable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="182a5-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="182a5-132">In questo modo, <xref:System.Collections.ICollection> eredita la definizione dell'enumeratore è necessaria per attraversare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="182a5-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="182a5-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="182a5-133">Example</span></span>  
 <span data-ttu-id="182a5-134">L'esempio seguente usa il `Inherits` istruzione per mostrare come una classe denominata `thisClass` può ereditare tutti i membri di una classe base denominata `anotherClass`.</span><span class="sxs-lookup"><span data-stu-id="182a5-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="182a5-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="182a5-135">Example</span></span>  
 <span data-ttu-id="182a5-136">Nell'esempio seguente mostra l'ereditarietà di più interfacce.</span><span class="sxs-lookup"><span data-stu-id="182a5-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="182a5-137">L'interfaccia denominata `thisInterface` ora include tutte le definizioni di <xref:System.IComparable>, <xref:System.IDisposable>, e <xref:System.IFormattable> interfacce membri ereditati forniscono rispettivamente per il confronto di tipo specifico di due oggetti, rilasciando le risorse allocate e che esprime il valore di un oggetto come un `String`.</span><span class="sxs-lookup"><span data-stu-id="182a5-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="182a5-138">Una classe che implementa `thisInterface` deve implementare ogni membro di ogni interfaccia di base.</span><span class="sxs-lookup"><span data-stu-id="182a5-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="182a5-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="182a5-139">See also</span></span>
- [<span data-ttu-id="182a5-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="182a5-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="182a5-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="182a5-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="182a5-142">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="182a5-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="182a5-143">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="182a5-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="182a5-144">Interfacce</span><span class="sxs-lookup"><span data-stu-id="182a5-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
