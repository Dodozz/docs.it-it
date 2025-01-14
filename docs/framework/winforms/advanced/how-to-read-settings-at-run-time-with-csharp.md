---
title: 'Procedura: Leggere le impostazioni in fase di esecuzione con C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8cdc1a79f1ab327ae037cd6a04aa769196405127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966915"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Procedura: Leggere le impostazioni in fase di esecuzione con C\#

È possibile leggere le impostazioni con ambito di applicazione e con ambito di utente in fase di esecuzione tramite l'oggetto Proprietà. L'oggetto Proprietà espone tutte le impostazioni predefinite per il progetto tramite il membro Properties.Settings.Default.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Leggere le impostazioni in fase di esecuzione con C\#
  
Accedere all'impostazione appropriata tramite il membro Properties.Settings.Default. Nell'esempio seguente viene illustrato come assegnare l'impostazione `myColor` a una proprietà BackColor. È necessario avere creato in precedenza un file di impostazioni che contenga un'impostazione denominata `myColor` di tipo `System.Drawing.Color`. Per informazioni sulla creazione di un file di impostazioni, vedere [How To: Creare una nuova impostazione in fase di progettazione](how-to-create-a-new-setting-at-design-time.md).  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Procedura: Scrivere le impostazioni utente in fase di esecuzione conC#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
