---
title: -target:exe (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: 7d34a25fd614a209761714e1f4eff3042ca240c0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331312"
---
# <a name="-targetexe-c-compiler-options"></a><span data-ttu-id="42d6f-102">-target:exe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="42d6f-102">-target:exe (C# Compiler Options)</span></span>
<span data-ttu-id="42d6f-103">L'opzione **-target:exe** indica al compilatore di creare un file eseguibile (EXE), applicazione console.</span><span class="sxs-lookup"><span data-stu-id="42d6f-103">The **-target:exe** option causes the compiler to create an executable (EXE), console application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42d6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42d6f-104">Syntax</span></span>  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a><span data-ttu-id="42d6f-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="42d6f-105">Remarks</span></span>  
 <span data-ttu-id="42d6f-106">L'opzione **-target:exe** è attiva per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="42d6f-106">The **-target:exe** option is in effect by default.</span></span> <span data-ttu-id="42d6f-107">Il file eseguibile verrà creato con estensione .exe.</span><span class="sxs-lookup"><span data-stu-id="42d6f-107">The executable file will be created with the .exe extension.</span></span>  
  
 <span data-ttu-id="42d6f-108">Usare [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) per creare l'eseguibile di un programma Windows.</span><span class="sxs-lookup"><span data-stu-id="42d6f-108">Use [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) to create a Windows program executable.</span></span>  
  
 <span data-ttu-id="42d6f-109">Se non diversamente specificato con l'opzione [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del file di input contenente il metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="42d6f-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="42d6f-110">Se specificato dalla riga di comando, tutti i file fino alla successiva opzione **-out** o **-target:module** vengono usati per creare il file con estensione .exe</span><span class="sxs-lookup"><span data-stu-id="42d6f-110">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .exe file</span></span>  
  
 <span data-ttu-id="42d6f-111">Un solo metodo **Main** è necessario nei file del codice sorgente che vengono compilati in un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="42d6f-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="42d6f-112">L'opzione del compilatore [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) consente di specificare la classe che contiene il metodo **Main**, nei casi in cui il codice ha più di una classe con un metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="42d6f-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) compiler option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="42d6f-113">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="42d6f-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="42d6f-114">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="42d6f-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="42d6f-115">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="42d6f-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="42d6f-116">Modificare la proprietà **Tipo di output**.</span><span class="sxs-lookup"><span data-stu-id="42d6f-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="42d6f-117">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="42d6f-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42d6f-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="42d6f-118">Example</span></span>  
 <span data-ttu-id="42d6f-119">Ciascuna delle righe di comando seguenti compilerà `in.cs`, creando `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="42d6f-119">Each of the following command lines will compile `in.cs`, creating `in.exe`:</span></span>  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="42d6f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42d6f-120">See also</span></span>

- [<span data-ttu-id="42d6f-121">-target (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="42d6f-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="42d6f-122">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="42d6f-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
