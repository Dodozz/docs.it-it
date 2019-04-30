---
title: Esempio di tecnologia SchemaImporterExtension
ms.date: 03/30/2017
ms.assetid: 3f5eb78f-0ef6-433a-b095-3a63b1ce0bc9
ms.openlocfilehash: 5027897bcf62e52dae5aab6090c01518a92636dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028304"
---
# <a name="schemaimporterextension-technology-sample"></a><span data-ttu-id="96962-102">Esempio di tecnologia SchemaImporterExtension</span><span class="sxs-lookup"><span data-stu-id="96962-102">SchemaImporterExtension Technology Sample</span></span>
[<span data-ttu-id="96962-103">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="96962-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/SchemaImporterExtension.zip.exe)  
  
 <span data-ttu-id="96962-104">In questo esempio viene illustrato un oggetto <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> personalizzato che consente di eseguire un controllo accurato sulla generazione del codice durante l'importazione di uno schema XML.</span><span class="sxs-lookup"><span data-stu-id="96962-104">This sample demonstrates a custom <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> that allows fine control over code generation when an XML schema is imported.</span></span> <span data-ttu-id="96962-105">In particolare viene illustrato come compilare, registrare e richiamare tale estensione.</span><span class="sxs-lookup"><span data-stu-id="96962-105">The application shows how to build, register and invoke this extension.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="96962-106">Per compilare l'esempio utilizzando il prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="96962-106">To build the sample using the command prompt</span></span>  
  
1. <span data-ttu-id="96962-107">Aprire una finestra del prompt dei comandi, quindi spostarsi in una delle sottodirectory specifiche del linguaggio relative all'esempio.</span><span class="sxs-lookup"><span data-stu-id="96962-107">Open a Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="96962-108">Digitare **msbuild.exe OrderSchemaImporterExtension.sln** dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="96962-108">Type **msbuild.exe OrderSchemaImporterExtension.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="96962-109">Per compilare l'esempio utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96962-109">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="96962-110">Aprire [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], quindi spostarsi in una delle sottodirectory specifiche del linguaggio relative all'esempio.</span><span class="sxs-lookup"><span data-stu-id="96962-110">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="96962-111">Fare doppio clic sull'icona relativa a OrderSchemaImporterExtension.sln per aprire il file in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96962-111">Double-click the icon for OrderSchemaImporterExtension.sln to open the file in Visual Studio.</span></span>  
  
3. <span data-ttu-id="96962-112">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="96962-112">On the **Build** menu, click **Build Solution**.</span></span>  
  
 <span data-ttu-id="96962-113">L'applicazione verrà compilata nella directory predefinita \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="96962-113">The application will be built in the default \bin or \bin\Debug directory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="96962-114">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="96962-114">To run the sample</span></span>  
  
1. <span data-ttu-id="96962-115">Spostarsi nella directory contenente il nuovo eseguibile, utilizzando il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="96962-115">Navigate to the directory containing the new executable, using the command prompt.</span></span>  
  
2. <span data-ttu-id="96962-116">Digitare **[nome file eseguibile]** dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="96962-116">Type **[exe name]** at the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96962-117">Note</span><span class="sxs-lookup"><span data-stu-id="96962-117">Remarks</span></span>  
 <span data-ttu-id="96962-118">Per ulteriori informazioni sulle fasi di registrazione e di creazione di file binari di esempio, vedere i commenti nei file di codice sorgente e build.proj.</span><span class="sxs-lookup"><span data-stu-id="96962-118">For more information about sample binary creation and registration steps, see the comments in the source code and build.proj files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96962-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96962-119">See also</span></span>

- <xref:System.CodeDom.CodeCompileUnit>
- <xref:System.CodeDom.CodeNamespace>
- <xref:System.CodeDom.CodeNamespaceImport>
- <xref:Microsoft.CSharp.CSharpCodeProvider>
- <xref:System.Xml.Serialization.IXmlSerializable>
- <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>
- <xref:System.CodeDom>
- <xref:System.CodeDom.Compiler>
- <xref:System.Web.Services.Description>
- <xref:System.Web.Services.Discovery>
- <xref:System.Xml.Serialization>
- <xref:System.Uri>
- <xref:Microsoft.VisualBasic.VBCodeProvider>
- <xref:System.Web.Services.Description.WebReference>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
