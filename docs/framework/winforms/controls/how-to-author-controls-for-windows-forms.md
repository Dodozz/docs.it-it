---
title: 'Procedura: Creare controlli per Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
ms.openlocfilehash: a6ea57dda8f034684e8590ce4c3b6d37ab01230e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579524"
---
# <a name="how-to-author-controls-for-windows-forms"></a>Procedura: Creare controlli per Windows Form
Un controllo rappresenta un collegamento grafico tra l'utente e il programma. Un controllo può fornire o elaborare dati, accettare input dall'utente, rispondere a eventi o eseguire qualsiasi numero di altre funzioni che connettono l'utente e l'applicazione. Poiché un controllo è essenzialmente un componente con un'interfaccia grafica, può essere utilizzato per le stesse funzioni di un componente oltre che per consentire l'interazione dell'utente. I controlli vengono creati per scopi specifici e la creazione di controlli è semplicemente un'altra attività di programmazione. Tenendo conto di questo, i passaggi seguenti rappresentano una panoramica del processo di creazione di un controllo. I collegamenti forniscono altre informazioni sui singoli passaggi.  
  
> [!NOTE]
>  Per creare un controllo personalizzato da usare nei Web Form, vedere [Sviluppo di controlli server ASP.NET personalizzati](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
>   
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-author-a-control"></a>Per creare un controllo  
  
1.  Determinare ciò il controllo dovrà fare o quale ruolo svolgerà nell'applicazione. I fattori da considerare sono:  
  
    -   Quale tipo di interfaccia grafica è necessario?  
  
    -   Quali specifiche interazioni dell'utente saranno gestite da questo controllo?  
  
    -   Le funzionalità necessarie sono fornite da ogni controllo esistente?  
  
    -   È possibile ottenere le funzionalità richieste combinando diversi controlli Windows Form?  
  
2.  Se è necessario un modello di oggetti per il controllo, stabilire come le funzionalità verranno distribuite nel modello di oggetti e suddividere le funzionalità tra il controllo e gli eventuali oggetti secondari. Un modello di oggetti può essere utile se si intende creare un controllo complesso o si desidera incorporare varie funzionalità.  
  
3.  Determinare il tipo di controllo necessario (ad esempio controllo utente, controllo personalizzato, controllo Windows Form ereditato). Per informazioni dettagliate, vedere [Consigli sui tipi di controlli](../../../../docs/framework/winforms/controls/control-type-recommendations.md) e [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
4.  Definire le funzionalità come proprietà, metodi ed eventi del controllo e i relativi oggetti secondari o strutture secondarie e assegnare i livelli di accesso appropriati (ad esempio pubblico, protetto e così via).  
  
5.  Se è necessario un disegno personalizzato per il controllo, aggiungere codice per esso. Per informazioni dettagliate, vedere [Disegno e rendering di controlli personalizzati](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
6.  Se il controllo eredita da <xref:System.Windows.Forms.UserControl>, è possibile verificarne il comportamento di runtime compilando il progetto di controllo ed eseguendolo nel **UserControl Test Container**. Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
7.  È possibile testare ed eseguire il debug del controllo anche creando un nuovo progetto, ad esempio un'applicazione Windows, e inserendolo in un contenitore. Questo processo viene illustrato come parte di [procedura dettagliata: Modifica di un controllo composito con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md).  
  
8.  Quando si aggiunge ogni funzionalità, aggiungere le funzionalità al progetto di test per verificarne il funzionamento.  
  
9. Ripetere l'operazione, ottimizzando la struttura.  
  
10. Creare il pacchetto e distribuire il controllo. Per informazioni dettagliate, vedere [Distribuzione di applicazioni, servizi e componenti](https://msdn.microsoft.com/library/wtzawcsz).  
  
## <a name="see-also"></a>Vedere anche
- [Procedura dettagliata: Modifica di un controllo composito con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Procedura dettagliata: Eredità da un controllo di Windows Forms con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [Procedura: Ereditare dalla classe UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)
- [Procedura: Ereditare dalla classe Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)
- [Procedura: Ereditare da esistenti di Windows Form](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)
- [Procedura: Testare il comportamento in fase di esecuzione di UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
