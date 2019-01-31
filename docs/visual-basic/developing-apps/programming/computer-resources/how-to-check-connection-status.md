---
title: 'Procedura: Controllare lo stato di connessione in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: c7a43fd154616e516f8c5e7d36d25f34924649ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499960"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="9a0b9-102">Procedura: Controllare lo stato di connessione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a0b9-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="9a0b9-103">Per determinare se il computer ha una rete o una connessione Internet funzionante, è possibile usare la proprietà <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>.</span><span class="sxs-lookup"><span data-stu-id="9a0b9-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="9a0b9-104">Per verificare se un computer ha una connessione funzionante</span><span class="sxs-lookup"><span data-stu-id="9a0b9-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="9a0b9-105">Determinare se la proprietà `IsAvailable` è `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="9a0b9-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="9a0b9-106">Il codice seguente controlla lo stato della proprietà e lo segnala:</span><span class="sxs-lookup"><span data-stu-id="9a0b9-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     <span data-ttu-id="9a0b9-107">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9a0b9-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="9a0b9-108">Nella selezione del frammento di codice si trova in **Connettività e rete**.</span><span class="sxs-lookup"><span data-stu-id="9a0b9-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="9a0b9-109">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="9a0b9-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a0b9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a0b9-110">See also</span></span>
- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>
