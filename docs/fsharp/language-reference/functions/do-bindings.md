---
title: Associazioni do (F#)
description: "Informazioni su come un 'do' associazione F # viene usato per eseguire codice senza definire una funzione o un valore."
ms.date: 05/16/2016
ms.openlocfilehash: 78dbf8da0fe40b5af566ad98693df1109eede7e4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "45973144"
---
# <a name="do-bindings"></a><span data-ttu-id="110f7-103">Associazioni do</span><span class="sxs-lookup"><span data-stu-id="110f7-103">do Bindings</span></span>

<span data-ttu-id="110f7-104">Oggetto `do` binding viene usato per eseguire codice senza definire una funzione o un valore.</span><span class="sxs-lookup"><span data-stu-id="110f7-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="110f7-105">Inoltre, eseguire i binding possono essere usati nelle classi, vedere [ `do` associazioni nelle classi](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="110f7-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="110f7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="110f7-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="110f7-107">Note</span><span class="sxs-lookup"><span data-stu-id="110f7-107">Remarks</span></span>

<span data-ttu-id="110f7-108">Usare un `do` binding quando si desidera eseguire il codice indipendentemente da una definizione di funzione o un valore.</span><span class="sxs-lookup"><span data-stu-id="110f7-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="110f7-109">L'espressione in una `do` binding deve restituire `unit`.</span><span class="sxs-lookup"><span data-stu-id="110f7-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="110f7-110">Codice in un livello superiore `do` associazione viene eseguita quando viene inizializzato il modulo.</span><span class="sxs-lookup"><span data-stu-id="110f7-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="110f7-111">La parola chiave `do` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="110f7-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="110f7-112">Gli attributi possono essere applicati a un livello superiore `do` associazione.</span><span class="sxs-lookup"><span data-stu-id="110f7-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="110f7-113">Ad esempio, se il programma Usa l'interoperabilità COM, è possibile applicare il `STAThread` attributo al programma.</span><span class="sxs-lookup"><span data-stu-id="110f7-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="110f7-114">Questo scopo, è possibile utilizzare un attributo in un `do` associazione, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="110f7-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="110f7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="110f7-115">See also</span></span>

- [<span data-ttu-id="110f7-116">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="110f7-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="110f7-117">Funzioni</span><span class="sxs-lookup"><span data-stu-id="110f7-117">Functions</span></span>](index.md)
