---
title: 'Procedura: Leggere e scrivere in un file di dati appena creato'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f51042564158cfd7924164ce2b1a0fcc9d2658d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562830"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="251f6-102">Procedura: Leggere e scrivere in un file di dati appena creato</span><span class="sxs-lookup"><span data-stu-id="251f6-102">How to: Read and Write to a Newly Created Data File</span></span>
<span data-ttu-id="251f6-103">Le classi <xref:System.IO.BinaryWriter> e <xref:System.IO.BinaryReader?displayProperty=nameWithType> vengono usate per scrivere e leggere i dati invece delle stringhe di caratteri.</span><span class="sxs-lookup"><span data-stu-id="251f6-103">The <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data rather than character strings.</span></span> <span data-ttu-id="251f6-104">L'esempio seguente illustra come scrivere e leggere i dati in un nuovo flusso di file vuoto denominato `Test.data`.</span><span class="sxs-lookup"><span data-stu-id="251f6-104">The following example demonstrates how to write data to, and read data from, a new, empty file stream called `Test.data`.</span></span> <span data-ttu-id="251f6-105">Dopo aver creato il file di dati nella directory corrente, vengono creati gli oggetti <xref:System.IO.BinaryWriter> e <xref:System.IO.BinaryReader> associati e l'oggetto <xref:System.IO.BinaryWriter> viene usato per scrivere i valori interi da 0 a 10 in `Test.data`, lasciando il puntatore del file alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="251f6-105">After creating the data file in the current directory, the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects are created, and the <xref:System.IO.BinaryWriter> object is used to write the integers 0 through 10 to `Test.data`, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="251f6-106">Dopo avere reimpostato il puntatore del file sull'origine, l'oggetto <xref:System.IO.BinaryReader> legge il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="251f6-106">After setting the file pointer back to the origin, the <xref:System.IO.BinaryReader> object reads out the specified content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="251f6-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="251f6-107">Example</span></span>  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a><span data-ttu-id="251f6-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="251f6-108">Robust Programming</span></span>  
 <span data-ttu-id="251f6-109">Se `Test.data` è già presente nella directory corrente, viene generata un'eccezione <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="251f6-109">If `Test.data` already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="251f6-110">Utilizzare l'opzione della modalità file <xref:System.IO.FileMode.Create?displayProperty=nameWithType> quando si inizializza il flusso di file per creare sempre un nuovo file senza generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="251f6-110">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> when you initialize the file stream to always create a new file without throwing an  exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="251f6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="251f6-111">See also</span></span>

- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryWriter>
- <xref:System.IO.FileStream>
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>
- <xref:System.IO.SeekOrigin>
- [<span data-ttu-id="251f6-112">Procedura: Enumerare directory e file</span><span class="sxs-lookup"><span data-stu-id="251f6-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [<span data-ttu-id="251f6-113">Procedura: Aprire e accodare un file di log</span><span class="sxs-lookup"><span data-stu-id="251f6-113">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [<span data-ttu-id="251f6-114">Procedura: Leggere testo da un file</span><span class="sxs-lookup"><span data-stu-id="251f6-114">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [<span data-ttu-id="251f6-115">Procedura: Scrivere un testo in un file</span><span class="sxs-lookup"><span data-stu-id="251f6-115">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [<span data-ttu-id="251f6-116">Procedura: Leggere caratteri da una stringa</span><span class="sxs-lookup"><span data-stu-id="251f6-116">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
- [<span data-ttu-id="251f6-117">Procedura: Scrivere caratteri in una stringa</span><span class="sxs-lookup"><span data-stu-id="251f6-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)
- [<span data-ttu-id="251f6-118">I/O di file e di flussi</span><span class="sxs-lookup"><span data-stu-id="251f6-118">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
