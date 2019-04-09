---
title: Oggetti DbProviderFactory
ms.date: 03/30/2017
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
ms.openlocfilehash: 2376cf39228cb5e8208112333ba06bb80070de84
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208814"
---
# <a name="dbproviderfactories"></a>Oggetti DbProviderFactory
Lo spazio dei nomi <xref:System.Data.Common> fornisce classi per la creazione di istanze di <xref:System.Data.Common.DbProviderFactory> per l'uso di origini dati specifiche. Quando si crea un'istanza di <xref:System.Data.Common.DbProviderFactory> e si passano le informazioni sul provider di dati, `DbProviderFactory` è in grado di determinare l'oggetto connessione corretto, fortemente tipizzato, da restituire in base alle informazioni fornite.  
  
 A partire dalla versione 4 di .NET Framework, i provider di dati come <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient>, a differenza dei provider personalizzati, non vengono più elencati nel file machine.config.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Cenni preliminari sul modello di factory](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 Viene fornita una panoramica del modello di progettazione e dell'interfaccia di programmazione di factory.  
  
 [Recupero di un oggetto DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 Viene illustrato come elencare i provider di dati installati e creare un oggetto <xref:System.Data.Common.DbConnection> da `DbProviderFactory`.  
  
 [DbConnection, DbCommand e DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 Viene illustrato come creare oggetti <xref:System.Data.Common.DbCommand> e <xref:System.Data.Common.DbDataReader> nonché come gestire gli errori di dati tramite <xref:System.Data.Common.DbException>.  
  
 [Modifica di dati con un oggetto DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 Viene illustrato come usare <xref:System.Data.Common.DbCommandBuilder> con <xref:System.Data.Common.DbDataAdapter> per recuperare e modificare dati.  
  
## <a name="see-also"></a>Vedere anche

- [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
