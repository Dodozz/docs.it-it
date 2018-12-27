---
title: Copiare e aggiornare espressioni di record
description: Informazioni su come scrivere un 'copia e aggiorna record expression' in cui vengono copiati un esistente gli aggiornamenti dei record, campi specificati e restituisce il record aggiornato.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 5f9b13ebf6c456aff73872b7522d7670c068dd88
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613310"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="53bb3-103">Copiare e aggiornare espressioni di record</span><span class="sxs-lookup"><span data-stu-id="53bb3-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="53bb3-104">Oggetto *copiare e aggiornare l'espressione di record* è un'espressione che consente di copiare un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.</span><span class="sxs-lookup"><span data-stu-id="53bb3-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="53bb3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53bb3-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="53bb3-106">Note</span><span class="sxs-lookup"><span data-stu-id="53bb3-106">Remarks</span></span>

<span data-ttu-id="53bb3-107">I record non sono modificabili per impostazione predefinita, in modo che non sono presenti aggiornamenti per un record esistente possibili.</span><span class="sxs-lookup"><span data-stu-id="53bb3-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="53bb3-108">Per creare un record aggiornato tutti i campi di un record dovrà essere specificato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="53bb3-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="53bb3-109">Per semplificare questa attività una *copiare e aggiornare l'espressione di record* può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="53bb3-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="53bb3-110">Questa espressione accetta un record esistente, crea una nuova istanza dello stesso tipo con campi specificati dall'espressione e il campo mancante specificati dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="53bb3-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="53bb3-111">Ciò risulta utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori di campo.</span><span class="sxs-lookup"><span data-stu-id="53bb3-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="53bb3-112">Consideriamo ad esempio un record appena creato.</span><span class="sxs-lookup"><span data-stu-id="53bb3-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="53bb3-113">Se si intende aggiornare solo nel campo del record è possibile usare la *copiare e aggiornare l'espressione di record* analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="53bb3-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="53bb3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53bb3-114">See also</span></span>

- [<span data-ttu-id="53bb3-115">Record</span><span class="sxs-lookup"><span data-stu-id="53bb3-115">Records</span></span>](records.md)
- [<span data-ttu-id="53bb3-116">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="53bb3-116">F# Language Reference</span></span>](index.md)