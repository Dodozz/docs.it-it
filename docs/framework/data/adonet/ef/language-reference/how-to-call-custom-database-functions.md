---
title: 'Procedura: Chiamare funzioni di database personalizzate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: cc2e25183649f6a95e7862520ccc5719f201277a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774647"
---
# <a name="how-to-call-custom-database-functions"></a>Procedura: Chiamare funzioni di database personalizzate
In questo argomento viene descritto come chiamare funzioni personalizzate definite nel database dall'interno di query LINQ to Entities.  
  
 Le funzioni di database che sono chiamate dalle query LINQ to Entities vengono eseguite nel database. L'esecuzione di funzioni nel database può migliorare le prestazioni dell'applicazione.  
  
 La procedura descritta di seguito fornisce una struttura di alto livello per la chiamata di una funzione di database personalizzata. Nell'esempio che segue vengono forniti dettagli aggiuntivi sui passaggi della procedura.  
  
### <a name="to-call-custom-functions-that-are-defined-in-the-database"></a>Per chiamare funzioni personalizzate definite nel database  
  
1. Creare una funzione personalizzata nel database.  
  
     Per altre informazioni sulla creazione di funzioni personalizzate in SQL Server, vedere [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).  
  
2. Dichiarare una funzione nel linguaggio Store Schema Definition Language (SSDL) del file .edmx. Il nome della funzione deve essere identico a quello della funzione dichiarata nel database.  
  
     Per altre informazioni, vedere [Function. Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).  
  
3. Aggiungere un metodo corrispondente a una classe nel codice dell'applicazione e applicare un <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al metodo. Si noti che i parametri <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> e <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> dell'attributo sono rispettivamente il nome dello spazio dei nomi del modello concettuale e il nome della funzione nel modello concettuale. La risoluzione del nome della funzione per LINQ rileva la distinzione tra maiuscole e minuscole.  
  
4. Chiamare il metodo in una query LINQ to Entities.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene mostrato come chiamare una funzione di database personalizzata dall'interno una query LINQ to Entities. Nell'esempio viene usato il modello School. Per informazioni sul modello School, vedere [creazione del Database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) e [genera il File con estensione edmx School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).  
  
 Nel codice seguente viene aggiunta la funzione `AvgStudentGrade` al database di esempio School.  
  
> [!NOTE]
>  I passaggi per la chiamata di una funzione di database personalizzata sono gli stessi indipendentemente dal server database. Tuttavia, il codice seguente è specifico per la creazione di una funzione in un database SQL Server. Il codice per la creazione di una funzione personalizzata in altri server database potrebbe essere differente.  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## <a name="example"></a>Esempio  
 Dichiarare una funzione nel linguaggio Store Schema Definition Language (SSDL) del file .edmx. Nel codice seguente viene dichiarata la funzione `AvgStudentGrade` in SSDL:  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## <a name="example"></a>Esempio  
 A questo punto creare un metodo ed eseguirne il mapping alla funzione dichiarata in SSDL. Il metodo nella classe seguente viene mappato alla funzione definita in SSDL (sopra) tramite un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Quando il metodo viene chiamato, viene eseguita la funzione corrispondente nel database.  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## <a name="example"></a>Esempio  
 Chiamare infine il metodo in una query LINQ to Entities. Nel codice seguente vengono visualizzati i cognomi di studenti e le medie dei voti alla console:  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Query in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
