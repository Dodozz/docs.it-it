---
title: -link (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
ms.openlocfilehash: b13d8266d0702d831a0f5ebb3a9586864fe22ccb
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586525"
---
# <a name="-link-visual-basic"></a><span data-ttu-id="04062-102">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04062-102">-link (Visual Basic)</span></span>
<span data-ttu-id="04062-103">Indica al compilatore di rendere disponibili al progetto in fase di compilazione le informazioni sui tipi COM presenti negli assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="04062-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04062-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04062-104">Syntax</span></span>  
  
```  
-link:fileList  
' -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="04062-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="04062-105">Arguments</span></span>  
  
|<span data-ttu-id="04062-106">Termine</span><span class="sxs-lookup"><span data-stu-id="04062-106">Term</span></span>|<span data-ttu-id="04062-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="04062-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="04062-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="04062-108">Required.</span></span> <span data-ttu-id="04062-109">Elenco di nomi di file di assembly delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="04062-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="04062-110">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="04062-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04062-111">Note</span><span class="sxs-lookup"><span data-stu-id="04062-111">Remarks</span></span>  
 <span data-ttu-id="04062-112">L'opzione `-link`consente di distribuire un'applicazione in cui sono incorporate informazioni sul tipo.</span><span class="sxs-lookup"><span data-stu-id="04062-112">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="04062-113">L'applicazione può quindi usare i tipi in un assembly di runtime che implementano le informazioni sul tipo incorporate senza dovere far riferimento all'assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="04062-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="04062-114">Se vengono pubblicate diverse versioni dell'assembly di runtime, l'applicazione che contiene le informazioni sul tipo incorporate può funzionare con le diverse versioni senza che sia necessaria la ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="04062-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="04062-115">Per un esempio, vedere [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="04062-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md).</span></span>  
  
 <span data-ttu-id="04062-116">L'opzione `-link` è particolarmente utile quando si usa l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="04062-116">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="04062-117">È possibile incorporare tipi COM in modo che per l'applicazione non sia più necessario un assembly di interoperabilità primario nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="04062-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="04062-118">L'opzione `-link` indica al compilatore di incorporare le informazioni sul tipo COM dall'assembly di interoperabilità a cui si fa riferimento nel codice compilato risultante.</span><span class="sxs-lookup"><span data-stu-id="04062-118">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="04062-119">Il tipo COM viene identificato dal valore CLSID (GUID).</span><span class="sxs-lookup"><span data-stu-id="04062-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="04062-120">Di conseguenza, l'applicazione può essere eseguita in un computer di destinazione in cui sono stati installati gli stessi tipi COM con gli stessi valori CLSID.</span><span class="sxs-lookup"><span data-stu-id="04062-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="04062-121">Le applicazioni che consentono di automatizzare Microsoft Office costituiscono un valido esempio.</span><span class="sxs-lookup"><span data-stu-id="04062-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="04062-122">Poiché applicazioni come Office mantengono in genere lo stesso valore CLSID in versioni diverse, l'applicazione può usare i tipi COM a cui si fa riferimento purché .NET Framework 4 o versioni successive sia installato nel computer di destinazione e l'applicazione usi metodi, proprietà o eventi inclusi nei tipi COM a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="04062-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="04062-123">L'opzione `-link` incorpora solo interfacce, strutture e delegati.</span><span class="sxs-lookup"><span data-stu-id="04062-123">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="04062-124">L'incorporamento di classi COM non è supportato.</span><span class="sxs-lookup"><span data-stu-id="04062-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04062-125">Quando si crea un'istanza di un tipo COM incorporato nel codice, è necessario creare l'istanza usando l'interfaccia appropriata.</span><span class="sxs-lookup"><span data-stu-id="04062-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="04062-126">Il tentativo di creare un'istanza di un tipo COM incorporato usando la coclasse genera un errore.</span><span class="sxs-lookup"><span data-stu-id="04062-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="04062-127">Per impostare l'opzione `-link` in Visual Studio, aggiungere un riferimento all'assembly e impostare la proprietà `Embed Interop Types` su **true**.</span><span class="sxs-lookup"><span data-stu-id="04062-127">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="04062-128">Il valore predefinito della proprietà `Embed Interop Types` è **false**.</span><span class="sxs-lookup"><span data-stu-id="04062-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="04062-129">Se si collega a un assembly COM (assembly A) che fa riferimento a un altro assembly COM (assembly B), è necessario eseguire il collegamento anche all'assembly B se si verifica una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04062-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
- <span data-ttu-id="04062-130">Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="04062-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="04062-131">Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="04062-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="04062-132">Uso [- libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) per specificare la directory in cui si trovano uno o più riferimenti agli assembly.</span><span class="sxs-lookup"><span data-stu-id="04062-132">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="04062-133">Come le [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) l'opzione del compilatore, il `-link` opzione del compilatore utilizza il file di risposta Vbc. rsp che fa riferimento a più frequente agli assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="04062-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `-link` compiler option uses the Vbc.rsp response file, which references frequently used .NET Framework assemblies.</span></span> <span data-ttu-id="04062-134">Usare la [- noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) l'opzione del compilatore se non si desidera al compilatore di utilizzare il file Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="04062-134">Use the [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="04062-135">La forma breve di `-link` è `-l`.</span><span class="sxs-lookup"><span data-stu-id="04062-135">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="04062-136">Generics e tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="04062-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="04062-137">Nelle sezioni seguenti vengono descritte le limitazioni all'uso di tipi generici in applicazioni che incorporano tipi di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="04062-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="04062-138">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="04062-138">Generic Interfaces</span></span>  
 <span data-ttu-id="04062-139">Le interfacce generiche incorporate da un assembly di interoperabilità non possono essere usate,</span><span class="sxs-lookup"><span data-stu-id="04062-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="04062-140">come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="04062-140">This is shown in the following example.</span></span>  
  
 [!code-vb[VbLinkCompiler#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#1)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="04062-141">Tipi con parametri generici</span><span class="sxs-lookup"><span data-stu-id="04062-141">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="04062-142">I tipi che hanno un parametro generico il cui tipo è incorporato da un assembly di interoperabilità non possono essere usati se tale tipo proviene da un assembly esterno.</span><span class="sxs-lookup"><span data-stu-id="04062-142">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="04062-143">Tale restrizione non si applica tuttavia alle interfacce.</span><span class="sxs-lookup"><span data-stu-id="04062-143">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="04062-144">Si consideri ad esempio l'interfaccia <xref:Microsoft.Office.Interop.Excel.Range> definita nell'assembly <xref:Microsoft.Office.Interop.Excel>.</span><span class="sxs-lookup"><span data-stu-id="04062-144">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="04062-145">Se una libreria incorpora tipi di interoperabilità dall'assembly <xref:Microsoft.Office.Interop.Excel> ed espone un metodo che restituisce un tipo generico che ha un parametro il cui tipo è l'interfaccia <xref:Microsoft.Office.Interop.Excel.Range>, il metodo deve restituire un'interfaccia generica, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="04062-145">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-vb[VbLinkCompiler#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#2)]  
[!code-vb[VbLinkCompiler#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#3)]  
[!code-vb[VbLinkCompiler#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#4)]  
  
 <span data-ttu-id="04062-146">Nell'esempio seguente, il codice client può chiamare il metodo che restituisce l'interfaccia generica <xref:System.Collections.IList> senza errori.</span><span class="sxs-lookup"><span data-stu-id="04062-146">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-vb[VbLinkCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="04062-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="04062-147">Example</span></span>  
 <span data-ttu-id="04062-148">Riga di comando seguente consente di compilare file di origine `OfficeApp.vb` e fare riferimento agli assembly da `COMData1.dll` e `COMData2.dll` produrre `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="04062-148">The following command line compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```console  
vbc -link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="04062-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04062-149">See also</span></span>

- [<span data-ttu-id="04062-150">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04062-150">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="04062-151">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti</span><span class="sxs-lookup"><span data-stu-id="04062-151">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="04062-152">-riferimenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04062-152">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="04062-153">-noconfig</span><span class="sxs-lookup"><span data-stu-id="04062-153">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="04062-154">-libpath</span><span class="sxs-lookup"><span data-stu-id="04062-154">-libpath</span></span>](../../../visual-basic/reference/command-line-compiler/libpath.md)
- [<span data-ttu-id="04062-155">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="04062-155">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="04062-156">Introduzione all'interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="04062-156">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
