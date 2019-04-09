---
title: "Procedura dettagliata: Esecuzione di un'operazione in background"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: cb06aa6bfa960a493090b67c8baa4d7b3b46756a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149084"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>Procedura dettagliata: Esecuzione di un'operazione in background
Se l'esecuzione di un'operazione richiede molto tempo e si vogliono evitare ritardi nella risposta dell'interfaccia utente, è possibile usare la classe <xref:System.ComponentModel.BackgroundWorker> per eseguire l'operazione in un altro thread.  
  
 Per un elenco completo del codice usato in questo esempio, vedere [come: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-run-an-operation-in-the-background"></a>Per eseguire un'operazione in background  
  
1.  Aprire il modulo attivo in Progettazione Windows Form e trascinare due <xref:System.Windows.Forms.Button> dei controlli il **della casella degli strumenti** al form e quindi impostare il `Name` e <xref:System.Windows.Forms.Control.Text%2A> le proprietà dei pulsanti in base alla tabella riportata di seguito.  
  
    |Button|Nome|Testo|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|**Inizia**|  
    |`button2`|`cancelBtn`|**Annulla**|  
  
2.  Aprire il **casella degli strumenti**, fare clic sul **componenti** scheda e quindi trascinare il <xref:System.ComponentModel.BackgroundWorker> componente al form.  
  
     Il `backgroundWorker1` viene visualizzato nel componente le **sulla barra dei componenti**.  
  
3.  Nella finestra **Proprietà** impostare la proprietà <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> su `true`.  
  
4.  Nel **proprietà** finestra, fare clic sul **eventi** pulsante e quindi fare doppio clic il <xref:System.ComponentModel.BackgroundWorker.DoWork> e <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> eventi per creare gestori eventi.  
  
5.  Inserire il codice che richiedono molto tempo nel <xref:System.ComponentModel.BackgroundWorker.DoWork> gestore dell'evento.  
  
6.  Estrarre eventuali parametri richiesti dall'operazione dei <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> proprietà del <xref:System.ComponentModel.DoWorkEventArgs> parametro.  
  
7.  Assegnare il risultato del calcolo per il <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> proprietà del <xref:System.ComponentModel.DoWorkEventArgs>.  
  
     Si tratta di verranno messe a disposizione il <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore dell'evento.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  Inserire il codice per recuperare il risultato dell'operazione nel <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> gestore dell'evento.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. Implementare il metodo `TimeConsumingOperation`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. Nella finestra di progettazione Windows Form, fare doppio clic su `startButton` per creare il <xref:System.Windows.Forms.Control.Click> gestore dell'evento.  
  
11. Chiamare il <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> metodo nella <xref:System.Windows.Forms.Control.Click> gestore eventi per `startButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. Nella finestra di progettazione Windows Form, fare doppio clic su `cancelButton` per creare il <xref:System.Windows.Forms.Control.Click> gestore dell'evento.  
  
13. Chiamare il <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> metodo nella <xref:System.Windows.Forms.Control.Click> gestore eventi per `cancelButton`.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. Nella parte superiore del file, importare gli spazi dei nomi System. ComponentModel e System. Threading.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. Premere F6 per compilare la soluzione e quindi premere CTRL+F5 per eseguire l'applicazione all'esterno del debugger.  
  
> [!NOTE]
>  Se si preme F5 per eseguire l'applicazione nel debugger, l'eccezione generata nel `TimeConsumingOperation` metodo viene rilevato e visualizzato dal debugger. Quando si esegue l'applicazione all'esterno del debugger, il <xref:System.ComponentModel.BackgroundWorker> gestisce l'eccezione e li inserisce nel <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> proprietà del <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.  
  
1.  Fare clic sui **avviare** pulsante per eseguire un'operazione asincrona e quindi fare clic sui **Annulla** sul pulsante per arrestare l'esecuzione dell'operazione asincrona.  
  
     Il risultato di ciascuna operazione viene visualizzato in una finestra di messaggio <xref:System.Windows.Forms.MessageBox>.  
  
## <a name="next-steps"></a>Passaggi successivi  
  
-   Implementare un form che segnala lo stato del processo di un'operazione asincrona. Per altre informazioni, vedere [Procedura: Implementare un Form che usa un'operazione in Background](how-to-implement-a-form-that-uses-a-background-operation.md).  
  
-   Implementare una classe che supporta il modello asincrono per i componenti. Per altre informazioni, vedere [implementazione del modello asincrono basato su eventi](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [Procedura: Implementare un modulo che usa un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Procedura: Eseguire un'operazione in background](how-to-run-an-operation-in-the-background.md)
- [Componente BackgroundWorker](backgroundworker-component.md)
