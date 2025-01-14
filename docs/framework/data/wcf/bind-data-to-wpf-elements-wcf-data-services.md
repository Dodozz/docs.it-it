---
title: 'Procedura: Associare dati a elementi Windows Presentation Foundation (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
ms.openlocfilehash: cecfa42035d4c09eade708417c338ef04ab09ad9
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423819"
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a>Procedura: Associare dati a elementi Windows Presentation Foundation (WCF Data Services)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], è possibile associare elementi Windows Presentation Foundation (WPF), ad esempio un <xref:System.Windows.Controls.ListBox> oppure <xref:System.Windows.Controls.ComboBox> a un'istanza di <xref:System.Data.Services.Client.DataServiceCollection%601>, che gestisce gli eventi generati dai controlli per mantenere la <xref:System.Data.Services.Client.DataServiceContext> sincronizzato con le modifiche apportate ai dati nei controlli. Per altre informazioni, vedere [associazione di dati a controlli](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
 Nell'esempio riportato in questo argomento vengono usati il servizio dati Northwind di esempio e le classi del servizio dati client generate automaticamente. Questo servizio e le classi dati client vengono create quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente è tratto dalla pagina code-behind per una pagina XAML (Extensible Application Markup Language) che definisce la finestra `SalesOrders` in WPF. Quando la finestra viene caricata, un <xref:System.Data.Services.Client.DataServiceCollection%601> viene creato in base al risultato di una query che restituisce i clienti filtrati per paese/regione. Tutte le pagine di questo risultato di paging vengono caricate insieme agli ordini correlati e vengono associate alla proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> dell'oggetto <xref:System.Windows.Controls.StackPanel> che rappresenta il controllo di layout radice per la finestra WPF. Per altre informazioni, vedere [caricamento di contenuto posticipato](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a>Esempio  
 Nel codice XAML seguente viene definita la finestra `SalesOrders` in WPF per l'esempio precedente.  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente è tratto dalla pagina code-behind per una pagina XAML (Extensible Application Markup Language) che definisce la finestra `SalesOrders` in WPF. Quando la finestra viene caricata, un <xref:System.Data.Services.Client.DataServiceCollection%601> viene creato in base al risultato di una query che restituisce i clienti con gli oggetti correlati filtrati per paese/regione. Questo risultato viene associato alla proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> dell'oggetto <xref:System.Windows.Controls.StackPanel> che rappresenta il controllo di layout radice per la finestra WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a>Esempio  
 Nel codice XAML seguente viene definita la finestra `SalesOrders` in WPF per l'esempio precedente.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]
