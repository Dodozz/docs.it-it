---
title: 'Procedura: Associare dati al controllo DataGridView di Windows Form'
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e147109a64687177f201ad1e312fab56ea61d604
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010930"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="d989f-102">Procedura: Associare dati al controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d989f-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="d989f-103">Il <xref:System.Windows.Forms.DataGridView> controllo supporta il modello di associazione dati standard di Windows Form, pertanto è possibile associare a un'ampia gamma di origini dati.</span><span class="sxs-lookup"><span data-stu-id="d989f-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="d989f-104">In genere, si associa a un <xref:System.Windows.Forms.BindingSource> che gestisce l'interazione con l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d989f-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="d989f-105">Il <xref:System.Windows.Forms.BindingSource> può essere qualsiasi origine dati di Windows Form, che consente una notevole flessibilità, la scelta o la modifica del percorso dei dati.</span><span class="sxs-lookup"><span data-stu-id="d989f-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="d989f-106">Per altre informazioni sulle origini dati di <xref:System.Windows.Forms.DataGridView> controllo supporta, vedere la [Cenni preliminari sul controllo DataGridView](datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d989f-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="d989f-107">Visual Studio offre supporto completo per il data binding al controllo DataGridView.</span><span class="sxs-lookup"><span data-stu-id="d989f-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="d989f-108">Per altre informazioni, vedere [Procedura: Associare dati al controllo DataGridView di Windows Form usando la finestra di progettazione](bind-data-to-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="d989f-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="d989f-109">Per connettere un controllo DataGridView ai dati:</span><span class="sxs-lookup"><span data-stu-id="d989f-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="d989f-110">Implementare un metodo per gestire i dettagli del recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="d989f-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="d989f-111">Il codice seguente esempio implementa un `GetData` metodo che inizializza un <xref:System.Data.SqlClient.SqlDataAdapter>e lo usa per popolare un <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="d989f-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d989f-112">Viene quindi associato il <xref:System.Data.DataTable> per il <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="d989f-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="d989f-113">Il modulo <xref:System.Windows.Forms.Form.Load> gestore dell'evento, associare il <xref:System.Windows.Forms.DataGridView> il controllo al <xref:System.Windows.Forms.BindingSource>e chiamare il `GetData` metodo per recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="d989f-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="d989f-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="d989f-114">Example</span></span>

<span data-ttu-id="d989f-115">In questo esempio di codice completo recupera i dati da un database per popolare un controllo DataGridView in un modulo di Windows.</span><span class="sxs-lookup"><span data-stu-id="d989f-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="d989f-116">Il form contiene inoltre i pulsanti per ricaricare i dati e inviare modifiche al database.</span><span class="sxs-lookup"><span data-stu-id="d989f-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="d989f-117">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d989f-117">This example requires:</span></span> 

- <span data-ttu-id="d989f-118">Accesso a un database di esempio Northwind di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d989f-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="d989f-119">Per altre informazioni sull'installazione di database di esempio Northwind, vedere [ottenere i database di esempio per gli esempi di codice ADO.NET](../../data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="d989f-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="d989f-120">Riferimenti agli assembly System, System, System. Data e System. Xml.</span><span class="sxs-lookup"><span data-stu-id="d989f-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="d989f-121">Per compilare ed eseguire questo esempio, incollare il codice nel *Form1* file di codice in un nuovo progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d989f-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="d989f-122">Per informazioni sulla compilazione dal C# o riga di comando di Visual Basic, vedere [della riga di comando edificio con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oppure [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="d989f-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="d989f-123">Popolare il `connectionString` variabili nell'esempio con i valori per la connessione di database di esempio Northwind di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d989f-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="d989f-124">L'autenticazione di Windows, denominato anche sicurezza integrata, è un modo più sicuro per la connessione al database di archiviare una password nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="d989f-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="d989f-125">Per altre informazioni sulla sicurezza della connessione, vedere [proteggere le informazioni di connessione](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="d989f-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d989f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d989f-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d989f-127">Visualizzare i dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d989f-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d989f-128">Proteggere le informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="d989f-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
