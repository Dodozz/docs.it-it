---
title: 'Procedura: Chiamare una Stored Procedure utilizzando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: af25ebe10681ebb1c346f90afc0291e53224833a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319573"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Procedura: Chiamare una Stored Procedure utilizzando LINQ (Visual Basic)
Language-Integrated Query (LINQ) semplifica accedere alle informazioni di database, tra cui database oggetti, ad esempio stored procedure.  
  
 Nell'esempio seguente viene illustrato come creare un'applicazione che chiama una stored procedure in un database di SQL Server. Nell'esempio viene illustrato come chiamare due diverse stored procedure nel database. Ogni routine restituisce i risultati di una query. Una procedura accetta i parametri di input e l'altra routine non accetta parametri.  
  
 Gli esempi in questo argomento usano il database di esempio Northwind. Se non è questo database nel computer di sviluppo, è possibile scaricarlo da Microsoft Download Center. Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Per creare una connessione a un database  
  
1. In Visual Studio, aprire **Esplora Server**/**Database Explorer** facendo **Esplora Server**/**Database Esplora** nella **visualizzazione** menu.  
  
2. Fare doppio clic su **connessioni dati** nelle **Esplora Server**/**Esplora Database** e quindi fare clic su **Aggiungi connessione**.  
  
3. Specificare una connessione valida al database di esempio Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Per aggiungere un progetto che contiene un file LINQ to SQL  
  
1. In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**. Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.  
  
2. Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**. Selezionare il **classi LINQ to SQL** modello di elemento.  
  
3. Denominare il file `northwind.dbml`. Fare clic su **Aggiungi**. Viene aperto il Object Relational Designer (O/R Designer) per il file Northwind. dbml.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Per aggiungere stored procedure a O/R Designer  
  
1. Nelle **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind. Espandere la **Stored procedure** cartella.  
  
     Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic sul file Northwind. dbml aggiunti in precedenza.  
  
2. Scegliere il **Sales by Year** stored procedure e trascinarlo nel riquadro a destra della finestra di progettazione. Scegliere il **Ten Most Expensive Products** stored procedure trascinarla nel riquadro a destra della finestra di progettazione.  
  
3. Salvare le modifiche e chiudere la finestra di progettazione.  
  
4. Salvare il progetto.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Per aggiungere il codice per visualizzare i risultati delle stored procedure.  
  
1. Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Form di Windows predefinito per il progetto, Form1.  
  
2. Fare doppio clic su Form1 per aggiungere codice al relativo `Load` evento.  
  
3. Quando si aggiungono le stored procedure per la finestra di Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto per il progetto. Questo oggetto contiene il codice che è necessario disporre per accedere a tali procedure. Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml. Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.  
  
     È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> nel codice e chiamare i metodi della stored procedure specificata da O/R Designer. Per associare al <xref:System.Windows.Forms.DataGridView> dell'oggetto, potrebbe essere necessario forzare la query vengono eseguite immediatamente chiamando il <xref:System.Linq.Enumerable.ToList%2A> metodo sui risultati della stored procedure.  
  
     Aggiungere il codice seguente per il `Load` chiamare una delle stored procedure esposte come metodi per il contesto dati dell'evento.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. Premere F5 per eseguire il progetto e visualizzare i risultati.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
