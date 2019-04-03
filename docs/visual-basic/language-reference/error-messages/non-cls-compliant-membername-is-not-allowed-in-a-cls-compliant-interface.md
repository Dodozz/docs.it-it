---
title: <membername> non conforme a CLS non consentito in un'interfaccia conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: dbffe2bd196e798b90104aebb74269387660c794
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840458"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="457d8-102">Non conforme a CLS \<membername > non è consentita in un'interfaccia conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="457d8-102">Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="457d8-103">Una proprietà, routine o evento in un'interfaccia è contrassegnata come `<CLSCompliant(True)>` quando l'interfaccia stessa viene contrassegnata come `<CLSCompliant(False)>` o non è contrassegnata.</span><span class="sxs-lookup"><span data-stu-id="457d8-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="457d8-104">Per un'interfaccia è conforme con la [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), tutti i relativi membri devono essere conformi.</span><span class="sxs-lookup"><span data-stu-id="457d8-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="457d8-105">Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità.</span><span class="sxs-lookup"><span data-stu-id="457d8-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="457d8-106">L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.</span><span class="sxs-lookup"><span data-stu-id="457d8-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="457d8-107">Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.</span><span class="sxs-lookup"><span data-stu-id="457d8-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="457d8-108">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="457d8-108">By default, this message is a warning.</span></span> <span data-ttu-id="457d8-109">Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="457d8-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="457d8-110">**ID errore:** BC40033</span><span class="sxs-lookup"><span data-stu-id="457d8-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="457d8-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="457d8-111">To correct this error</span></span>  
  
-   <span data-ttu-id="457d8-112">Se si Richiedi la conformità a CLS ed è possibile accedere al codice sorgente di interfaccia, contrassegnare l'interfaccia come `<CLSCompliant(True)>` se tutti i relativi membri sono conformi.</span><span class="sxs-lookup"><span data-stu-id="457d8-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="457d8-113">Se necessaria la conformità a CLS e non è possibile controllare il codice sorgente dell'interfaccia, o se non è idonea essere conforme, definire il membro all'interno di un'interfaccia diversa.</span><span class="sxs-lookup"><span data-stu-id="457d8-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="457d8-114">Se è necessario che il membro rimanga nell'interfaccia corrente, rimuovere il <xref:System.CLSCompliantAttribute> dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="457d8-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457d8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="457d8-115">See also</span></span>

- [<span data-ttu-id="457d8-116">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="457d8-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
