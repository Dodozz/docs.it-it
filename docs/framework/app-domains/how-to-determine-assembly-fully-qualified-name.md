---
title: 'Procedura: Determinare il nome completo di un assembly'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32beb648bed37281e798f51e6b4a316197c23845
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283517"
---
# <a name="how-to-determine-an-assemblys-fully-qualified-name"></a><span data-ttu-id="9c8df-102">Procedura: Determinare il nome completo di un assembly</span><span class="sxs-lookup"><span data-stu-id="9c8df-102">How to: Determine an Assembly's Fully Qualified Name</span></span>
<span data-ttu-id="9c8df-103">Per individuare il nome completo di un assembly nella Global Assembly Cache, usare lo strumento Global Assembly Cache ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="9c8df-103">To discover the fully qualified name of an assembly in the global assembly cache, use the Global Assembly Cache Tool ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md)).</span></span> <span data-ttu-id="9c8df-104">Vedere [Procedura: Visualizzare il contenuto della Global Assembly Cache](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="9c8df-104">See [How to: View the Contents of the Global Assembly Cache](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span></span>  
  
 <span data-ttu-id="9c8df-105">Per gli assembly che non si trovano nella Global Assembly Cache è possibile ottenere il nome completo dell'assembly in diversi modi: è possibile usare il codice per restituire le informazioni alla console o a una variabile oppure [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per esaminare i metadati dell'assembly che contengono il nome completo.</span><span class="sxs-lookup"><span data-stu-id="9c8df-105">For assemblies that are not in the global assembly cache, you can get the fully qualified assembly name in a number of ways: can use code to output the information to the console or to a variable, or you can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
-   <span data-ttu-id="9c8df-106">Se l'assembly è già stato caricato dall'applicazione, è possibile recuperare il valore della proprietà <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> per ottenere il nome completo.</span><span class="sxs-lookup"><span data-stu-id="9c8df-106">If the assembly is already loaded by the application, you can retrieve the value of the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property to get the fully qualified name.</span></span> <span data-ttu-id="9c8df-107">È possibile usare questo approccio indipendentemente dalla presenza dell'assembly nella GAC.</span><span class="sxs-lookup"><span data-stu-id="9c8df-107">You can use this approach whether or not the assembly is in the GAC.</span></span> <span data-ttu-id="9c8df-108">Nell'esempio viene illustrata una situazione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="9c8df-108">The example provides an illustration.</span></span>  
  
-   <span data-ttu-id="9c8df-109">Se si conosce il percorso del file system dell'assembly, è possibile chiamare il metodo statico (`Shared` in Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> per ottenere il nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9c8df-109">If you know the assembly's file system path, you can call the static (`Shared` in Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method to get the fully qualified assembly name.</span></span> <span data-ttu-id="9c8df-110">Di seguito è riportato un semplice esempio.</span><span class="sxs-lookup"><span data-stu-id="9c8df-110">The following is a simple example.</span></span>  
  
     [!code-csharp[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/cs/getassemblyname1.cs#1)]
     [!code-vb[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/vb/getassemblyname1.vb#1)]  
  
-   <span data-ttu-id="9c8df-111">È possibile usare [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per esaminare i metadati dell'assembly che contengono il nome completo.</span><span class="sxs-lookup"><span data-stu-id="9c8df-111">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
 <span data-ttu-id="9c8df-112">Per altre informazioni sull'impostazione degli attributi dell'assembly, ad esempio versione, impostazioni cultura e nome dell'assembly, vedere [Impostazione degli attributi dell'assembly](../../../docs/framework/app-domains/set-assembly-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="9c8df-112">For more information about setting assembly attributes such as version, culture, and assembly name, see [Setting Assembly Attributes](../../../docs/framework/app-domains/set-assembly-attributes.md).</span></span> <span data-ttu-id="9c8df-113">Per altre informazioni sull'assegnazione di un nome sicuro all'assembly, vedere [Creazione e uso degli assembly con nome sicuro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="9c8df-113">For more information about giving an assembly a strong name, see [Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c8df-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9c8df-114">Example</span></span>  
 <span data-ttu-id="9c8df-115">Il codice seguente mostra come visualizzare il nome completo di un assembly contenente una classe specificata nella console.</span><span class="sxs-lookup"><span data-stu-id="9c8df-115">The following code example shows how to display the fully qualified name of an assembly containing a specified class to the console.</span></span> <span data-ttu-id="9c8df-116">Poiché contiene il nome di un assembly già caricato dall'app, non è importante che l'assembly sia contenuto nella GAC.</span><span class="sxs-lookup"><span data-stu-id="9c8df-116">Because it retrieves the name of an assembly that the app has already loaded, it does not matter whether the assembly is in the GAC.</span></span>  
  
 [!code-cpp[Assembly.Fullname#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.FullName/CPP/example2.cpp#2)]
 [!code-csharp[Assembly.Fullname#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.FullName/CS/example2.cs#2)]
 [!code-vb[Assembly.Fullname#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.FullName/VB/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9c8df-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c8df-117">See also</span></span>
- [<span data-ttu-id="9c8df-118">Nomi degli assembly</span><span class="sxs-lookup"><span data-stu-id="9c8df-118">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)
- [<span data-ttu-id="9c8df-119">Creazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="9c8df-119">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)
- [<span data-ttu-id="9c8df-120">Creazione e utilizzo degli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="9c8df-120">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="9c8df-121">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="9c8df-121">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)
- [<span data-ttu-id="9c8df-122">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="9c8df-122">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="9c8df-123">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="9c8df-123">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
