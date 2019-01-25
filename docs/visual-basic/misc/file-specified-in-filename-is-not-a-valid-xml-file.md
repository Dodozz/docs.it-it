---
title: Il file specificato in FileName non è un file XML valido
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: ffa39653c20127bb6af5e85654fee940a191fe5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603524"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="86f9f-102">Il file specificato in FileName non è un file XML valido</span><span class="sxs-lookup"><span data-stu-id="86f9f-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="86f9f-103">Il nome file fornito non è un file XML valido.</span><span class="sxs-lookup"><span data-stu-id="86f9f-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="86f9f-104">Per specificare la struttura e il contenuto consentito di un documento XML, è possibile usare una definizione DTD (Document Type Definition), uno schema XDR (XML-Data Reduced) o uno schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="86f9f-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="86f9f-105">Gli schemi XSD rappresentano modo migliore per specificare le grammatiche XML in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86f9f-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>

> [!NOTE]
>  <span data-ttu-id="86f9f-106">Nelle precedenti versioni di Visual Studio, **Progettazione XML** è la finestra di progettazione per i dataset tipizzati e lo schema XML.</span><span class="sxs-lookup"><span data-stu-id="86f9f-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="86f9f-107">È ancora possibile usare **Progettazione XML** per creare e modificare i file di schema XML.</span><span class="sxs-lookup"><span data-stu-id="86f9f-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="86f9f-108">Tuttavia, in Visual Studio 2012, la finestra di progettazione per la creazione e modifica di dataset tipizzati è il **Progettazione Dataset**.</span><span class="sxs-lookup"><span data-stu-id="86f9f-108">However, in Visual Studio 2012, the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="86f9f-109">Per altre informazioni, vedere [creazione e modifica di dataset tipizzati](/visualstudio/data-tools/creating-and-editing-typed-datasets).</span><span class="sxs-lookup"><span data-stu-id="86f9f-109">For more information, see [Creating and Editing Typed Datasets](/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="86f9f-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="86f9f-110">To correct this error</span></span>

-   <span data-ttu-id="86f9f-111">Verificare che il nome file fornito sia corretto.</span><span class="sxs-lookup"><span data-stu-id="86f9f-111">Check that you are supplying the correct file name.</span></span>

-   <span data-ttu-id="86f9f-112">Accertarsi che il file specificato contenga XML valido, caricando il file XML che si vuole verificare in **Progettazione XML**.</span><span class="sxs-lookup"><span data-stu-id="86f9f-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="86f9f-113">Scegliere **Convalida dati XML** dal menu **XML**.</span><span class="sxs-lookup"><span data-stu-id="86f9f-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="86f9f-114">Gli errori sono visualizzati nell' **Elenco attività**.</span><span class="sxs-lookup"><span data-stu-id="86f9f-114">Errors are displayed in the **Task List**.</span></span>

-   <span data-ttu-id="86f9f-115">Se il file XML ha uno schema XML associato, verificare che gli elementi appaiano nella struttura definita e che il contenuto dei singoli elementi sia conforme ai tipi di dati dichiarati specificati nello schema.</span><span class="sxs-lookup"><span data-stu-id="86f9f-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>

## <a name="see-also"></a><span data-ttu-id="86f9f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86f9f-116">See also</span></span>

- <xref:System.Xml>
- [<span data-ttu-id="86f9f-117">Procedura: Analizzare i percorsi dei File</span><span class="sxs-lookup"><span data-stu-id="86f9f-117">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)