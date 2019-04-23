---
title: Dataset ADO.NET
ms.date: 03/30/2017
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
ms.openlocfilehash: 50e8e8f5e4b3ee2f5a41cb9dad11b5e701135d9e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190938"
---
# <a name="adonet-datasets"></a>Dataset ADO.NET
L'oggetto <xref:System.Data.DataSet> è fondamentale per il supporto di scenari di dati disconnessi e distribuiti con [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. Il **set di dati** è una rappresentazione residente in memoria dei dati che fornisce un modello di programmazione relazionale coerente indipendentemente dall'origine dati. È possibile usarlo con numerose origini dati diverse, con dati XML o per la gestione di dati locali all'applicazione. Il **set di dati** rappresenta un set completo di dati che include tabelle correlate, vincoli e relazioni tra le tabelle. La figura seguente mostra le **set di dati** modello a oggetti.  
  
 ![ADO.Net graphic](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Modello a oggetti DataSet  
  
 I metodi e gli oggetti in un **set di dati** siano coerenti con quelli presenti nel modello di database relazionale.  
  
 Il **set di dati** possono anche mantenere e ricaricare il contenuto come XML e il relativo schema come schema XML schema definition language (XSD). Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="the-datatablecollection"></a>DataTableCollection  
 Un' [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **set di dati** contiene una raccolta di zero o più tabelle rappresentate da <xref:System.Data.DataTable> oggetti. Il <xref:System.Data.DataTableCollection> contiene tutte le **DataTable** gli oggetti in un **set di dati**.  
  
 Oggetto **DataTable** definito nel <xref:System.Data> dello spazio dei nomi e rappresenta una singola tabella di dati residenti in memoria. In tale oggetto sono contenuti una raccolta di colonne rappresentata da un tipo <xref:System.Data.DataColumnCollection> e dei vincoli rappresentati da un tipo <xref:System.Data.ConstraintCollection>. Lo schema della tabella viene definito da questi due elementi. Oggetto **DataTable** inoltre contiene una raccolta di righe, rappresentate dal <xref:System.Data.DataRowCollection>, che contiene i dati nella tabella. Oltre allo stato corrente, in <xref:System.Data.DataRow> vengono mantenute sia la versione corrente che la versione originale, in modo da consentire l'identificazione delle modifiche apportate ai valori memorizzati nella riga.  
  
## <a name="the-dataview-class"></a>Classe DataView  
 Un oggetto <xref:System.Data.DataView> consente di creare diverse visualizzazioni dei dati archiviati in un oggetto <xref:System.Data.DataTable>. Questa funzionalità è usata spesso nelle applicazioni di associazione dati. Usando un oggetto <xref:System.Data.DataView>, è possibile esporre i dati di una tabella applicando diversi tipi di ordinamento e filtrare i dati per stato di riga o sulla base di un'espressione di filtro. Per altre informazioni, vedere [DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  
 Oggetto **set di dati** che contiene le relazioni nel relativo <xref:System.Data.DataRelationCollection> oggetto. Una relazione, rappresentata dal <xref:System.Data.DataRelation> oggetti, associa le righe in una **DataTable** con le righe in un altro **DataTable**. Una relazione è analoga a un eventuale percorso di join esistente tra colonne di chiave primaria e di chiave esterna di un database relazionale. Oggetto **DataRelation** identifica le colonne corrispondenti delle due tabelle di un **DataSet**.  
  
 Le relazioni consentono la navigazione da una tabella a altra in un **set di dati**. Gli elementi fondamentali di una **DataRelation** sono il nome della relazione, il nome di tabelle correlate e le colonne correlate in ogni tabella. È possibile compilare relazioni con più colonne per tabella specificando una matrice di oggetti <xref:System.Data.DataColumn> come colonne chiave. Quando si aggiunge una relazione con il <xref:System.Data.DataRelationCollection>, è possibile aggiungere facoltativamente un **UniqueKeyConstraint** e un **ForeignKeyConstraint** per imporre vincoli di integrità quando vengono apportate modifiche alla colonna correlata valori.  
  
 Per altre informazioni, vedere [aggiunta di oggetti DataRelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 È possibile compilare un **set di dati** da un flusso o documento XML. È possibile usare il flusso o documento XML per fornire al **set di dati** o dati, le informazioni sullo schema oppure entrambi. Le informazioni fornite dal documento o flusso XML possono essere combinate con i dati o informazioni sullo schema già presenti nel **set di dati**. Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 Il **set di dati**, **DataTable**, e **DataColumn** dotati di un **ExtendedProperties** proprietà. **Proprietà estese** è un **PropertyCollection** in cui è possibile inserire informazioni personalizzate, ad esempio l'istruzione SELECT che è stato usato per generare il set di risultati o il tempo quando i dati sono stati generati. Il **ExtendedProperties** raccolta viene mantenuta con le informazioni sullo schema per il **DataSet**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] fornisce funzionalità di esecuzione delle query integrate nel linguaggio per dati disconnessi archiviati in un oggetto DataSet. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Usa standard [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] sintassi e offre controllo della sintassi in fase di compilazione, la tipizzazione statica e il supporto IntelliSense quando si usa l'IDE di Visual Studio.  
  
 Per altre informazioni, vedere [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Oggetti DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
