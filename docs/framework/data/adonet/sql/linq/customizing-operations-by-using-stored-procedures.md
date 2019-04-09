---
title: Personalizzazione di operazioni utilizzando stored procedure
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
ms.openlocfilehash: 93aa679e02482e5c237c233655ee19f3bae17fd3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155948"
---
# <a name="customizing-operations-by-using-stored-procedures"></a>Personalizzazione di operazioni utilizzando stored procedure
Le stored procedure costituiscono un approccio comune per eseguire l'override del comportamento predefinito. Negli esempi riportati in questo argomento viene illustrato come usare wrapper di metodi generati per le stored procedure e chiamare direttamente le stored procedure.  
  
 Se si usa Visual Studio, è possibile usare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] assegnare stored procedure per eseguire inserimenti, aggiornamenti ed eliminazioni.  
  
> [!NOTE]
>  Per rileggere i valori generati dal database, usare i parametri di output nelle stored procedure. Se non è possibile usare parametri di output, scrivere un'implementazione di metodo parziale anziché basarsi sugli override generati da [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. I membri con mapping ai valori generati dal database devono essere impostati su valori appropriati dopo il completamento delle operazioni `INSERT` o `UPDATE`. Per altre informazioni, vedere [responsabilità di sviluppatore nell'override del comportamento predefinito](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente si presupporre che la classe `Northwind` contenga due metodi per chiamare stored procedure usate per gli override in una classe derivata.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#1)]  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nella classe seguente vengono usati questi metodi per l'override.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#2)]  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 È possibile usare `NorthwindThroughSprocs` esattamente come si utilizzerebbe `Northwnd`.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Responsabilità dello sviluppatore nell'override del comportamento predefinito](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
