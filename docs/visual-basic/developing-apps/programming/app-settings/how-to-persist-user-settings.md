---
title: 'Procedura: Salvare in modo permanente le impostazioni utente in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: dab285f175838fb71e4218cbafdd4f7593c9e786
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611293"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a>Procedura: Salvare in modo permanente le impostazioni utente in Visual Basic
È possibile usare il metodo `My.Settings.Save` per mantenere le modifiche apportate alle impostazioni dell'utente.  
  
 In genere, le applicazioni sono progettate per rendere permanenti le modifiche alle impostazioni dell'utente quando l'applicazione si arresta. Questo avviene perché il salvataggio delle impostazioni può richiedere diversi secondi, in base a una serie di fattori.  
  
 Per altre informazioni, vedere [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Mentre è possibile modificare e salvare i valori delle impostazioni dell'ambito dell'utente in fase di esecuzione, le impostazioni dell'ambito dell'applicazione sono di sola lettura e non possono essere modificate a livello di codice. È possibile modificare le impostazioni dell'ambito dell'applicazione quando si crea l'applicazione tramite **Creazione progetti** o modificando il file di configurazione dell'applicazione. Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene modificato il valore dell'impostazione utente `LastChanged` e la modifica viene salvata chiamando il metodo `My.Settings.Save`.  
  
 [!code-vb[VbVbalrMyResources#5](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-persist-user-settings_1.vb)]  
  
 Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione utente `LastChanged` di tipo `Date`. Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="see-also"></a>Vedere anche
- [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Procedura: Modificare le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
