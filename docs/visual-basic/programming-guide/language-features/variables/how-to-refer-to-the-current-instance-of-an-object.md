---
title: "Procedura: Fare riferimento all'istanza corrente di un oggetto (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 70955cd55dfb91d4111e59ae58bfe409a4470433
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663536"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="6b13c-102">Procedura: Fare riferimento all'istanza corrente di un oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b13c-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="6b13c-103">Il *istanza corrente* di un oggetto è l'istanza in cui è attualmente in esecuzione il codice.</span><span class="sxs-lookup"><span data-stu-id="6b13c-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="6b13c-104">Si utilizza il `Me` (parola chiave) per fare riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="6b13c-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="6b13c-105">Per fare riferimento all'istanza corrente</span><span class="sxs-lookup"><span data-stu-id="6b13c-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="6b13c-106">Usare il `Me` parola chiave in cui in genere si utilizzerà il nome di una variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="6b13c-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="6b13c-107">Sebbene `Me` si comporta come un oggetto variabile, non è possibile dichiararla o qualsiasi elemento assegnare ad esso.</span><span class="sxs-lookup"><span data-stu-id="6b13c-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="6b13c-108">`Me` fa sempre riferimento all'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="6b13c-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b13c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b13c-109">See also</span></span>

- [<span data-ttu-id="6b13c-110">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="6b13c-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="6b13c-111">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="6b13c-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="6b13c-112">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="6b13c-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
