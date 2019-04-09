---
title: "Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: e5ba42c2ff86f46e2722d0f4455c10ab7b85af1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204653"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms
Nell'esempio di codice seguente viene illustrato come usare il controllo <xref:System.Windows.Forms.DataGridView> per segnalare all'utente eventuali errori di immissione dei dati.  
  
 Per una spiegazione completa di questo esempio di codice, vedere [procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nella finestra di Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Data, System.Windows.Forms e System.XML.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Immissione di dati nel controllo DataGridView Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Convalida dei dati nel controllo DataGridView di Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
