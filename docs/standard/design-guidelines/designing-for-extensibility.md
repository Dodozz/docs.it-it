---
title: Progettazione finalizzata all'estensibilità
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: KrzysztofCwalina
ms.openlocfilehash: 94900dee72230a1b9d099d78168acc508af62af7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127355"
---
# <a name="designing-for-extensibility"></a><span data-ttu-id="b51de-102">Progettazione finalizzata all'estensibilità</span><span class="sxs-lookup"><span data-stu-id="b51de-102">Designing for Extensibility</span></span>
<span data-ttu-id="b51de-103">Un aspetto importante della progettazione di un framework è assicurare che l'estendibilità del framework è stato considerato con attenzione.</span><span class="sxs-lookup"><span data-stu-id="b51de-103">One important aspect of designing a framework is making sure the extensibility of the framework has been carefully considered.</span></span> <span data-ttu-id="b51de-104">È necessario comprendere i costi e vantaggi associati vari meccanismi di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="b51de-104">This requires that you understand the costs and benefits associated with various extensibility mechanisms.</span></span> <span data-ttu-id="b51de-105">In questo capitolo contribuisce di stabilire quale dei meccanismi di estendibilità: creazione di una sottoclasse, eventi, i membri virtuali, callback e così via, possano soddisfare i requisiti del framework.</span><span class="sxs-lookup"><span data-stu-id="b51de-105">This chapter helps you decide which of the extensibility mechanisms—subclassing, events, virtual members, callbacks, and so on—can best meet the requirements of your framework.</span></span>  
  
 <span data-ttu-id="b51de-106">Esistono diversi modi per consentire di estendibilità nel Framework.</span><span class="sxs-lookup"><span data-stu-id="b51de-106">There are many ways to allow extensibility in frameworks.</span></span> <span data-ttu-id="b51de-107">Sono compresi tra meno potenti, ma meno onerosi e molto potenti ma dispendioso.</span><span class="sxs-lookup"><span data-stu-id="b51de-107">They range from less powerful but less costly to very powerful but expensive.</span></span> <span data-ttu-id="b51de-108">Per qualsiasi requisito di estendibilità specifico, è consigliabile scegliere il meccanismo di estendibilità meno costoso che soddisfi i requisiti.</span><span class="sxs-lookup"><span data-stu-id="b51de-108">For any given extensibility requirement, you should choose the least costly extensibility mechanism that meets the requirements.</span></span> <span data-ttu-id="b51de-109">Tenere presente che in genere è possibile aggiungere maggiore estendibilità in un secondo momento, ma è bene non creare immediatamente senza introdurre modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="b51de-109">Keep in mind that it’s usually possible to add more extensibility later, but you can never take it away without introducing breaking changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b51de-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="b51de-110">In This Section</span></span>  
 [<span data-ttu-id="b51de-111">Classi non sealed</span><span class="sxs-lookup"><span data-stu-id="b51de-111">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [<span data-ttu-id="b51de-112">Membri protetti</span><span class="sxs-lookup"><span data-stu-id="b51de-112">Protected Members</span></span>](../../../docs/standard/design-guidelines/protected-members.md)  
 [<span data-ttu-id="b51de-113">Eventi e callback</span><span class="sxs-lookup"><span data-stu-id="b51de-113">Events and Callbacks</span></span>](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [<span data-ttu-id="b51de-114">Membri virtuali</span><span class="sxs-lookup"><span data-stu-id="b51de-114">Virtual Members</span></span>](../../../docs/standard/design-guidelines/virtual-members.md)  
 [<span data-ttu-id="b51de-115">Astrazioni (interfacce e tipi astratti)</span><span class="sxs-lookup"><span data-stu-id="b51de-115">Abstractions (Abstract Types and Interfaces)</span></span>](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [<span data-ttu-id="b51de-116">Classi base per l'implementazione di astrazioni</span><span class="sxs-lookup"><span data-stu-id="b51de-116">Base Classes for Implementing Abstractions</span></span>](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [<span data-ttu-id="b51de-117">Sealing</span><span class="sxs-lookup"><span data-stu-id="b51de-117">Sealing</span></span>](../../../docs/standard/design-guidelines/sealing.md)  
 <span data-ttu-id="b51de-118">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="b51de-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b51de-119">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="b51de-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51de-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b51de-120">See also</span></span>

- [<span data-ttu-id="b51de-121">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="b51de-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
