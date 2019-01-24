---
title: 'Procedura: Eseguire direttamente comandi SQL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 0ca62c0affc282140eb36979baafb8e3f9c89c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737546"
---
# <a name="how-to-directly-execute-sql-commands"></a>Procedura: Eseguire direttamente comandi SQL
Presupponendo una connessione <xref:System.Data.Linq.DataContext>, è possibile usare <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> per eseguire comandi SQL che non restituiscono oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene imposto a SQL Server di aumentare il valore di UnitPrice di 1,00.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Eseguire direttamente query SQL](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)
- [Comunicazione con il database](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
