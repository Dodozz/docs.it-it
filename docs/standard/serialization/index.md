---
title: Serializzazione in .NET
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e05d358452a247b0d071f78d19c0bf721502899a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018034"
---
# <a name="serialization-in-net"></a><span data-ttu-id="47a0d-102">Serializzazione in .NET</span><span class="sxs-lookup"><span data-stu-id="47a0d-102">Serialization in .NET</span></span>
<span data-ttu-id="47a0d-103">La serializzazione è il processo di conversione dello stato di un oggetto in un form che può essere mantenuto o trasportato.</span><span class="sxs-lookup"><span data-stu-id="47a0d-103">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="47a0d-104">Il complemento della serializzazione è la deserializzazione, che converte un flusso in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="47a0d-104">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="47a0d-105">Insieme, questi processi consentono di archiviare e trasferire i dati in modo semplice.</span><span class="sxs-lookup"><span data-stu-id="47a0d-105">Together, these processes allow data to be easily stored and transferred.</span></span>  
  
<span data-ttu-id="47a0d-106">.NET offre due tecnologie di serializzazione:</span><span class="sxs-lookup"><span data-stu-id="47a0d-106">.NET features two serialization technologies:</span></span>  
  
- <span data-ttu-id="47a0d-107">La serializzazione binaria mantiene la fedeltà dei tipi, utile per il mantenimento dello stato di un oggetto tra chiamate diverse di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="47a0d-107">Binary serialization preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="47a0d-108">È possibile, ad esempio, condividere un oggetto tra diverse applicazioni serializzandolo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="47a0d-108">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="47a0d-109">La serializzazione di un oggetto può essere effettuata in un flusso, in un disco, in memoria, in rete e così via.</span><span class="sxs-lookup"><span data-stu-id="47a0d-109">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="47a0d-110">.NET Remoting utilizza la serializzazione per passare oggetti "per valore" da un computer o dominio dell'applicazione a un altro.</span><span class="sxs-lookup"><span data-stu-id="47a0d-110">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="47a0d-111">La serializzazione XML serializza solo i campi e le proprietà pubbliche e non mantiene la fedeltà dei tipi.</span><span class="sxs-lookup"><span data-stu-id="47a0d-111">XML serialization serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="47a0d-112">Ciò risulta utile se si vuole fornire o utilizzare dati senza limitare l'applicazione che utilizza i dati.</span><span class="sxs-lookup"><span data-stu-id="47a0d-112">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="47a0d-113">Poiché XML è uno standard aperto, questa rappresenta una scelta interessante ai fini della condivisione di dati attraverso il Web.</span><span class="sxs-lookup"><span data-stu-id="47a0d-113">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="47a0d-114">Analogamente, SOAP è uno standard aperto che rappresenta una scelta altrettanto interessante.</span><span class="sxs-lookup"><span data-stu-id="47a0d-114">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47a0d-115">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="47a0d-115">In This Section</span></span>  
[<span data-ttu-id="47a0d-116">Argomenti sulle procedure relative alla serializzazione</span><span class="sxs-lookup"><span data-stu-id="47a0d-116">Serialization How-to Topics</span></span>](../../../docs/standard/serialization/serialization-how-to-topics.md)  
<span data-ttu-id="47a0d-117">Vengono riportati collegamenti alle procedure contenute in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="47a0d-117">Lists links to How-to topics contained in this section.</span></span>
  
[<span data-ttu-id="47a0d-118">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="47a0d-118">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
<span data-ttu-id="47a0d-119">Descrive il meccanismo della serializzazione binaria incluso nel Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="47a0d-119">Describes the binary serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="47a0d-120">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="47a0d-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
<span data-ttu-id="47a0d-121">Descrive il meccanismo della serializzazione XML e SOAP incluso nel Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="47a0d-121">Describes the XML and SOAP serialization mechanism that is included with the common language runtime.</span></span>

[<span data-ttu-id="47a0d-122">Strumenti per la serializzazione</span><span class="sxs-lookup"><span data-stu-id="47a0d-122">Serialization Tools</span></span>](../../../docs/standard/serialization/serialization-tools.md)  
<span data-ttu-id="47a0d-123">Questi strumenti consentono di sviluppare codice di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="47a0d-123">These tools help develop serialization code.</span></span>

[<span data-ttu-id="47a0d-124">Esempi di serializzazione</span><span class="sxs-lookup"><span data-stu-id="47a0d-124">Serialization Samples</span></span>](../../../docs/standard/serialization/serialization-samples.md)  
<span data-ttu-id="47a0d-125">Negli esempi viene illustrato come eseguire la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="47a0d-125">The samples demonstrate how to do serialization.</span></span>

## <a name="reference"></a><span data-ttu-id="47a0d-126">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="47a0d-126">Reference</span></span>
<span data-ttu-id="47a0d-127"><xref:System.Runtime.Serialization> Contiene classi che possono essere usate per la serializzazione e la deserializzazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="47a0d-127"><xref:System.Runtime.Serialization> Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="47a0d-128">Contiene classi utilizzabili per la serializzazione di oggetti in documenti XML o in flussi.</span><span class="sxs-lookup"><span data-stu-id="47a0d-128">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>