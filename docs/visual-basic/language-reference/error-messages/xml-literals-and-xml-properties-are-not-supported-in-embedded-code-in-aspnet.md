---
title: I valori letterali XML e le proprietà XML all'interno del codice incorporato non sono supportati in ASP.NET.
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 79be695478983055ae1f016cf841d733d3f4c430
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813925"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a>I valori letterali XML e le proprietà XML all'interno del codice incorporato non sono supportati in ASP.NET.
Valori letterali XML e proprietà XML non sono supportate nel codice incorporato all'interno di ASP.NET. Per usare le funzionalità XML, spostare il codice nel code-behind.  
  
 Un valore letterale XML o una proprietà axis XML è definita all'interno di codice incorporato (`<%= =>`) in un file di ASP.NET.  
  
 **ID errore:** BC31200  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare il codice che include il valore letterale XML o una proprietà axis XML in un file code-behind ASP.NET.  
  
## <a name="see-also"></a>Vedere anche

- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
