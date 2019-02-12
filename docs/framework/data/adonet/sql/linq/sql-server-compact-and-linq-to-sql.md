---
title: SQL Server Compact e LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: d7c0b34c431947a3e9f3f6b87e5d66e800c58f44
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092930"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact e LINQ to SQL
SQL Server Compact è il database predefinito installato con Visual Studio. Per altre informazioni, vedere [usando SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).  
  
 Questo argomento vengono illustrate le differenze principali in utilizzo, configurazione, set di funzionalità e ambito di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supportano.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Caratteristiche di SQL Server Compact in relazione a LINQ to SQL  
 Per impostazione predefinita, SQL Server Compact è installato per tutte le edizioni di Visual Studio ed è pertanto disponibile nel computer di sviluppo per l'uso con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Distribuzione di un'applicazione che Usa SQL Server Compact e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è diverso da quello per un'applicazione di SQL Server. SQL Server Compact non fa parte di .NET Framework e pertanto deve essere fornito con l'applicazione o scaricato separatamente dal sito Microsoft.  
  
 Tenere presente le seguenti caratteristiche:  
  
-   SQL Server Compact viene fornito come una DLL che può essere usata direttamente sui file di database (con estensione sdf).  
  
-   SQL Server Compact viene eseguito nello stesso processo come l'applicazione client. L'efficienza della comunicazione con SQL Server Compact può quindi essere significativamente più elevata rispetto alla comunicazione con SQL Server. D'altra parte, SQL Server Compact richiede l'interoperabilità fra codice gestito e con i relativi costi associati.  
  
-   Le dimensioni della DLL SQL Server Compact sono piccola. Questa funzionalità riduce le dimensioni complessive dell'applicazione.  
  
-   Il runtime di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e lo strumento della riga di comando SQLMetal supportano SQL Server Compact.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] non supporta SQL Server Compact.  
  
## <a name="feature-set"></a>Set di funzionalità  
 Il set di funzionalità di SQL Server Compact è molto più semplice rispetto al set di funzionalità di SQL Server nei modi seguenti che possono influire sulla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applicazioni:  
  
-   SQL Server Compact non supporta stored procedure o visualizzazioni.  
  
-   SQL Server Compact supporta solo un subset di tipi di dati e funzioni SQL.  
  
-   SQL Server Compact supporta solo un subset di costrutti SQL.  
  
-   SQL Server Compact fornisce solo un'utilità di ottimizzazione con funzionalità minime. È possibile che alcune query potrebbero raggiungere il timeout.  
  
-   SQL Server Compact non supporta il trust parziale.  
  
## <a name="see-also"></a>Vedere anche
- [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
