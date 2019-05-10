---
title: "Procedura: Associare dati utilizzando un'origine dati di progetto (WCF Data Services)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: 2477af0a-676f-44f7-b73d-e66208785509
ms.openlocfilehash: 69a0ec657f0a8cec34048776a4767cec23d091d9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645643"
---
# <a name="how-to-bind-data-using-a-project-data-source-wcf-data-services"></a>Procedura: Associare dati utilizzando un'origine dati di progetto (WCF Data Services)

È possibile creare origini dati che si basano sugli oggetti dati generati in un'applicazione client WCF Data Services. Quando si aggiunge un riferimento a un servizio dati tramite il **Aggiungi riferimento al servizio** finestra di dialogo, un'origine dati del progetto viene creata con le classi dati client generate. Per ogni set di entità esposto dal servizio dati viene creata un'origine dati. È possibile creare form che visualizzino i dati del servizio mediante il trascinamento di questi elementi di origine dati dal **Zdroje dat** finestra nella finestra di progettazione. Questi elementi diventeranno controlli associati all'origine dati. Durante l'esecuzione, questa origine dati è associata a un'istanza del <xref:System.Data.Services.Client.DataServiceCollection%601> classe, che viene riempita con oggetti restituiti da una query al servizio dati. Per altre informazioni, vedere [associazione di dati a controlli](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).

 Negli esempi riportati in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).

## <a name="use-a-project-data-source-in-a-wpf-window"></a>Usare un'origine dati del progetto in una finestra WPF

1. In Visual Studio in un progetto WPF aggiungere un riferimento al servizio dati Northwind. Per altre informazioni, vedere [Procedura: Aggiungere un riferimento al servizio dati](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).

2. Nel **Zdroje dat** finestra, espandere il `Customers` nodo il **NorthwindEntities** origine dati del progetto.

3. Fare clic sul **CustomerID** elemento, scegliere **ComboBox** dall'elenco e trascinare il **CustomerID** elemento dal **clienti** nodo per il finestra di progettazione.

     Nel file XAML per la finestra verranno creati gli elementi oggetto seguenti:

    - Un elemento <xref:System.Windows.Data.CollectionViewSource> denominato `customersViewSource`. La proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> dell'elemento oggetto <xref:System.Windows.Controls.Grid> di primo livello viene impostata sul nuovo oggetto <xref:System.Windows.Data.CollectionViewSource>.

    - Un oggetto <xref:System.Windows.Controls.ComboBox> con associazione a dati denominato `CustomerID`.

    - Oggetto <xref:System.Windows.Controls.Label>.

4. Trascinare il **ordini** proprietà di navigazione nella finestra di progettazione.

     Nel file XAML per la finestra verranno creati gli elementi oggetto aggiuntivi seguenti:

    - Un secondo elemento <xref:System.Windows.Data.CollectionViewSource> denominato `customersOrdersViewSource`, la cui origine è `customerViewSource`.

    - Un controllo <xref:System.Windows.Controls.DataGrid> con associazione a dati denominato `ordersDataGrid`.

5. (Facoltativo) Trascinare gli elementi aggiuntivi dal **clienti** nodo nella finestra di progettazione.

6. Aprire la tabella codici per il form e aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):

     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersusingwpf)]

7. Nella classe parziale che definisce il form aggiungere il codice seguente per creare un'istanza di <xref:System.Data.Objects.ObjectContext> e definire la costante `customerID`.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersdefinitionwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf2.xaml.vb#customersordersdefinitionwpf)]

8. Nella finestra di progettazione selezionare la finestra.

    > [!NOTE]
    > Assicurarsi di selezionare la finestra stessa anziché il contenuto incluso nella finestra. Se si seleziona la finestra, il **Name** casella di testo nella parte superiore della **proprietà** finestra deve contenere il nome della finestra.

9. Nel **delle proprietà** finestra, seleziona la **eventi** pulsante.

10. Trovare il **Loaded** evento e quindi fare doppio clic sul menu a discesa elenco accanto a questo evento.

     In Visual Studio verrà aperto il file code-behind per la finestra e verrà generato un gestore di eventi <xref:System.Windows.FrameworkElement.Loaded>.

11. Nel gestore di eventi <xref:System.Windows.FrameworkElement.Loaded> appena creato copiare e incollare il codice che segue.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersdatabindingwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf2.xaml.vb#customersordersdatabindingwpf)]

12. Tramite questo codice viene creata un'istanza di <xref:System.Data.Services.Client.DataServiceCollection%601> per il tipo di `Customers` in base all'esecuzione di una query LINQ che restituisce un oggetto <xref:System.Collections.Generic.IEnumerable%601> di `Customers` insieme agli oggetti `Orders` correlati dal servizio dati Northwind e tale istanza viene associata a `customersViewSource`.

## <a name="use-a-project-data-source-in-a-windows-form"></a>Usare un'origine dati del progetto in un modulo di Windows

1. Nel **Zdroje dat** finestra, espandere il **clienti** nodo il **NorthwindEntities** origine dati del progetto.

2. Fare clic sul **CustomerID** elemento, scegliere **ComboBox** dall'elenco e trascinare il **CustomerID** elemento dal **clienti** nodo per il finestra di progettazione.

     Nel form verranno creati i controlli seguenti:

    - Un'istanza di <xref:System.Windows.Forms.BindingSource> denominata `customersBindingSource`.

    - Un'istanza di <xref:System.Windows.Forms.BindingNavigator> denominata `customersBindingNavigator`. È possibile eliminare questo controllo in quanto non necessario.

    - Un oggetto <xref:System.Windows.Forms.ComboBox> con associazione a dati denominato `CustomerID`.

    - Oggetto <xref:System.Windows.Forms.Label>.

3. Trascinare il **ordini** proprietà di navigazione al form.

4. Verrà creato il controllo `ordersBindingSource` con la proprietà <xref:System.Windows.Forms.BindingSource.DataSource%2A> impostata su `customersBindingSource` e la proprietà <xref:System.Windows.Forms.BindingSource.DataMember%2A> impostata su `Customers`. Nel form verrà inoltre creato il controllo con associazione a dati `ordersDataGridView`, accompagnato da un controllo etichetta con il titolo appropriato.

5. (Facoltativo) Trascinare gli elementi aggiuntivi dal **clienti** nodo nella finestra di progettazione.

6. Aprire la tabella codici per il form e aggiungere le istruzioni `using` seguenti (`Imports` in Visual Basic):

     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersusing)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersusing)]

7. Nella classe parziale che definisce il form aggiungere il codice seguente per creare un'istanza di <xref:System.Data.Objects.ObjectContext> e definire la costante `customerID`.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdefinition)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdefinition)]

8. Nella finestra di progettazione dei form fare doppio clic sul form.

     Verrà visualizzata la tabella codici per il form e verrà creato il metodo che gestisce l'evento `Load` per il form.

9. Nel gestore di eventi `Load` copiare e incollare il codice riportato di seguito.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdatabinding)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdatabinding)]

10. Tramite questo codice viene creata un'istanza di <xref:System.Data.Services.Client.DataServiceCollection%601> per il tipo di `Customers` in base all'esecuzione di un oggetto <xref:System.Data.Services.Client.DataServiceQuery%601> che restituisce un oggetto <xref:System.Collections.Generic.IEnumerable%601> di `Customers` dal servizio dati Northwind e tale istanza viene associata a `customersBindingSource`.

## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Procedura: Associare dati a elementi Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)
