---
title: 'Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], creating property grids for user settings
- user settings [Visual Basic], creating property grids
- property grids [Visual Basic], creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
ms.openlocfilehash: 5f4b962762aeecea65748c5456bc4a2d75595d4f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311617"
---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a>Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic
È possibile creare una griglia di proprietà delle impostazioni utente popolando un controllo <xref:System.Windows.Forms.PropertyGrid> con le proprietà dell'impostazione utente dell'oggetto `My.Settings`.  
  
> [!NOTE]
>  Affinché l'esempio funzioni, per l'applicazione devono essere state configurate le impostazioni utente. Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
 L'oggetto `My.Settings` espone ogni impostazione come proprietà. Il nome della proprietà corrisponde allo stesso nome dell'impostazione e il tipo di proprietà al tipo di impostazione. L'**ambito** dell'impostazione determina se la proprietà è di sola lettura. La proprietà di un'impostazione dell'ambito dell'**applicazione** è di sola lettura, mentre la proprietà dell'ambito dell'**utente**-è di lettura e scrittura. Per altre informazioni, vedere [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  Non è possibile modificare o salvare i valori delle impostazioni dell'ambito dell'applicazione in fase di esecuzione. È possibile modificare le impostazioni dell'ambito dell'applicazione quando si crea l'applicazione tramite **Creazione progetti** o modificando il file di configurazione dell'applicazione. Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
 In questo esempio viene usato un controllo <xref:System.Windows.Forms.PropertyGrid> per accedere alle proprietà dell'impostazione utente dell'oggetto `My.Settings`. Per impostazione predefinita, <xref:System.Windows.Forms.PropertyGrid> mostra tutte le proprietà dell'oggetto `My.Settings`. Tuttavia, le proprietà dell'impostazione utente hanno l'attributo <xref:System.Configuration.UserScopedSettingAttribute>. In questo esempio la proprietà <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> di <xref:System.Windows.Forms.PropertyGrid> viene impostata su <xref:System.Configuration.UserScopedSettingAttribute> per visualizzare solo le proprietà dell'impostazione utente.  
  
### <a name="to-add-a-user-setting-property-grid"></a>Per aggiungere una griglia delle proprietà dell'impostazione utente  
  
1. Aggiungere il controllo **PropertyGrid** dalla **casella degli strumenti** all'area di progettazione dell'applicazione, presupponendo che questo campo sia `Form1`.  
  
     Il nome predefinito del controllo PropertyGrid è `PropertyGrid1`.  
  
2. Fare doppio clic sull'area di progettazione del `Form1` per aprire il codice per il gestore eventi che carica il form.  
  
3. Impostare l'oggetto `My.Settings` come oggetto selezionato per la griglia delle proprietà.  
  
     [!code-vb[VbVbalrMyResources#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#11)]  
  
4. Configurare la griglia delle proprietà affinché mostri solo le impostazioni utente.  
  
     [!code-vb[VbVbalrMyResources#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#12)]  
  
    > [!NOTE]
    >  Per visualizzare solo le impostazioni dell'ambito applicazione, usare l'attributo <xref:System.Configuration.ApplicationScopedSettingAttribute> anziché <xref:System.Configuration.UserScopedSettingAttribute>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Alla chiusura dell'applicazione vengono salvate le impostazioni utente. Per salvare immediatamente le impostazioni, chiamare il metodo `My.Settings.Save`. Per altre informazioni, vedere [Procedura: Mantenere le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>Vedere anche

- [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Procedura: Leggere le impostazioni dell'applicazione in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Procedura: Modificare le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Procedura: Mantenere le impostazioni utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
