---
title: Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 4150d2f9634045351cb52e02c4f4807e55d118e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717902"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)
Il `My.Resources` oggetto consente di accedere alle risorse dell'applicazione e consente di recuperare in modo dinamico le risorse per l'applicazione.  
  
## <a name="retrieving-resources"></a>Recupero di risorse  
 Un numero di risorse, ad esempio i file audio, icone, immagini e stringhe può essere recuperato tramite il `My.Resources` oggetto. Ad esempio, è possibile accedere i file di risorse specifiche delle impostazioni cultura dell'applicazione. Nell'esempio seguente imposta l'icona del form per l'icona denominato `Form1Icon` archiviati nel file di risorse dell'applicazione.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 Il `My.Resources` oggetto espone solo le risorse globali. Non fornisce accesso ai file di risorse associati ai form. È necessario accedere alle risorse form dal form.  
  
 Analogamente, il `My.Settings` oggetto consente di accedere alle impostazioni dell'applicazione e consente di archiviare e recuperare le impostazioni delle proprietà e altre informazioni per l'applicazione in modo dinamico. Per altre informazioni, vedere [oggetto My. Resources](../../../visual-basic/language-reference/objects/my-resources-object.md) e [oggetto My. Settings](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Vedere anche
- [Oggetto My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [Oggetto My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Accesso alle impostazioni dell'applicazione](../../../visual-basic/developing-apps/programming/app-settings/index.md)
