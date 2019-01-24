---
title: Modalità virtuale nel controllo DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- virtual data binding [Visual Basic]
- DataRepeater
- DataRepeater, virtual mode
ms.assetid: 5fb805dc-2d8b-4139-b1e3-86e4c2667221
ms.openlocfilehash: 3988c16746606de9f20f9a66b87539b6cea04758
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700806"
---
# <a name="virtual-mode-in-the-datarepeater-control-visual-studio"></a>Modalità virtuale nel controllo DataRepeater (Visual Studio)
Quando si desidera visualizzare grandi quantità di dati tabulari in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> (controllo), è possibile migliorare le prestazioni, impostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> proprietà `True` e gestendo in modo esplicito l'interazione del controllo con l'origine dati. Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo fornisce diversi eventi che è possibile gestire per interagire con l'origine dati e visualizzare i dati in base alle esigenze in fase di esecuzione.  
  
## <a name="how-virtual-mode-works"></a>Funzionamento della modalità virtuale come  
 Lo scenario più comune per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo consiste nell'associare i controlli figlio del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> a una data di origine in fase di progettazione e consentire il <xref:System.Windows.Forms.BindingSource> per passare i dati e viceversa in base alle esigenze. Quando si usa la modalità virtuale, i controlli non sono associati a un'origine dati e dati vengono passati avanti e indietro all'origine dati sottostante in fase di esecuzione.  
  
 Quando la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> è impostata su `True`, creare l'interfaccia utente aggiungendo i controlli dalle **della casella degli strumenti** invece di aggiungere controlli associati dal **Zdroje dat** finestra.  
  
 È necessario aggiungere il codice per gestire la visualizzazione di dati e gli eventi vengono generati in modo da controlli. Quando un nuovo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> è mostrata nella visualizzazione di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> evento viene generato una volta per ogni controllo ed è necessario fornire i valori per ogni controllo nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> gestore dell'evento.  
  
 Se i dati in uno dei controlli viene modificati dall'utente, il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> viene generato l'evento ed è necessario convalidare i dati e salvarlo per l'origine dati.  
  
 Se l'utente aggiunge un nuovo elemento, il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> viene generato l'evento. Utilizzare questo gestore di evento per creare un nuovo record nell'origine dati. Per evitare modifiche accidentali, è necessario monitorare anche il <xref:System.Windows.Forms.Control.KeyDown> evento per ogni controllo e chiamare <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> se l'utente preme il tasto ESC.  
  
 Se i dati di origine viene modificata, è possibile aggiornare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo chiamando la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> e <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> metodi. Entrambi i metodi devono essere chiamati in ordine.  
  
 Infine, è necessario implementare i gestori eventi per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> evento si verifica quando viene eliminato un elemento e, facoltativamente, per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletingItems> e <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.UserDeletedItems> che si verificano ogni volta che un utente elimina un elemento premendo il tasto CANC.  
  
## <a name="implementing-virtual-mode"></a>Implementazione della modalità virtuale  
 Di seguito sono i passaggi necessari per implementare la modalità virtuale.  
  
#### <a name="to-implement-virtual-mode"></a>Per implementare la modalità virtuale  
  
1.  Trascinare un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllare dal **Visual Basic Power Packs** scheda il **casella degli strumenti** a un form o un controllo contenitore. Impostare la proprietà <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> su `True`.  
  
2.  Trascinare i controlli dal **casella degli strumenti** nell'area modello dell'elemento (l'area superiore) del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. È necessario un controllo per ogni campo nell'origine dati che si desidera visualizzare.  
  
3.  Implementare un gestore per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded> eventi per fornire valori per ogni controllo. Questo evento viene generato quando un nuovo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> di scorrimento nella visualizzazione. Il codice sarà simile all'esempio seguente, che fa riferimento a un'origine dati denominata `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_1.cs)]  
  
4.  Implementare un gestore per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> archiviare i dati dell'evento. Questo evento viene generato quando l'utente esegue il commit delle modifiche a un controllo figlio del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>. Il codice sarà simile all'esempio seguente, che fa riferimento a un'origine dati denominata `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_2.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_2.cs)]  
  
5.  Implementare un gestore per ogni controllo figlio <xref:System.Windows.Forms.Control.KeyDown> eventi e monitoraggio il tasto ESC. Chiamare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CancelEdit%2A> metodo per impedire la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed> generazione dell'evento. Il codice sarà simile all'esempio seguente.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_3.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_3.cs)]  
  
6.  Implementare un gestore per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded> evento. Questo evento viene generato quando l'utente aggiunge un nuovo elemento per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Il codice sarà simile all'esempio seguente, che fa riferimento a un'origine dati denominata `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_4.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_4.cs)]  
  
7.  Implementare un gestore per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemsRemoved> evento. Questo evento si verifica quando un utente elimina un elemento esistente. Il codice sarà simile all'esempio seguente, che fa riferimento a un'origine dati denominata `Employees`.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_5.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_5.cs)]  
  
8.  Per la convalida a livello di controllo, è possibile implementare i gestori per il <xref:System.Windows.Forms.Control.Validating> gli eventi dei controlli figlio. Il codice sarà simile all'esempio seguente.  
  
     [!code-vb[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/virtual-mode-in-the-datarepeater-control-visual-studio_6.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterVirtualMode#6](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/virtual-mode-in-the-datarepeater-control-visual-studio_6.cs)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValuePushed>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.NewItemNeeded>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemValueNeeded>
- [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
