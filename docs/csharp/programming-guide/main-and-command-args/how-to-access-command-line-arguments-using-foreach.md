---
title: 'Procedura: Accedere agli argomenti della riga di comando utilizzando foreach - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
ms.openlocfilehash: 79c798bb6ec16fc639d37defc40da5af770e5bba
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242432"
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="332e7-102">Procedura: Accedere agli argomenti della riga di comando utilizzando foreach (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="332e7-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="332e7-103">Un altro approccio per eseguire l'iterazione della matrice consiste nell'usare l'istruzione [foreach](../../../csharp/language-reference/keywords/foreach-in.md), come illustrato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="332e7-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="332e7-104">L'istruzione `foreach` può essere usata per eseguire l'iterazione di una matrice, una classe di raccolte .NET Framework o qualsiasi classe o struct che implementa l'interfaccia <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="332e7-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="332e7-105">Quando si esegue un'applicazione in Visual Studio, è possibile specificare argomenti della riga di comando nella [Pagina Debug, Progettazione progetti](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="332e7-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="332e7-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="332e7-106">Example</span></span>  
 <span data-ttu-id="332e7-107">In questo esempio viene illustrato come stampare gli argomenti della riga di comando usando `foreach`.</span><span class="sxs-lookup"><span data-stu-id="332e7-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="332e7-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="332e7-108">See Also</span></span>

- <xref:System.Array>  
- <xref:System.Collections>  
- [<span data-ttu-id="332e7-109">Compilazione dalla riga di comando con csc.exe</span><span class="sxs-lookup"><span data-stu-id="332e7-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
- [<span data-ttu-id="332e7-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="332e7-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="332e7-111">foreach, in</span><span class="sxs-lookup"><span data-stu-id="332e7-111">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
- [<span data-ttu-id="332e7-112">Main() e argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="332e7-112">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [<span data-ttu-id="332e7-113">Procedura: Visualizzare gli argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="332e7-113">How to: Display Command Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
- [<span data-ttu-id="332e7-114">Valori restituiti da Main()</span><span class="sxs-lookup"><span data-stu-id="332e7-114">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
