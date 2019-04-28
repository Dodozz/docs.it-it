---
title: -resource (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 46122eaa7ca54679c9a52b939f9100c9a0747e7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61639082"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="98d41-102">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98d41-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="98d41-103">Incorpora una risorsa gestita in un assembly.</span><span class="sxs-lookup"><span data-stu-id="98d41-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98d41-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98d41-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="98d41-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="98d41-105">Arguments</span></span>  
  
|<span data-ttu-id="98d41-106">Termine</span><span class="sxs-lookup"><span data-stu-id="98d41-106">Term</span></span>|<span data-ttu-id="98d41-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="98d41-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="98d41-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="98d41-108">Required.</span></span> <span data-ttu-id="98d41-109">Il nome del file di risorse da incorporare nel file di output.</span><span class="sxs-lookup"><span data-stu-id="98d41-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="98d41-110">Per impostazione predefinita, `filename` è pubblico nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="98d41-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="98d41-111">Racchiudere il nome file racchiuso tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="98d41-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="98d41-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="98d41-112">Optional.</span></span> <span data-ttu-id="98d41-113">Il nome logico della risorsa nome utilizzato per caricarlo.</span><span class="sxs-lookup"><span data-stu-id="98d41-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="98d41-114">L'impostazione predefinita corrisponde al nome del file.</span><span class="sxs-lookup"><span data-stu-id="98d41-114">The default is the name of the file.</span></span> <span data-ttu-id="98d41-115">Facoltativamente, è possibile specificare se la risorsa è pubblica o privata nel manifesto dell'assembly, come con il codice seguente: `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="98d41-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98d41-116">Note</span><span class="sxs-lookup"><span data-stu-id="98d41-116">Remarks</span></span>  
 <span data-ttu-id="98d41-117">Usare `-linkresource` per collegare una risorsa a un assembly senza inserire il file di risorse nel file di output.</span><span class="sxs-lookup"><span data-stu-id="98d41-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="98d41-118">Se `filename` è un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse creato, ad esempio, mediante il [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) oppure nell'ambiente di sviluppo, è possibile accedervi tramite i membri di <xref:System.Resources> dello spazio dei nomi (vedere <xref:System.Resources.ResourceManager> per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="98d41-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="98d41-119">Per accedere a tutte le altre risorse in fase di esecuzione, usare uno dei seguenti metodi: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="98d41-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="98d41-120">La forma breve di `-resource` è `-res`.</span><span class="sxs-lookup"><span data-stu-id="98d41-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="98d41-121">Per informazioni su come impostare `-resource` nell'IDE di Visual Studio, vedere [gestione delle applicazioni alle risorse (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="98d41-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98d41-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="98d41-122">Example</span></span>  
 <span data-ttu-id="98d41-123">Il codice seguente Compila `In.vb` e il file di risorse consente di collegare `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="98d41-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="98d41-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98d41-124">See also</span></span>

- [<span data-ttu-id="98d41-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="98d41-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="98d41-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="98d41-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="98d41-127">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98d41-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="98d41-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98d41-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="98d41-129">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="98d41-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
