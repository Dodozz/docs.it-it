---
title: Oggetti DataSet, DataTable e DataView
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: abfb53b0a7d827ffe8df909746c0c0ad0ce8c57b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750759"
---
# <a name="datasets-datatables-and-dataviews"></a>Oggetti DataSet, DataTable e DataView
L'oggetto <xref:System.Data.DataSet> di ADO.NET è una rappresentazione di dati residente in memoria, che fornisce un modello di programmazione relazionale coerente indipendentemente dall'origine dati in esso contenuta. Un <xref:System.Data.DataSet> rappresenta un set completo di dati che include le tabelle in cui sono contenuti, ordinati e vincolati i dati e le relazioni tra le tabelle.  
  
 Per usare un <xref:System.Data.DataSet> sono disponibili numerosi metodi, che è possibile applicare singolarmente o in combinazione. È possibile:  
  
- Creare a livello di programmazione degli oggetti <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> e <xref:System.Data.Constraint> all'interno di un <xref:System.Data.DataSet> e compilare le tabelle con i dati.  
  
- Compilare il tipo <xref:System.Data.DataSet> con tabelle di dati provenienti da un'origine dati relazionale esistente usando un `DataAdapter`.  
  
- Caricare e mantenere il contenuto del <xref:System.Data.DataSet> usando XML. Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
 Un <xref:System.Data.DataSet> tipizzato in modo sicuro può anche essere trasportato usando un servizio Web XML. Grazie alla struttura che lo caratterizza, il <xref:System.Data.DataSet> è ideale per il trasporto di dati tramite i servizi Web XML. Per una panoramica dei servizi Web XML, vedere [Panoramica dei servizi Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)). Per un esempio di utilizzo di un <xref:System.Data.DataSet> da un servizio Web XML, vedere [Uso di un set di dati da un servizio Web XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 Viene descritta la sintassi per la creazione di un'istanza di un tipo <xref:System.Data.DataSet>.  
  
 [Aggiunta di un oggetto DataTable a un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 Viene descritto come creare e aggiungere tabelle e colonne a un <xref:System.Data.DataSet>.  
  
 [Aggiunta di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 Viene descritto come creare le relazioni tra tabelle in un <xref:System.Data.DataSet>.  
  
 [Esplorazione di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 Viene descritto come usare le relazioni tra tabelle in un <xref:System.Data.DataSet> per restituire le righe padre o figlio di una relazione padre-figlio.  
  
 [Unione di contenuti di set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 Viene descritto come unire il contenuto di una matrice di <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow> in un altro <xref:System.Data.DataSet>.  
  
 [Copia di contenuti di set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 Viene descritto come creare una copia di un <xref:System.Data.DataSet> in cui possa essere contenuto lo schema e i dati specificati.  
  
 [Gestione di eventi di set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 Vengono descritti gli eventi di un <xref:System.Data.DataSet> e il relativo uso.  
  
 [Set di dati tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 Vengono illustrate le caratteristiche di un <xref:System.Data.DataSet> tipizzato e viene descritto come crearlo e usarlo.  
  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Viene descritto come creare una <xref:System.Data.DataTable>, definire lo schema e modificare i dati.  
  
 [DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 Viene descritto come creare e usare un oggetto <xref:System.Data.DataTableReader>.  
  
 [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 Viene descritto come creare e usare `DataViews` e come usare eventi <xref:System.Data.DataView>.  
  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Viene descritta l'interazione del <xref:System.Data.DataSet> con XML come origine dati, inclusi il caricamento e il mantenimento del contenuto di un <xref:System.Data.DataSet> sotto forma di dati XML.  
  
 [Utilizzo di un set di dati da un servizio Web XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 Viene descritto come creare un servizio Web XML che usa un <xref:System.Data.DataSet> per trasportare i dati.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Novità in ADO.NET](../../../../../docs/framework/data/adonet/whats-new.md)  
 Vengono descritte le nuove funzionalità di ADO.NET.  
  
 [Panoramica di ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Viene fornita un'introduzione alle caratteristiche e ai componenti di ADO.NET.  
  
 [Popolamento di un set di dati da un oggetto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Viene descritto come caricare un **DataSet** con dati da un'origine dati.  
  
 [Aggiornamento di origini dati con DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Viene descritto come applicare le modifiche apportate ai dati di un **DataSet** nell'origine dati.  
  
 [Aggiunta di vincoli esistenti a un set di dati](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Viene descritto come compilare un **DataSet** con informazioni relative alla chiave primaria provenienti da un'origine dati.  
  
## <a name="see-also"></a>Vedere anche

- [ADO.NET](../../../../../docs/framework/data/adonet/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
