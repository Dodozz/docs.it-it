---
title: 'Procedura: Controllare la quantità di dati correlati recuperata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
ms.openlocfilehash: dd59c09185eab003274614dcc30393b060e6b7c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904475"
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a>Procedura: Controllare la quantità di dati correlati recuperata
Usare il metodo <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per specificare quali dati correlati alla destinazione principale devono essere recuperati contemporaneamente. Ad esempio, se le informazioni necessarie sono relative agli ordini dei clienti, è possibile usare <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> per assicurarsi che le informazioni sugli ordini vengano recuperate contestualmente alle informazioni sui clienti. Questo approccio comporta un solo accesso al database per entrambi i set di informazioni.  
  
> [!NOTE]
>  È possibile recuperare dati riferiti alla destinazione principale della query recuperando un prodotto incrociato come una proiezione estesa, ad esempio gli ordini quando la destinazione della query sono i clienti. Questo approccio, tuttavia, presenta spesso svantaggi. Ad esempio, i risultati sono solo proiezioni e non entità che possono essere modificate ed essere salvate in modo permanente da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Inoltre è possibile che vengano recuperate grandi quantità di dati non necessari.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente tutti gli oggetti `Orders` di tutti gli oggetti `Customers` residenti nell'area londinese vengono recuperati quando viene eseguita la query. Di conseguenza, l'accesso successivo alla proprietà `Orders` su un oggetto `Customer` non avvia una nuova query di database.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Esecuzione di query sul database](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
