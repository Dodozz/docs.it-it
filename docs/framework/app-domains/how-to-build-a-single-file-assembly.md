---
title: 'Procedura: compilare un assembly con un singolo file'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fff84266dd99b84cc99c1996a3063dc962fa2e94
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841138"
---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="8cf25-102">Procedura: compilare un assembly con un singolo file</span><span class="sxs-lookup"><span data-stu-id="8cf25-102">How to: Build a Single-File Assembly</span></span>

<span data-ttu-id="8cf25-103">Un assembly con un singolo file, che rappresenta il tipo di assembly più semplice, contiene le informazioni e l'implementazione relative al tipo, oltre al [manifesto dell'assembly](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="8cf25-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="8cf25-104">Per creare un assembly con un singolo file, è possibile usare i compilatori della riga di comando o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8cf25-104">You can use command-line compilers or Visual Studio to create a single-file assembly.</span></span> <span data-ttu-id="8cf25-105">Per impostazione predefinita, il file di assembly creato dal compilatore ha l'estensione exe.</span><span class="sxs-lookup"><span data-stu-id="8cf25-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>

> [!NOTE]
> <span data-ttu-id="8cf25-106">È possibile usare Visual Studio per C# e Visual Basic solo per creare assembly con un singolo file.</span><span class="sxs-lookup"><span data-stu-id="8cf25-106">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="8cf25-107">Per creare assembly con più file, è necessario usare i compilatori della riga di comando o Visual C++.</span><span class="sxs-lookup"><span data-stu-id="8cf25-107">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="8cf25-108">Le procedure seguenti illustrano come creare assembly con un singolo file usando i compilatori della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8cf25-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="8cf25-109">Per creare un assembly con estensione exe</span><span class="sxs-lookup"><span data-stu-id="8cf25-109">To create an assembly with an .exe extension</span></span>

1.  <span data-ttu-id="8cf25-110">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="8cf25-110">At the command prompt, type the following command:</span></span>

     <span data-ttu-id="8cf25-111">\<*comando compilatore*> \<*nome modulo*></span><span class="sxs-lookup"><span data-stu-id="8cf25-111">\<*compiler command*> \<*module name*></span></span>

     <span data-ttu-id="8cf25-112">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8cf25-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

 <span data-ttu-id="8cf25-113">L'esempio seguente crea un assembly denominato `myCode.exe` da un modulo di codice denominato `myCode`.</span><span class="sxs-lookup"><span data-stu-id="8cf25-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>

```console
csc myCode.cs
```

```console
vbc myCode.vb
```

### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="8cf25-114">Per creare un assembly con estensione exe e specificare il nome del file di output</span><span class="sxs-lookup"><span data-stu-id="8cf25-114">To create an assembly with an .exe extension and specify the output file name</span></span>

1.  <span data-ttu-id="8cf25-115">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="8cf25-115">At the command prompt, type the following command:</span></span>

     <span data-ttu-id="8cf25-116">\<*comando compilatore*> **/out:**\<*nome file*> \<*nome modulo*></span><span class="sxs-lookup"><span data-stu-id="8cf25-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

     <span data-ttu-id="8cf25-117">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice, *nome file* è il nome del file di output e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8cf25-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

 <span data-ttu-id="8cf25-118">L'esempio seguente crea un assembly denominato `myAssembly.exe` da un modulo di codice denominato `myCode`.</span><span class="sxs-lookup"><span data-stu-id="8cf25-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>

```console
csc -out:myAssembly.exe myCode.cs
```

```console
vbc -out:myAssembly.exe myCode.vb
```

## <a name="creating-library-assemblies"></a><span data-ttu-id="8cf25-119">Creazione di assembly di librerie</span><span class="sxs-lookup"><span data-stu-id="8cf25-119">Creating Library Assemblies</span></span>
 <span data-ttu-id="8cf25-120">Un assembly di librerie è simile a una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="8cf25-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="8cf25-121">L'assembly contiene tipi a cui altri assembly faranno riferimento, ma non ha alcun punto di ingresso per avviare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8cf25-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

### <a name="to-create-a-library-assembly"></a><span data-ttu-id="8cf25-122">Per creare un assembly di librerie</span><span class="sxs-lookup"><span data-stu-id="8cf25-122">To create a library assembly</span></span>

1.  <span data-ttu-id="8cf25-123">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="8cf25-123">At the command prompt, type the following command:</span></span>

     <span data-ttu-id="8cf25-124">\<*comando compilatore*> **-t:library** \<*nome modulo*></span><span class="sxs-lookup"><span data-stu-id="8cf25-124">\<*compiler command*> **-t:library** \<*module name*></span></span>

     <span data-ttu-id="8cf25-125">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8cf25-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="8cf25-126">È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **-out:**.</span><span class="sxs-lookup"><span data-stu-id="8cf25-126">You can also use other compiler options, such as the **-out:** option.</span></span>

 <span data-ttu-id="8cf25-127">L'esempio seguente crea un assembly di librerie denominato `myCodeAssembly.dll` da un modulo di codice denominato `myCode`.</span><span class="sxs-lookup"><span data-stu-id="8cf25-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>

```console
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="8cf25-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cf25-128">See Also</span></span>

- [<span data-ttu-id="8cf25-129">Creazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="8cf25-129">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)
- [<span data-ttu-id="8cf25-130">Assembly con più file</span><span class="sxs-lookup"><span data-stu-id="8cf25-130">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="8cf25-131">Procedura: Compilare un assembly con più file</span><span class="sxs-lookup"><span data-stu-id="8cf25-131">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="8cf25-132">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="8cf25-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)