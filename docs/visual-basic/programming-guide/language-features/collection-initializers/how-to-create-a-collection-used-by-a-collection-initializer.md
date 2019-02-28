---
title: 'Procedura: Creare una raccolta usata da un inizializzatore di raccolta (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: d0007ebf5f18dee5bd8448a071fe1f0f984aff1a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967451"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="72e75-102">Procedura: Creare una raccolta usata da un inizializzatore di raccolta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72e75-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="72e75-103">Quando si usa un inizializzatore di insieme per creare una raccolta, il compilatore Visual Basic cerca un' `Add` metodo di raccolta per il quale i parametri per il `Add` metodo corrispondono ai tipi dei valori nell'inizializzatore di insieme.</span><span class="sxs-lookup"><span data-stu-id="72e75-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="72e75-104">Ciò `Add` metodo viene utilizzato per popolare la raccolta con i valori dall'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="72e75-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72e75-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="72e75-105">Example</span></span>  
 <span data-ttu-id="72e75-106">L'esempio seguente mostra un' `OrderCollection` raccolta che contiene un pubblico `Add` metodo che è possibile usare un inizializzatore di raccolta per aggiungere gli oggetti di tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="72e75-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="72e75-107">Il `Add` metodo consente di utilizzare la sintassi dell'inizializzatore di raccolta abbreviato.</span><span class="sxs-lookup"><span data-stu-id="72e75-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="72e75-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72e75-108">See also</span></span>
- [<span data-ttu-id="72e75-109">Inizializzatori di raccolta</span><span class="sxs-lookup"><span data-stu-id="72e75-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="72e75-110">Procedura: Creare un metodo di estensione usata da un inizializzatore di raccolta Add</span><span class="sxs-lookup"><span data-stu-id="72e75-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
