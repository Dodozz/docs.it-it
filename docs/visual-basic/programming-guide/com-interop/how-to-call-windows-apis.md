---
title: 'Procedura: Chiamare le API di Windows (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 3769da28e1c9a27c8363b0d6ec639cedaf0f03be
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624846"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="8f193-102">Procedura: Chiamare le API di Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f193-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="8f193-103">In questo esempio definisce e chiama il `MessageBox` funzione in User32. dll e quindi passa una stringa a esso.</span><span class="sxs-lookup"><span data-stu-id="8f193-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f193-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f193-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8f193-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8f193-105">Compiling the Code</span></span>  
 <span data-ttu-id="8f193-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f193-106">This example requires:</span></span>  
  
- <span data-ttu-id="8f193-107">Un riferimento allo spazio dei nomi <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="8f193-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8f193-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="8f193-108">Robust Programming</span></span>  
 <span data-ttu-id="8f193-109">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="8f193-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="8f193-110">Il metodo non è statico, è astratto o è stato definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8f193-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="8f193-111">Il tipo padre è un'interfaccia o la lunghezza di *name* oppure *dllName* è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="8f193-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="8f193-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="8f193-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="8f193-113">Il *name* oppure *dllName* è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8f193-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="8f193-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="8f193-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="8f193-115">Il tipo contenitore è stato creato in precedenza con `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="8f193-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="8f193-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="8f193-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f193-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f193-117">See also</span></span>

- [<span data-ttu-id="8f193-118">Informazioni dettagliate su platform invoke</span><span class="sxs-lookup"><span data-stu-id="8f193-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="8f193-119">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="8f193-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="8f193-120">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="8f193-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="8f193-121">[Definizione di un metodo tramite Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8f193-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="8f193-122">Procedura dettagliata: Chiamata delle API di Windows</span><span class="sxs-lookup"><span data-stu-id="8f193-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="8f193-123">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="8f193-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
