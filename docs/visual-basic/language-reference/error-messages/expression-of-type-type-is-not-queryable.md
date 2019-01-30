---
title: L'espressione di tipo <type> non può essere sottoposta a query
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 06b2a7f5c6bd838d09fd39f31778462c364fb8bd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261256"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="7ae83-102">Espressione di tipo \<tipo > non è disponibile per query</span><span class="sxs-lookup"><span data-stu-id="7ae83-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="7ae83-103">Espressione di tipo \<tipo > non è disponibile per query.</span><span class="sxs-lookup"><span data-stu-id="7ae83-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="7ae83-104">Assicurarsi che sia presente un'importazione di riferimento e/o lo spazio dei nomi di assembly per il provider LINQ.</span><span class="sxs-lookup"><span data-stu-id="7ae83-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="7ae83-105">Tipi queryable sono definiti nel <xref:System.Linq>, <xref:System.Data.Linq>, e <xref:System.Xml.Linq> gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7ae83-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="7ae83-106">È necessario importare uno o più di questi spazi dei nomi per eseguire query LINQ.</span><span class="sxs-lookup"><span data-stu-id="7ae83-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="7ae83-107">Il <xref:System.Linq> spazio dei nomi consente agli oggetti di query, ad esempio le raccolte e matrici usando LINQ.</span><span class="sxs-lookup"><span data-stu-id="7ae83-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="7ae83-108">Il <xref:System.Data.Linq> dello spazio dei nomi consente di eseguire query sui set di dati ADO.NET e i database di SQL Server usando LINQ.</span><span class="sxs-lookup"><span data-stu-id="7ae83-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="7ae83-109">Il <xref:System.Xml.Linq> dello spazio dei nomi consente di eseguire query XML con LINQ e usare le funzionalità XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7ae83-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="7ae83-110">**ID errore:** BC36593</span><span class="sxs-lookup"><span data-stu-id="7ae83-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7ae83-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7ae83-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="7ae83-112">Aggiungere un `Import` istruzione per il <xref:System.Linq>, <xref:System.Data.Linq>, o <xref:System.Xml.Linq> dello spazio dei nomi al file di codice.</span><span class="sxs-lookup"><span data-stu-id="7ae83-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="7ae83-113">È anche possibile importare gli spazi dei nomi per il progetto utilizzando il **riferimenti** pagina della finestra di Progettazione progetti (**My Project**).</span><span class="sxs-lookup"><span data-stu-id="7ae83-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="7ae83-114">Verificare che il tipo identificato come origine della query è un tipo queryable.</span><span class="sxs-lookup"><span data-stu-id="7ae83-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="7ae83-115">Vale a dire, un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="7ae83-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae83-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ae83-116">See also</span></span>
- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="7ae83-117">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ae83-117">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="7ae83-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="7ae83-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="7ae83-119">XML</span><span class="sxs-lookup"><span data-stu-id="7ae83-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="7ae83-120">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="7ae83-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="7ae83-121">Istruzione Imports (tipo e spazio dei nomi .NET)</span><span class="sxs-lookup"><span data-stu-id="7ae83-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="7ae83-122">Pagina Riferimenti, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ae83-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
