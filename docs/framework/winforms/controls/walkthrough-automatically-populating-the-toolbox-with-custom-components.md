---
title: 'Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 6ecf69350b8337dc6049b73251809192b47dc2fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759908"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati
Se i componenti vengono definiti da un progetto nella soluzione attualmente aperta, verranno automaticamente visualizzati nei **casella degli strumenti**, senza alcun intervento da parte dell'utente. È anche possibile inserire manualmente il **casella degli strumenti** con i componenti personalizzati usando la [Scegli elementi della finestra della casella (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), ma il **della casella degli strumenti** tengano conto elementi della soluzione di output con tutte le caratteristiche seguenti di compilazione:  
  
- Implementa <xref:System.ComponentModel.IComponent>;  
  
- Non dispone <xref:System.ComponentModel.ToolboxItemAttribute> impostato su `false`;  
  
- Non dispone <xref:System.ComponentModel.DesignTimeVisibleAttribute> impostato su `false`.  
  
> [!NOTE]
>  Il **casella degli strumenti** non rispetta le catene di riferimento, in modo da non visualizzerà gli elementi che non vengono compilati da un progetto nella soluzione.  
  
 Questa procedura dettagliata illustra come un componente personalizzato viene visualizzato automaticamente nel **casella degli strumenti** dopo aver compilato il componente. Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
- Creazione di un progetto Windows Form.  
  
- Creazione di un componente personalizzato.  
  
- Creazione di un'istanza di un componente personalizzato.  
  
- Scaricare e ricaricare un componente personalizzato.  
  
 Al termine, si noterà che il **casella degli strumenti** viene popolato con un componente che è stato creato.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio indica come creare il progetto e impostare il modulo.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1. Creare un progetto di applicazione basata su Windows denominato `ToolboxExample` (**File** > **New** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).  
  
2. Aggiungere un nuovo componente al progetto. nominarla `DemoComponent`.  
  
     Per altre informazioni, vedere [Procedura: Aggiungere nuovi elementi di progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).  
  
3. Compilare il progetto.  
  
4. Dal **degli strumenti** menu, fare clic sul **opzioni** elemento. Fare clic su **generali** sotto il **progettazione di Windows Form** e verificare che il **AutoToolboxPopulate** opzione è impostata su **True**.  
  
## <a name="creating-an-instance-of-a-custom-component"></a>Creazione di un'istanza di un componente personalizzato  
 Il passaggio successivo consiste nel creare un'istanza del componente personalizzato nel modulo. Poiché il **casella degli strumenti** automaticamente gli account per il nuovo componente, è semplice come la creazione di qualsiasi altro componente o controllo.  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a>Per creare un'istanza di un componente personalizzato  
  
1. Aprire il form del progetto nel **progettazione form**.  
  
2. Nel **casella degli strumenti**, fare clic sulla scheda nuovo chiamata **Componenti ToolboxExample**.  
  
     Dopo aver selezionato la scheda, si noterà **DemoComponent**.  
  
    > [!NOTE]
    >  Per motivi di prestazioni, i componenti nell'area popolato automaticamente della **casella degli strumenti** non vengono visualizzate le bitmap personalizzate e <xref:System.Drawing.ToolboxBitmapAttribute> non è supportato. Per visualizzare un'icona per un componente personalizzato nella **casella degli strumenti**, utilizzare il **Scegli elementi della casella degli strumenti** finestra di dialogo per caricare il componente.  
  
3. Trascinare il componente al form.  
  
     Viene creata e aggiunto a un'istanza del componente di **sulla barra dei componenti**.  
  
## <a name="unloading-and-reloading-a-custom-component"></a>Scaricare e ricaricare un componente personalizzato  
 Il **casella degli strumenti** tengano conto dei componenti in ogni progetto di caricamento e quando viene scaricato un progetto, vengono rimossi i riferimenti ai componenti del progetto.  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a>Per sperimentare l'effetto della casella degli strumenti di scaricamento e il ricaricamento di componenti  
  
1. Scaricare il progetto dalla soluzione.  
  
     Per altre informazioni sullo scaricamento dei progetti, vedere [come: Scaricare e ricaricare i progetti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)). Se viene chiesto di salvare, scegliere **Sì**.  
  
2. Aggiungere un nuovo **applicazioni Windows** progetto alla soluzione. Aprire il form nel **progettazione**.  
  
     Il **Componenti ToolboxExample** scheda dal progetto precedente è stata ancora attivo.  
  
3. Ricarica il `ToolboxExample` progetto.  
  
     Il **Componenti ToolboxExample** scheda ora viene visualizzata di nuovo.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa procedura dettagliata viene dimostrato che la **casella degli strumenti** prende in considerazione i componenti di un progetto, ma la **della casella degli strumenti** è anche dei controlli. Sperimentare con i controlli personalizzati aggiungendo e rimuovendo i progetti di controllo dalla soluzione.  
  
## <a name="see-also"></a>Vedere anche

- [Generale, finestra di progettazione di Windows Form, finestra di dialogo Opzioni](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))
- [Procedura: Organizzare le schede della casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))
- [Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))
- [Inserimento di controlli in Windows Form](putting-controls-on-windows-forms.md)
