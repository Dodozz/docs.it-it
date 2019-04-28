---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 51cfe4a52af2fbcd51a4f9e2dc738e83fe0852c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793978"
---
# <a name="-keycontainer"></a><span data-ttu-id="33b3a-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="33b3a-102">-keycontainer</span></span>
<span data-ttu-id="33b3a-103">Specifica il nome di un contenitore di chiavi per una coppia di chiavi allo scopo di assegnare a un assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="33b3a-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33b3a-104">Syntax</span></span>  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="33b3a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="33b3a-105">Arguments</span></span>  
  
|<span data-ttu-id="33b3a-106">Termine</span><span class="sxs-lookup"><span data-stu-id="33b3a-106">Term</span></span>|<span data-ttu-id="33b3a-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="33b3a-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="33b3a-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="33b3a-108">Required.</span></span> <span data-ttu-id="33b3a-109">File contenitore che contiene la chiave.</span><span class="sxs-lookup"><span data-stu-id="33b3a-109">Container file that contains the key.</span></span> <span data-ttu-id="33b3a-110">Racchiudere il nome file racchiuso tra virgolette ("") se il nome contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="33b3a-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33b3a-111">Note</span><span class="sxs-lookup"><span data-stu-id="33b3a-111">Remarks</span></span>  
 <span data-ttu-id="33b3a-112">Il compilatore crea il componente condivisibile inserendo una chiave pubblica nel manifesto dell'assembly e firmando l'assembly finale con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="33b3a-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="33b3a-113">Per generare un file di chiave, digitare `sn -k file` nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="33b3a-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="33b3a-114">Il `-i` opzione installa la coppia di chiavi in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="33b3a-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="33b3a-115">Per altre informazioni, vedere [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="33b3a-115">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="33b3a-116">Se esegue la compilazione con `-target:module`, il nome del file di chiave verrà mantenuto nel modulo e incorporato nell'assembly che viene creato quando si compila un assembly con [- addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="33b3a-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="33b3a-117">Questa opzione può essere specificata anche come attributo personalizzato <xref:System.Reflection.AssemblyKeyNameAttribute> nel codice sorgente di qualsiasi modulo MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="33b3a-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="33b3a-118">È possibile passare al compilatore le informazioni di crittografia anche tramite [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="33b3a-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="33b3a-119">Usare [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) se si vuole un assembly con firma parziale.</span><span class="sxs-lookup"><span data-stu-id="33b3a-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="33b3a-120">Visualizzare [creazione e assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) per altre informazioni su come firmare un assembly.</span><span class="sxs-lookup"><span data-stu-id="33b3a-120">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33b3a-121">Il `-keycontainer` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="33b3a-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33b3a-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="33b3a-122">Example</span></span>  
 <span data-ttu-id="33b3a-123">Il codice seguente consente di compilare file sorgente `Input.vb` e specifica un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="33b3a-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="33b3a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33b3a-124">See also</span></span>

- [<span data-ttu-id="33b3a-125">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="33b3a-125">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="33b3a-126">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33b3a-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="33b3a-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="33b3a-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="33b3a-128">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="33b3a-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
