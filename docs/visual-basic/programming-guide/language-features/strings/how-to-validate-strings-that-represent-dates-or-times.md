---
title: 'Procedura: Convalidare le stringhe che rappresentano date o ore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: f24ff05e48327c21c02eb92b07db17266f743a80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024612"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="24eda-102">Procedura: Convalidare le stringhe che rappresentano date o ore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24eda-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="24eda-103">I seguente esempio di codice impostare un `Boolean` valore che indica se una stringa rappresenta una data valida o un'ora.</span><span class="sxs-lookup"><span data-stu-id="24eda-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24eda-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="24eda-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24eda-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="24eda-105">Compiling the Code</span></span>  
 <span data-ttu-id="24eda-106">Sostituire `("01/01/03")` e `"9:30 PM"` con la data e ora che si desidera convalidare.</span><span class="sxs-lookup"><span data-stu-id="24eda-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="24eda-107">È possibile sostituire la stringa con un'altra stringa hardcoded, con un `String` variabile, o con un metodo che restituisce una stringa, ad esempio `InputBox`.</span><span class="sxs-lookup"><span data-stu-id="24eda-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="24eda-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="24eda-108">Robust Programming</span></span>  
 <span data-ttu-id="24eda-109">Usare questo metodo per convalidare la stringa prima di tentare di convertire le `String` a un `DateTime` variabile.</span><span class="sxs-lookup"><span data-stu-id="24eda-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="24eda-110">Controllando la data o ora prima di tutto, è possibile evitare la generazione di un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="24eda-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24eda-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24eda-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="24eda-112">Convalida delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24eda-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
