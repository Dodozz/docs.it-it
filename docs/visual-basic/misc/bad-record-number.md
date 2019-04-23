---
title: Numero di record non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: abd0a1467c0991a40b93e74a1d7a7889367fb8ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340802"
---
# <a name="bad-record-number"></a><span data-ttu-id="d9533-102">Numero di record non valido</span><span class="sxs-lookup"><span data-stu-id="d9533-102">Bad record number</span></span>
<span data-ttu-id="d9533-103">Il numero di record nell'istruzione `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` è minore o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="d9533-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d9533-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d9533-104">To correct this error</span></span>  
  
1. <span data-ttu-id="d9533-105">Controllare i calcoli usati per generare il numero di record.</span><span class="sxs-lookup"><span data-stu-id="d9533-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="d9533-106">Controllare l'ortografia delle variabili che contengono il numero di record o usati per calcolare i numeri di record.</span><span class="sxs-lookup"><span data-stu-id="d9533-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="d9533-107">Un nome di variabile contenente errori di ortografia è dichiarato in modo implicito e inizializzato su zero, a meno che non sia stato usato `Option Explicit On` nel modulo.</span><span class="sxs-lookup"><span data-stu-id="d9533-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9533-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9533-108">See also</span></span>

- [<span data-ttu-id="d9533-109">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="d9533-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
