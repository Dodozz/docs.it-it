---
title: 'Procedura: Generare il modello a oggetti come file esterno'
ms.date: 03/30/2017
ms.assetid: 2496fa06-3df4-4ecb-86c4-70a49ea08565
ms.openlocfilehash: 2e439cd6628daa5b574be2049393dc2964896679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033748"
---
# <a name="how-to-generate-the-object-model-as-an-external-file"></a>Procedura: Generare il modello a oggetti come file esterno
In alternativa al mapping basato sugli attributi, è possibile generare il modello a oggetti come file XML esterno usando lo strumento da riga di comando SQLMetal. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md). Usando un file di mapping XML esterno, si evita confusione nel codice. È inoltre possibile modificare il comportamento modificando il file esterno senza ricompilare i file binari dell'applicazione. Per altre informazioni, vedere [Mapping esterno](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
> [!NOTE]
>  [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] non supporta la generazione di un file di mapping esterno.  
  
## <a name="example"></a>Esempio  
 Il comando seguente genera un file di mapping esterno dal database di esempio Northwind.  
  
```  
sqlmetal /server:myserver /database:northwind /map:externalfile.xml  
```  
  
## <a name="example"></a>Esempio  
 L'estratto seguente di un file di mapping esterno mostra il mapping per la tabella Customers del database di esempio Northwind. Questo estratto viene generato eseguendo SQLMetal con il **/Map** opzione.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Database xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Name="northwnd">  
  <Table Name="Customers">  
    <Type Name=".Customer">  
      <Column Name="CustomerID" Member="CustomerID" Storage="_CustomerID" DbType="NChar(5) NOT NULL" CanBeNull="False" IsPrimaryKey="True" />  
      <Column Name="CompanyName" Member="CompanyName" Storage="_CompanyName" DbType="NVarChar(40) NOT NULL" CanBeNull="False" />  
      <Column Name="ContactName" Member="ContactName" Storage="_ContactName" DbType="NVarChar(30)" />  
      <Column Name="ContactTitle" Member="ContactTitle" Storage="_ContactTitle" DbType="NVarChar(30)" />  
      <Column Name="Address" Member="Address" Storage="_Address" DbType="NVarChar(60)" />  
      <Column Name="City" Member="City" Storage="_City" DbType="NVarChar(15)" />  
      <Column Name="Region" Member="Region" Storage="_Region" DbType="NVarChar(15)" />  
      <Column Name="PostalCode" Member="PostalCode" Storage="_PostalCode" DbType="NVarChar(10)" />  
      <Column Name="Country" Member="Country" Storage="_Country" DbType="NVarChar(15)" />  
      <Column Name="Phone" Member="Phone" Storage="_Phone" DbType="NVarChar(24)" />  
      <Column Name="Fax" Member="Fax" Storage="_Fax" DbType="NVarChar(24)" />  
      <Association Name="FK_CustomerCustomerDemo_Customers" Member="CustomerCustomerDemos" Storage="_CustomerCustomerDemos" ThisKey="CustomerID" OtherTable="CustomerCustomerDemo" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
      <Association Name="FK_Orders_Customers" Member="Orders" Storage="_Orders" ThisKey="CustomerID" OtherTable="Orders" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
    </Type>  
  </Table>  
</Database>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Creazione del modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md) (Mapping esterno)
- [Procedura: Generare il modello a oggetti in Visual Basic o C#](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
