---
title: La parola chiave fixed
description: Informazioni su come è possibile aggiungere una variabile locale nello stack per impedire la raccolta con il F# 'fixed' (parola chiave).
ms.date: 04/24/2017
ms.openlocfilehash: 7fdf66560f3e2ab7584b00c7e4584d7f6c161858
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614341"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="5142d-103">La parola chiave fixed</span><span class="sxs-lookup"><span data-stu-id="5142d-103">The fixed keyword</span></span>

<span data-ttu-id="5142d-104">F#4.1 introduce il `fixed` parola chiave, che consente di "aggiungere" una variabile locale nello stack per evitare che vengano raccolti o spostate durante la garbage collection.</span><span class="sxs-lookup"><span data-stu-id="5142d-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="5142d-105">Viene usato per gli scenari di programmazione di basso livello.</span><span class="sxs-lookup"><span data-stu-id="5142d-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="5142d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5142d-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="5142d-107">Note</span><span class="sxs-lookup"><span data-stu-id="5142d-107">Remarks</span></span>

<span data-ttu-id="5142d-108">Estende la sintassi delle espressioni per consentire l'estrazione di un puntatore e associarlo a un nome di cui viene impedito di essere raccolti o spostati durante l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="5142d-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="5142d-109">Un puntatore da un'espressione è stato risolto tramite il `fixed` parola chiave è associata a un identificatore tramite il `use` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="5142d-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="5142d-110">La semantica di questo oggetto è simile alla gestione delle risorse tramite il `use` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="5142d-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="5142d-111">Mentre si trova nell'ambito e una volta esula dall'ambito, non è non è più fisso, il puntatore è stato risolto.</span><span class="sxs-lookup"><span data-stu-id="5142d-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="5142d-112">`fixed` non è possibile usare all'esterno del contesto di un `use` associazione.</span><span class="sxs-lookup"><span data-stu-id="5142d-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="5142d-113">È necessario associare il puntatore a un nome con `use`.</span><span class="sxs-lookup"><span data-stu-id="5142d-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="5142d-114">Uso di `fixed` deve verificarsi all'interno di un'espressione in una funzione o un metodo.</span><span class="sxs-lookup"><span data-stu-id="5142d-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="5142d-115">Non può essere utilizzato in un ambito a livello di script o a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="5142d-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="5142d-116">Simile a tutte le code di puntatore, questa è una funzionalità non sicura e genererà un avviso quando viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="5142d-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="5142d-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="5142d-117">Example</span></span>

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a><span data-ttu-id="5142d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5142d-118">See also</span></span>

- [<span data-ttu-id="5142d-119">NativePtr (modulo)</span><span class="sxs-lookup"><span data-stu-id="5142d-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
