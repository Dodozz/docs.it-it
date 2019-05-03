---
title: Clausola Distinct (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: fbca9fa8aa227d8d5b6488bef179f4bda08bb38c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945353"
---
# <a name="distinct-clause-visual-basic"></a>Clausola Distinct (Visual Basic)
Limita i valori della variabile di intervallo corrente per eliminare i valori duplicati nelle clausole di query successiva.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>Note  
 È possibile usare il `Distinct` clausola per restituire un elenco di elementi univoci. Il `Distinct` clausola fa sì che la query ignorare i risultati della query duplicate. Il `Distinct` clausola viene applicata ai valori duplicati per tutti i campi specificati dalla restituiti il `Select` clausola. Se nessun `Select` clausola viene specificata, il `Distinct` clausola viene applicata alla variabile di intervallo per la query identificata nel `From` clausola. Se la variabile di intervallo non è un tipo non modificabile, la query ignorerà un risultato della query solo se tutti i membri del tipo corrisponde a un risultato di query esistente.  
  
## <a name="example"></a>Esempio  
 L'espressione di query seguente viene aggiunto un elenco di clienti e un elenco di ordini dei clienti. Il `Distinct` clausola è inclusa per restituire un elenco di nomi di clienti univoci e ordinare le date.  
  
 [!code-vb[VbSimpleQuerySamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#20)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
