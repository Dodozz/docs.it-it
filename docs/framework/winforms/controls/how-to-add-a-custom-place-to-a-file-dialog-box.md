---
title: 'Procedura: Aggiungere un percorso personalizzato a una finestra di dialogo File'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 129ebed6d0a2b075020e635c8463536f97629d2f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624111"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Procedura: Aggiungere un percorso personalizzato a una finestra di dialogo File
Le finestre di dialogo predefinite Apri e Salva in [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] dispongono di un'area sul lato sinistro della finestra di dialogo denominata **Collegamenti preferiti**, che contiene percorsi personalizzati. Il <xref:System.Windows.Forms.OpenFileDialog> e <xref:System.Windows.Forms.SaveFileDialog> classi consentono di aggiungere cartelle al <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> raccolta.  
  
> [!NOTE]
>  Affinché un percorso personalizzato venga visualizzato nel <xref:System.Windows.Forms.OpenFileDialog> oppure <xref:System.Windows.Forms.SaveFileDialog>, il <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> proprietà deve essere impostata su `true` (predefinito).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Per aggiungere un percorso personalizzato a una finestra di dialogo File  
  
- Aggiungere un percorso, un GUID della cartella nota, o un <xref:System.Windows.Forms.FileDialogCustomPlace> dell'oggetto per il <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> raccolta della finestra di dialogo.  
  
     L'esempio di codice riportato di seguito illustra come aggiungere un percorso:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [GUID di cartella nota per percorsi personalizzati della finestra di dialogo File](known-folder-guids-for-file-dialog-custom-places.md)
