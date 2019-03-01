---
title: 'Procedura: Creare una nuova impostazione in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: c936adb6d4d80032b862994c21178a505da6789b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964248"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="228cb-102">Procedura: Creare una nuova impostazione in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="228cb-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="228cb-103">È possibile creare una nuova impostazione in fase di progettazione tramite Progettazione impostazioni.</span><span class="sxs-lookup"><span data-stu-id="228cb-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="228cb-104">Progettazione impostazioni è un'interfaccia stile griglia che consente di creare nuove impostazioni e specificare le proprietà per tali impostazioni.</span><span class="sxs-lookup"><span data-stu-id="228cb-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="228cb-105">È necessario specificare nome, valore, tipo e ambito per le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="228cb-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="228cb-106">Dopo aver creata un'impostazione, è possibile accedere nel codice.</span><span class="sxs-lookup"><span data-stu-id="228cb-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="228cb-107">Per creare una nuova impostazione in fase di progettazione in C\#</span><span class="sxs-lookup"><span data-stu-id="228cb-107">To create a new setting at design time in C\#</span></span>
  
1.  <span data-ttu-id="228cb-108">Nelle **Esplora soluzioni**, espandere il **proprietà** nodo del progetto.</span><span class="sxs-lookup"><span data-stu-id="228cb-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2.  <span data-ttu-id="228cb-109">Fare doppio clic il file. Settings in cui si desidera aggiungere una nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="228cb-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="228cb-110">Il nome predefinito per questo file è Settings. Settings.</span><span class="sxs-lookup"><span data-stu-id="228cb-110">The default name for this file is Settings.settings.</span></span>  
  
3.  <span data-ttu-id="228cb-111">Nella finestra di progettazione impostazioni, impostare il nome, valore, tipo e ambito per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="228cb-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="228cb-112">Ogni riga rappresenta una singola impostazione.</span><span class="sxs-lookup"><span data-stu-id="228cb-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="228cb-113">Per creare una nuova impostazione in fase di progettazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="228cb-113">To create a new setting at design time in Visual Basic</span></span>  
  
1.  <span data-ttu-id="228cb-114">Nelle **Esplora soluzioni**, fare clic sul nodo del progetto e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="228cb-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="228cb-115">Nel **delle proprietà** pagina, selezionare la **impostazioni** scheda.</span><span class="sxs-lookup"><span data-stu-id="228cb-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3.  <span data-ttu-id="228cb-116">Nella finestra di progettazione impostazioni, impostare il nome, valore, tipo e ambito per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="228cb-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="228cb-117">Ogni riga rappresenta una singola impostazione.</span><span class="sxs-lookup"><span data-stu-id="228cb-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228cb-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="228cb-118">See also</span></span>
- [<span data-ttu-id="228cb-119">Uso delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="228cb-119">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [<span data-ttu-id="228cb-120">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="228cb-120">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="228cb-121">Procedura: Modificare il valore di un'impostazione esistente in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="228cb-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)
