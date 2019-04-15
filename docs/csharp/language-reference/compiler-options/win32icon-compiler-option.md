---
title: -win32icon (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 7bc7da8121ec1190908d9b94fc7c987f9888c020
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317453"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="b2312-102">-win32icon (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="b2312-102">-win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="b2312-103">Con l'opzione **-win32icon** viene inserito un file con estensione ico nel file di output, che assume l'aspetto desiderato in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="b2312-103">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2312-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2312-104">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="b2312-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b2312-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="b2312-106">Il file con estensione ico da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="b2312-106">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2312-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b2312-107">Remarks</span></span>  
 <span data-ttu-id="b2312-108">Un file con estensione ico può essere creato mediante il [compilatore di risorse](/windows/desktop/menurc/resource-compiler).</span><span class="sxs-lookup"><span data-stu-id="b2312-108">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="b2312-109">Il Compilatore di risorse viene richiamato quando si compila un programma Visual C++. Dal file .rc viene creato un file .ico.</span><span class="sxs-lookup"><span data-stu-id="b2312-109">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="b2312-110">Vedere [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (per fare riferimento a un file di risorse di .NET Framework) o a [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (per associarlo).</span><span class="sxs-lookup"><span data-stu-id="b2312-110">See [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="b2312-111">Vedere [-win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) per importare un file con estensione res.</span><span class="sxs-lookup"><span data-stu-id="b2312-111">See [-win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="b2312-112">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b2312-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="b2312-113">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="b2312-113">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="b2312-114">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="b2312-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="b2312-115">Modificare la proprietà **Icona dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="b2312-115">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="b2312-116">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2312-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2312-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2312-117">Example</span></span>  
 <span data-ttu-id="b2312-118">Compilare `in.cs` e associare un file con estensione ico `rf.ico` per produrre `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="b2312-118">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2312-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2312-119">See also</span></span>

- [<span data-ttu-id="b2312-120">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="b2312-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="b2312-121">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="b2312-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
