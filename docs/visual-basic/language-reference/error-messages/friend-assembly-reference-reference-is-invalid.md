---
title: Il riferimento all'assembly Friend <reference> non è valido
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0c1526e32ddc64cb4124c6f8205d58deef911dd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802474"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Riferimento all'assembly Friend \<riferimento > non è valido
Riferimento all'assembly Friend \<riferimento > non è valido. Gli assembly firmati con nome sicuro devono specificare una chiave pubblica nelle relative dichiarazioni InternalsVisibleTo.  
  
 Il nome dell'assembly passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo identifica un assembly con nome sicuro, ma non include un `PublicKey` attributo.  
  
 **ID errore:** BC31535  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Determinare la chiave pubblica dell'assembly friend sicuro. Includere la chiave pubblica come parte del nome dell'assembly passato al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> costruttore di attributo tramite la `PublicKey` attributo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.AssemblyName>
- [Assembly Friend](../../../standard/assembly/friend-assemblies.md)
