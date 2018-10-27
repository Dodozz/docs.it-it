---
title: Derivazione della struttura relazionale di dataset da XML Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 76fd0126f32eb2b22a12ee0b67e1f81794ff9445
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195294"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="3d222-102">Derivazione della struttura relazionale di dataset da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="3d222-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="3d222-103">Questa sezione fornisce una panoramica della compilazione dello schema relazionale di un tipo `DataSet` da un documento basato sullo schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="3d222-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="3d222-104">In generale, per ognuno `complexType` nell'elemento figlio di un elemento dello schema, viene generata una tabella di `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="3d222-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="3d222-105">La struttura della tabella è determinata dalla definizione del tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="3d222-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="3d222-106">Le tabelle vengono create nel `DataSet` per gli elementi di primo livello nello schema.</span><span class="sxs-lookup"><span data-stu-id="3d222-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="3d222-107">Tuttavia, una tabella viene creata solo per un livello superiore `complexType` elemento quando il `complexType` è annidato all'interno di un altro elemento `complexType` elemento, nel quale caso annidata `complexType` elemento viene mappato a una `DataTable` all'interno del `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="3d222-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="3d222-108">Per altre informazioni su XSD, vedere il World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), il [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/)e il [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="3d222-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="3d222-109">Nell'esempio seguente viene illustrato un XML Schema in cui `customers` è l'elemento figlio del `MyDataSet` elemento, che è un **DataSet** elemento.</span><span class="sxs-lookup"><span data-stu-id="3d222-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="3d222-110">L'elemento `customers` nell'esempio precedente è un elemento di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="3d222-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="3d222-111">La definizione di tipo complesso viene quindi analizzata e la tabella seguente viene creata dal processo di mapping.</span><span class="sxs-lookup"><span data-stu-id="3d222-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="3d222-112">Il tipo di dati relativo a ogni colonna della tabella viene derivato dal tipo di XML Schema relativo al corrispondente elemento o attributo specificato.</span><span class="sxs-lookup"><span data-stu-id="3d222-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d222-113">Se l'elemento `customers` è un tipo di dati XML Schema semplice, ad esempio **integer**, verrà generata alcuna tabella.</span><span class="sxs-lookup"><span data-stu-id="3d222-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="3d222-114">Le tabelle vengono create solo per gli elementi di livello principale di tipo complesso.</span><span class="sxs-lookup"><span data-stu-id="3d222-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="3d222-115">Nello Schema XML seguente, il **Schema** elemento ha due figli, `InStateCustomers` e `OutOfStateCustomers`.</span><span class="sxs-lookup"><span data-stu-id="3d222-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="3d222-116">Entrambi gli elementi figlio `InStateCustomers` e `OutOfStateCustomers` sono elementi di tipo complesso (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="3d222-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="3d222-117">Pertanto, il processo di mapping che genera l'errore di due tabelle identiche seguenti nel `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="3d222-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="3d222-118">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="3d222-118">In This Section</span></span>  
 [<span data-ttu-id="3d222-119">Mapping tra vincoli XML Schema (XSD) e vincoli di DataSet</span><span class="sxs-lookup"><span data-stu-id="3d222-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="3d222-120">Vengono descritti gli elementi di XML Schema utilizzati per creare i vincoli di chiave univoci ed esterni in un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="3d222-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="3d222-121">Generazione di relazioni tra DataSet da XML Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="3d222-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="3d222-122">Vengono descritti gli elementi di XML Schema usati per creare relazioni tra le colonne della tabella in un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="3d222-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="3d222-123">Vincoli e relazioni di XML Schema</span><span class="sxs-lookup"><span data-stu-id="3d222-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="3d222-124">Viene descritto come le relazioni vengono create in modo implicito quando si usano elementi di XML Schema per creare vincoli in un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="3d222-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3d222-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="3d222-125">Related Sections</span></span>  
 [<span data-ttu-id="3d222-126">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="3d222-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="3d222-127">Viene descritto come caricare e mantenere la struttura relazionale e i dati in un `DataSet` come dati XML.</span><span class="sxs-lookup"><span data-stu-id="3d222-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d222-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d222-128">See Also</span></span>  
 [<span data-ttu-id="3d222-129">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="3d222-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
