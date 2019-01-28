---
title: 'Procedura: Creare un nuovo metodo per una enumerazione - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 411606b6d86f8781be0cb2db19474d563c09a610
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725129"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="fe151-102">Procedura: Creare un nuovo metodo per una enumerazione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="fe151-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="fe151-103">È possibile usare metodi di estensione per aggiungere la funzionalità specifica di un particolare tipo enum.</span><span class="sxs-lookup"><span data-stu-id="fe151-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe151-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe151-104">Example</span></span>  
 <span data-ttu-id="fe151-105">Nell'esempio seguente, l'enumerazione `Grades` rappresenta il voto che uno studente potrebbe ricevere in un corso.</span><span class="sxs-lookup"><span data-stu-id="fe151-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="fe151-106">Il metodo di estensione denominato `Passing` viene aggiunto al tipo `Grades` in modo che ogni istanza di tale tipo ora "sa" se rappresenta un voto sufficiente oppure no.</span><span class="sxs-lookup"><span data-stu-id="fe151-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 <span data-ttu-id="fe151-107">Si noti che la classe `Extensions` contiene anche una variabile statica aggiornata in modo dinamico e che il valore restituito dal metodo di estensione riflette il valore corrente di tale variabile.</span><span class="sxs-lookup"><span data-stu-id="fe151-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="fe151-108">Ciò dimostra che dietro le quinte i metodi di estensione vengono chiamati direttamente per la classe statica nella quale sono definiti.</span><span class="sxs-lookup"><span data-stu-id="fe151-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fe151-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fe151-109">Compiling the Code</span></span>  
 <span data-ttu-id="fe151-110">Per eseguire questo codice, copiarlo e incollarlo in un progetto di applicazione console di Visual C# creato in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fe151-110">To run this code, copy and paste it into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="fe151-111">Per impostazione predefinita, questo progetto usa la versione 3.5 di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e contiene un riferimento a System.Core.dll e una direttiva `using` per System.Linq.</span><span class="sxs-lookup"><span data-stu-id="fe151-111">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="fe151-112">Se uno o più di questi requisiti non sono presenti nel progetto, è possibile aggiungerli manualmente.</span><span class="sxs-lookup"><span data-stu-id="fe151-112">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe151-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe151-113">See also</span></span>

- [<span data-ttu-id="fe151-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="fe151-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fe151-115">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="fe151-115">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
