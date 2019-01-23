---
title: 'Procedura: Leggere le impostazioni in fase di esecuzione conC#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d798b40e5e337ea7652c8e82cb7fa860a87528b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521751"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="644cb-102">Procedura: Leggere le impostazioni in fase di esecuzione conC#</span><span class="sxs-lookup"><span data-stu-id="644cb-102">How To: Read Settings at Run Time With C#</span></span> #
<span data-ttu-id="644cb-103">È possibile leggere le impostazioni con ambito di applicazione e con ambito di utente in fase di esecuzione tramite l'oggetto Proprietà.</span><span class="sxs-lookup"><span data-stu-id="644cb-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="644cb-104">L'oggetto Proprietà espone tutte le impostazioni predefinite per il progetto tramite il membro Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="644cb-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member.</span></span>  
  
### <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="644cb-105">Per leggere le impostazioni in fase di esecuzione con C#</span><span class="sxs-lookup"><span data-stu-id="644cb-105">To Read Settings at Run Time with C#</span></span>  
  
-   <span data-ttu-id="644cb-106">Accedere all'impostazione appropriata tramite il membro Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="644cb-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="644cb-107">Nell'esempio seguente viene illustrato come assegnare l'impostazione `myColor` a una proprietà BackColor.</span><span class="sxs-lookup"><span data-stu-id="644cb-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="644cb-108">È necessario avere creato in precedenza un file di impostazioni che contenga un'impostazione denominata `myColor` di tipo `System.Drawing.Color`.</span><span class="sxs-lookup"><span data-stu-id="644cb-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="644cb-109">Per informazioni sulla creazione di un file di impostazioni, vedere [How To: Creare una nuova impostazione in fase di progettazione](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="644cb-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="644cb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="644cb-110">See also</span></span>
- [<span data-ttu-id="644cb-111">Uso delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="644cb-111">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [<span data-ttu-id="644cb-112">Procedura: Scrivere le impostazioni utente in fase di esecuzione conC#</span><span class="sxs-lookup"><span data-stu-id="644cb-112">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="644cb-113">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="644cb-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
