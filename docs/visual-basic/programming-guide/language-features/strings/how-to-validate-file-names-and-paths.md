---
title: 'Procedura: Convalidare i nomi di File e percorsi in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c0d39ecbaf9ca23c72e45b8839d268fbc38fe48e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648450"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="1fb8b-102">Procedura: Convalidare i nomi di File e percorsi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1fb8b-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="1fb8b-103">Questo esempio viene restituito un `Boolean` valore che indica se una stringa rappresenta un nome file o percorso.</span><span class="sxs-lookup"><span data-stu-id="1fb8b-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="1fb8b-104">I controlli di convalida se il nome contiene caratteri non consentiti dal file system.</span><span class="sxs-lookup"><span data-stu-id="1fb8b-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fb8b-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1fb8b-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 <span data-ttu-id="1fb8b-106">In questo esempio non verifica se il nome è posizionato in modo non corretto due punti o le directory con alcun nome, o se la lunghezza del nome supera la lunghezza massima definita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="1fb8b-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="1fb8b-107">Inoltre non controlla se l'applicazione è autorizzata ad accedere alla risorsa del file system con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="1fb8b-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb8b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fb8b-108">See also</span></span>
- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="1fb8b-109">Convalida delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1fb8b-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
