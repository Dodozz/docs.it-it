---
title: Errori in fase di progettazione in Progettazione Windows Form
ms.date: 03/30/2017
f1_keywords:
- DTELErrorList
- WhyDTELPage
helpviewer_keywords:
- errors [Windows Forms Designer]
- design-time errors [Windows Forms Designer]
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
ms.openlocfilehash: 64a0b8d0d0d9f0cc2bc2a841b999af58f29b4f75
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718051"
---
# <a name="design-time-errors-in-the-windows-forms-designer"></a>Errori in fase di progettazione in Progettazione Windows Form
In questo argomento viene illustrato il significato e l'uso dell'elenco errori della fase di progettazione visualizzato in Microsoft Visual Studio quando il caricamento di Progettazione Windows Form non riesce. Se viene visualizzato questo elenco di errori non si deve interpretarlo come un bug della progettazione, ma come ausilio per la correzione degli errori nel codice.  
  
 Una conoscenza di base di questo elenco di errori consentirà di eseguire il debug delle applicazioni fornendo informazioni dettagliate sugli errori e suggerendo le possibili soluzioni.  
  
## <a name="the-design-time-error-list-interface"></a>L'interfaccia dell'elenco di errori in fase di progettazione  
 Se Progettazione Windows Form non viene caricato, verrà visualizzato un elenco di errori nella finestra di progettazione. Gli errori sono raggruppati in categorie. Ad esempio, se si dispone di quattro istanze di variabili non dichiarate, queste verranno raggruppate nella stessa categoria di errori. Ogni categoria di errori include una breve descrizione che riepiloga l'errore.  
  
 È possibile espandere o comprimere una categoria di errore facendo clic sull'intestazione della categoria di errori oppure facendo clic sulla freccia di espansione di espansione/compressione. Quando si espande una categoria di errori, vengono visualizzate le seguenti informazioni aggiuntive:  
  
-   Istanze dell'errore.  
  
-   Informazioni sull'errore.  
  
-   Post dei forum sull'errore.  
  
### <a name="instances-of-this-error"></a>Istanze dell'errore  
 Nelle informazioni sono elencate tutte le istanze dell'errore nel progetto corrente. Molti errori evidenziano un percorso esatto nel formato seguente: *[nome progetto]* *[nome modulo]* riga:*[numero riga]* colonna:*[numero colonna]*. Il collegamento **Vai al codice** consente di visualizzare il percorso nel codice in cui si verifica l'errore.  
  
 Se uno stack di chiamate è associato all'errore, è possibile selezionare il collegamento **Mostra stack di chiamate** che espande ulteriormente l'errore per visualizzare lo stack di chiamate. L'analisi dello stack può fornire informazioni utili sul debug. Ad esempio, è possibile rilevare le funzioni chiamate prima del verificarsi dell'errore. Lo stack di chiamate è selezionabile, in modo da poterlo copiare e salvare.  
  
> [!NOTE]
>  In Visual Basic l'elenco degli errori in fase di progettazione non mostra più di un errore, ma è possibile visualizzare più istanze dello stesso errore. In Visual C++ gli errori non sono dotati di collegamenti per andare al codice o al numero di riga.  
  
### <a name="help-with-this-error"></a>Informazioni sull'errore  
 Se l'errore contiene un collegamento a un argomento della Guida MSDN associato, nelle informazioni aggiuntive verrà incluso un collegamento all'argomento della Guida. Quando si fa clic sul collegamento, l'argomento della Guida associato viene visualizzato in Visual Studio.  
  
### <a name="forum-posts-about-this-error"></a>Post dei forum sull'errore  
 Nelle informazioni aggiuntive verrà incluso un collegamento ai post del forum MSDN relativi all'errore. La ricerca viene effettuata nei forum sulla base della stringa del messaggio di errore. È anche possibile provare a effettuare una ricerca nei seguenti forum:  
  
-   [Forum di Progettazione Windows Form](https://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [Forum di Windows Form](https://go.microsoft.com/fwlink/?LinkId=203523)  
  
### <a name="ignore-and-continue"></a>Ignora e continua  
 È possibile ignorare la condizione di errore e continuare a caricare la finestra di progettazione. La scelta di questa azione può produrre risultati imprevisti. Ad esempio, nell'area di progettazione potrebbero non venire visualizzati alcuni controlli.  
  
## <a name="see-also"></a>Vedere anche
- [Risoluzione dei problemi relativi allo sviluppo in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))
- [Risoluzione dei problemi relativi alla modifica di controlli e componenti](troubleshooting-control-and-component-authoring.md)
- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Messaggi di errore di Progettazione Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233640(v=vs.100))
