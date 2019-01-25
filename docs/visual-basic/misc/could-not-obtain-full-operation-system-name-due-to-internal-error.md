---
title: Errore interno. Impossibile ottenere il nome completo del sistema operativo
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: df7a91ea5763c0fe4b7a1993bec29f1b1bb43fcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723295"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="e3ddb-102">Errore interno. Impossibile ottenere il nome completo del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="e3ddb-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="e3ddb-103">Errore interno. Impossibile ottenere il nome completo del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e3ddb-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="e3ddb-104">WMI potrebbe non essere presente sul computer in uso.</span><span class="sxs-lookup"><span data-stu-id="e3ddb-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="e3ddb-105">Una chiamata alla proprietà `My.Computer.Info.OSFullName` non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e3ddb-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="e3ddb-106">L'errore può derivare dal fatto che Strumentazione gestione Windows (WMI) non è installato nel computer corrente.</span><span class="sxs-lookup"><span data-stu-id="e3ddb-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3ddb-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e3ddb-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="e3ddb-108">Aggiungere un blocco `Try...Catch` nella chiamata alla proprietà `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="e3ddb-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="e3ddb-109">Per altre informazioni su WMI e come installarla, passare a e cercare "Windows Management Instrumentation Core".</span><span class="sxs-lookup"><span data-stu-id="e3ddb-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ddb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3ddb-110">See also</span></span>
- [<span data-ttu-id="e3ddb-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="e3ddb-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="e3ddb-112">Gestione di eccezioni ed errori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e3ddb-112">Exception and Error Handling in Visual Basic</span></span>](https://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)
- [<span data-ttu-id="e3ddb-113">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="e3ddb-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
