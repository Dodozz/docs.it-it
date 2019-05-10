---
title: La proprietà predefinita '<propertyname1>' è in conflitto con la proprietà predefinita '<propertyname2> nella base '<classname>', quindi deve essere dichiarata 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: c964003217e7b96cf25288e2ae6ae6a2fb07a6c3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651384"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="a9021-102">Proprietà predefinita '\<nomeproprietà1 >' è in conflitto con la proprietà predefinita '\<nomeproprietà2 >' in '\<NomeClasse >' e pertanto deve essere dichiarato come 'Shadows'</span><span class="sxs-lookup"><span data-stu-id="a9021-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>
<span data-ttu-id="a9021-103">Una proprietà viene dichiarata con lo stesso nome di una proprietà definita nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="a9021-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="a9021-104">In questo caso, la proprietà di questa classe deve nascondere le proprietà della classe base.</span><span class="sxs-lookup"><span data-stu-id="a9021-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="a9021-105">Si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="a9021-105">This message is a warning.</span></span> <span data-ttu-id="a9021-106">Per impostazione predefinita viene usato`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="a9021-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="a9021-107">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a9021-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a9021-108">**ID errore:** BC40007</span><span class="sxs-lookup"><span data-stu-id="a9021-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a9021-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a9021-109">To correct this error</span></span>  
  
- <span data-ttu-id="a9021-110">Aggiungere il `Shadows` una parola chiave per la dichiarazione o modificare il nome della proprietà da dichiarare.</span><span class="sxs-lookup"><span data-stu-id="a9021-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9021-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9021-111">See also</span></span>

- [<span data-ttu-id="a9021-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="a9021-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="a9021-113">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9021-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
