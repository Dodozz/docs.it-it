---
title: '&lt;eccezione&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: c2b6e13059e3b309e4734c56bf9fd5eb7b82daa7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540897"
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="a50a5-102">&lt;eccezione&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a50a5-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="a50a5-103">Specifica le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="a50a5-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a50a5-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a50a5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a50a5-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="a50a5-106">Riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="a50a5-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="a50a5-107">Il compilatore controlla che l'eccezione specificata esista e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="a50a5-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="a50a5-108">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="a50a5-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="a50a5-109">Descrizione.</span><span class="sxs-lookup"><span data-stu-id="a50a5-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a50a5-110">Note</span><span class="sxs-lookup"><span data-stu-id="a50a5-110">Remarks</span></span>  
 <span data-ttu-id="a50a5-111">Usare il `<exception>` tag per specificare le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="a50a5-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="a50a5-112">Questo tag viene applicato a una definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="a50a5-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="a50a5-113">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="a50a5-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a50a5-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="a50a5-114">Example</span></span>  
 <span data-ttu-id="a50a5-115">Questo esempio Usa la `<exception>` tag per descrivere un'eccezione che il `IntDivide` funzione può generare.</span><span class="sxs-lookup"><span data-stu-id="a50a5-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a50a5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a50a5-116">See also</span></span>
- [<span data-ttu-id="a50a5-117">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="a50a5-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
