---
title: 'Procedura: Elencare i formati di dati in un oggetto dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: 7d96cc7f7327ff7d33cf1147dbae75bc7620e310
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595890"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="d9140-102">Procedura: Elencare i formati di dati in un oggetto dati</span><span class="sxs-lookup"><span data-stu-id="d9140-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="d9140-103">Gli esempi seguenti illustrano come usare il <xref:System.Windows.DataObject.GetFormats%2A> overload del metodo get di una matrice di stringhe che indicano di ogni formato di dati che è disponibile in un oggetto dati.</span><span class="sxs-lookup"><span data-stu-id="d9140-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9140-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9140-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d9140-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9140-105">Description</span></span>  
 <span data-ttu-id="d9140-106">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetFormats%2A> overload per ottenere una matrice di stringhe che indicano tutti i formati di dati disponibili in un oggetto dati (nativo e conversione automatica).</span><span class="sxs-lookup"><span data-stu-id="d9140-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="d9140-107">Codice</span><span class="sxs-lookup"><span data-stu-id="d9140-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="d9140-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9140-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d9140-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9140-109">Description</span></span>  
 <span data-ttu-id="d9140-110">Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetFormats%2A> overload per ottenere una matrice di stringhe che indicano solo i formati di dati disponibili in un oggetto dati (auto-convertibili formati dati vengono filtrati).</span><span class="sxs-lookup"><span data-stu-id="d9140-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="d9140-111">Codice</span><span class="sxs-lookup"><span data-stu-id="d9140-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="d9140-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9140-112">See also</span></span>
- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="d9140-113">Cenni preliminari sul trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="d9140-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
