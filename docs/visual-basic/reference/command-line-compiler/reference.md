---
title: -riferimenti (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: a205682bb15b5d25ba0a2df895533d3443a41409
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663474"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="bd2b7-102">-riferimenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd2b7-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="bd2b7-103">Indica al compilatore di rendere disponibili per il progetto in corso di compilazione informazioni sui tipi negli assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd2b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd2b7-104">Syntax</span></span>  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="bd2b7-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="bd2b7-105">Arguments</span></span>  
  
|<span data-ttu-id="bd2b7-106">Termine</span><span class="sxs-lookup"><span data-stu-id="bd2b7-106">Term</span></span>|<span data-ttu-id="bd2b7-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="bd2b7-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="bd2b7-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-108">Required.</span></span> <span data-ttu-id="bd2b7-109">Elenco di nomi di file di assembly delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="bd2b7-110">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd2b7-111">Note</span><span class="sxs-lookup"><span data-stu-id="bd2b7-111">Remarks</span></span>  
 <span data-ttu-id="bd2b7-112">I file importati devono contenere i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="bd2b7-113">Solo i tipi pubblici sono visibili all'esterno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="bd2b7-114">Il [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opzione Importa i metadati da un modulo.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="bd2b7-115">Se si fa riferimento a un assembly (Assembly A) che a sua volta fa riferimento a un altro assembly (Assembly B), è necessario fare riferimento all'Assembly B se:</span><span class="sxs-lookup"><span data-stu-id="bd2b7-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="bd2b7-116">Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="bd2b7-117">Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="bd2b7-118">Uso [- libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) per specificare la directory in cui si trovano uno o più riferimenti agli assembly.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-118">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="bd2b7-119">Per il compilatore di riconoscere un tipo in un assembly (non un modulo), è necessario imporre la risoluzione del tipo.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="bd2b7-120">Un esempio di come è possibile eseguire questa operazione consiste nel definire un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="bd2b7-121">Esistono altri modi risolvere i nomi dei tipi in un assembly per consentire al compilatore.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="bd2b7-122">Ad esempio, se si eredita da un tipo in un assembly, il nome del tipo quindi diventa noto al compilatore.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="bd2b7-123">Il file di risposta Vbc. rsp, che fa riferimento comunemente utilizzati [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assembly, viene usato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="bd2b7-124">Usare `-noconfig` se non si desidera al compilatore di utilizzare vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-124">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="bd2b7-125">La forma breve di `-reference` è `/r`.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-125">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd2b7-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd2b7-126">Example</span></span>  
 <span data-ttu-id="bd2b7-127">Il comando seguente consente di compilare file di origine `Input.vb` e fare riferimento agli assembly da `Metad1.dll` e `Metad2.dll` produrre `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-127">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd2b7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd2b7-128">See also</span></span>

- [<span data-ttu-id="bd2b7-129">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd2b7-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bd2b7-130">-noconfig</span><span class="sxs-lookup"><span data-stu-id="bd2b7-130">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="bd2b7-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd2b7-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="bd2b7-132">Public</span><span class="sxs-lookup"><span data-stu-id="bd2b7-132">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="bd2b7-133">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="bd2b7-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
