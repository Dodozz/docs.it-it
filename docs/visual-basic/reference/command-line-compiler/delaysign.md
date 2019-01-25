---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 1a784dc57331ed4cbaeb8524dbb3b6ea9a06eca1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605591"
---
# <a name="-delaysign"></a><span data-ttu-id="3c858-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="3c858-102">-delaysign</span></span>
<span data-ttu-id="3c858-103">Specifica se l'assembly avrà firma completa o parziale.</span><span class="sxs-lookup"><span data-stu-id="3c858-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c858-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c858-104">Syntax</span></span>  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3c858-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3c858-105">Arguments</span></span>  
 <span data-ttu-id="3c858-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="3c858-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="3c858-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3c858-107">Optional.</span></span> <span data-ttu-id="3c858-108">Usare `-delaysign-` se si desidera che l'assembly abbia firma completa.</span><span class="sxs-lookup"><span data-stu-id="3c858-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="3c858-109">Usare `-delaysign+` se si desidera inserire la chiave pubblica nell'assembly e riserva lo spazio per l'hash con segno.</span><span class="sxs-lookup"><span data-stu-id="3c858-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="3c858-110">Il valore predefinito è `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="3c858-110">The default is `-delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c858-111">Note</span><span class="sxs-lookup"><span data-stu-id="3c858-111">Remarks</span></span>  
 <span data-ttu-id="3c858-112">Il `-delaysign` opzione non ha effetto solo se abbinata [- keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) oppure [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="3c858-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="3c858-113">Quando si richiede un assembly con firma completa, il compilatore genera un hash per il file contenente il manifesto (i metadati dell'assembly) e firma tale hash con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="3c858-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="3c858-114">La firma digitale risultante viene archiviata nel file contenente il manifesto.</span><span class="sxs-lookup"><span data-stu-id="3c858-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="3c858-115">Quando un assembly è impostata la firma ritardata, il compilatore non di calcolo e archiviare la firma, ma riserva lo spazio nel file in modo che la firma può essere aggiunto in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="3c858-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="3c858-116">Ad esempio, usando `-delaysign+`, uno sviluppatore di un'organizzazione può distribuire le versioni di test senza segno di un assembly che i tester possono registrarsi con la global assembly cache e usare.</span><span class="sxs-lookup"><span data-stu-id="3c858-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="3c858-117">Al termine di lavoro nell'assembly, la persona responsabile della chiave privata dell'organizzazione possa firmare completamente l'assembly.</span><span class="sxs-lookup"><span data-stu-id="3c858-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="3c858-118">In questo contesto protegge chiave privata dell'organizzazione dalla divulgazione, consentendo a tutti gli sviluppatori di utilizzare gli assembly.</span><span class="sxs-lookup"><span data-stu-id="3c858-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="3c858-119">Visualizzare [creazione e assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) per altre informazioni su come firmare un assembly.</span><span class="sxs-lookup"><span data-stu-id="3c858-119">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="3c858-120">Per impostare - delaysign nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3c858-120">To set -delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="3c858-121">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="3c858-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3c858-122">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="3c858-122">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="3c858-123">Fare clic sulla scheda **Firma**.</span><span class="sxs-lookup"><span data-stu-id="3c858-123">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="3c858-124">Impostare il valore di **solo firma ritardata** casella.</span><span class="sxs-lookup"><span data-stu-id="3c858-124">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c858-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c858-125">See also</span></span>
- [<span data-ttu-id="3c858-126">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c858-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3c858-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="3c858-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="3c858-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="3c858-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [<span data-ttu-id="3c858-129">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="3c858-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
