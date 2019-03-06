---
title: 'Procedura: Utilizzare gli attributi di separazione delle colonne di un oggetto FlowDocument'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 8693c8973442a5c6e65e64c5c66194c11bbff119
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363783"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="7e128-102">Procedura: Utilizzare gli attributi di separazione delle colonne di un oggetto FlowDocument</span><span class="sxs-lookup"><span data-stu-id="7e128-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="7e128-103">In questo esempio viene illustrato come utilizzare le funzionalità di separazione delle colonne di una <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="7e128-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e128-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e128-104">Example</span></span>  
 <span data-ttu-id="7e128-105">L'esempio seguente definisce una <xref:System.Windows.Documents.FlowDocument>e imposta la <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, e <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributi.</span><span class="sxs-lookup"><span data-stu-id="7e128-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="7e128-106">Il <xref:System.Windows.Documents.FlowDocument> contiene un paragrafo unico del contenuto di esempio.</span><span class="sxs-lookup"><span data-stu-id="7e128-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="7e128-107">Nella figura seguente vengono illustrati gli effetti del <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, e <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> gli attributi in un rendering <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="7e128-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="7e128-108">![Schermata: FlowDocument con colonne](./media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span><span class="sxs-lookup"><span data-stu-id="7e128-108">![Screenshot: FlowDocument Intra Column](./media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span></span>
