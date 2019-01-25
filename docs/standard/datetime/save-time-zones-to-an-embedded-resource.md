---
title: 'Procedura: Salvare fusi orari in una risorsa incorporata'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c67a97193d186275e6a788f6b18bbc17c535f367
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592874"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="8c657-102">Procedura: Salvare fusi orari in una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="8c657-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="8c657-103">Una fuso orario dell'applicazione spesso richiede la presenza di un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8c657-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="8c657-104">Tuttavia, poiché la disponibilità dei singoli <xref:System.TimeZoneInfo> oggetti dipende dalle informazioni archiviate nel Registro di sistema locale, anche fusi orari generalmente disponibili può essere assente.</span><span class="sxs-lookup"><span data-stu-id="8c657-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="8c657-105">Inoltre, viene creata un'istanza di informazioni sui fusi orari personalizzati usando il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo) non è archiviato con altre informazioni sul fuso orario nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="8c657-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="8c657-106">Per garantire che i fusi orari disponibili quando sono necessari, è possibile salvarli serializzando li e ripristinarli in un secondo momento per la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="8c657-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="8c657-107">In genere, la serializzazione un <xref:System.TimeZoneInfo> oggetto presente a parte l'applicazione abilitata per il fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8c657-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="8c657-108">A seconda l'archivio dati usato per contenere serializzato <xref:System.TimeZoneInfo> oggetti, dati del fuso orario possono essere serializzati come parte di una routine di installazione o configurazione (ad esempio, quando i dati vengono archiviati in una chiave applicazione del Registro di sistema) o come parte di una routine di utilità che esegue prima che venga compilata l'applicazione finale (ad esempio, quando i dati serializzati vengono archiviati in un file di risorse (resx) XML di .NET).</span><span class="sxs-lookup"><span data-stu-id="8c657-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="8c657-109">Oltre a un file di risorse che viene compilato con l'applicazione, diversi altri archivi dati è utilizzabile per informazioni sul fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8c657-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="8c657-110">tra cui:</span><span class="sxs-lookup"><span data-stu-id="8c657-110">These include the following:</span></span>

* <span data-ttu-id="8c657-111">Il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="8c657-111">The registry.</span></span> <span data-ttu-id="8c657-112">Si noti che un'applicazione deve utilizzare le sottochiavi della chiave dell'applicazione per archiviare i dati di fuso orario personalizzato anziché utilizzare le sottochiavi della HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span><span class="sxs-lookup"><span data-stu-id="8c657-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

* <span data-ttu-id="8c657-113">File di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8c657-113">Configuration files.</span></span>

* <span data-ttu-id="8c657-114">Altri file di sistema.</span><span class="sxs-lookup"><span data-stu-id="8c657-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="8c657-115">Per salvare un fuso orario per serializzarlo in un file resx</span><span class="sxs-lookup"><span data-stu-id="8c657-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="8c657-116">Recuperare un fuso orario esistente o creare un nuovo fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8c657-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="8c657-117">Per recuperare un fuso orario esistente, vedere [come: Accedere ora UTC e l'ora locale zona agli oggetti predefiniti](../../../docs/standard/datetime/access-utc-and-local.md) e [come: Creare un'istanza di un oggetto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="8c657-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="8c657-118">Per creare un nuovo fuso orario, chiamare uno degli overload del <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="8c657-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="8c657-119">Per altre informazioni, vedere [Procedura: Creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) e [come: Creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="8c657-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="8c657-120">Chiamare il <xref:System.TimeZoneInfo.ToSerializedString%2A> metodo per creare una stringa che contiene i dati del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="8c657-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="8c657-121">Creare un'istanza di un <xref:System.IO.StreamWriter> oggetto fornendo il nome e, facoltativamente, il percorso del file con estensione resx di <xref:System.IO.StreamWriter> costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="8c657-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="8c657-122">Creare un'istanza di un <xref:System.Resources.ResXResourceWriter> passando il <xref:System.IO.StreamWriter> dell'oggetto per il <xref:System.Resources.ResXResourceWriter> costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="8c657-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="8c657-123">Passare il fuso orario stringa serializzata al <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="8c657-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="8c657-124">Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c657-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="8c657-125">Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c657-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="8c657-126">Chiudi il <xref:System.IO.StreamWriter> chiamando il <xref:System.IO.StreamWriter.Close%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="8c657-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="8c657-127">Aggiungere il file con estensione resx generati al progetto di Visual Studio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8c657-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="8c657-128">Usando il **proprietà** finestra in Visual Studio, assicurarsi che il file con estensione resx **azione di compilazione** viene impostata su **risorsa incorporata**.</span><span class="sxs-lookup"><span data-stu-id="8c657-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="8c657-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c657-129">Example</span></span>

<span data-ttu-id="8c657-130">L'esempio seguente serializza un <xref:System.TimeZoneInfo> oggetto che rappresenta l'ora solare fuso centrale e un <xref:System.TimeZoneInfo> oggetto che rappresenta il Palmer Station, Antartide a un file di risorse .NET XML denominato SerializedTimeZones.</span><span class="sxs-lookup"><span data-stu-id="8c657-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="8c657-131">Ora solare fuso centrale viene in genere definita nel Registro di sistema. Palmer Station, Antartide è un fuso orario personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8c657-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="8c657-132">In questo esempio serializza <xref:System.TimeZoneInfo> gli oggetti in modo che siano disponibili in un file di risorse in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8c657-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="8c657-133">Poiché il <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> metodo aggiunge informazioni di intestazione completa in un file di risorsa XML .NET, non può essere usato per aggiungere risorse a un file esistente.</span><span class="sxs-lookup"><span data-stu-id="8c657-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="8c657-134">Nell'esempio viene gestita tramite il controllo dei file SerializedTimeZones e, se presente, l'archiviazione di tutte le relative risorse diverso da due fusi orari serializzati generico <xref:System.Collections.Generic.Dictionary%602> oggetto.</span><span class="sxs-lookup"><span data-stu-id="8c657-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="8c657-135">Il file esistente viene eliminato e le risorse esistenti vengono aggiunti a un nuovo file SerializedTimeZones.</span><span class="sxs-lookup"><span data-stu-id="8c657-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="8c657-136">I dati serializzati fuso orario viene inoltre aggiunto a questo file.</span><span class="sxs-lookup"><span data-stu-id="8c657-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="8c657-137">La chiave (o **nome**) i campi delle risorse non devono contenere spazi incorporati.</span><span class="sxs-lookup"><span data-stu-id="8c657-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="8c657-138">Il <xref:System.String.Replace%28System.String%2CSystem.String%29> metodo viene chiamato per rimuovere tutti gli spazi incorporati negli identificatori del fuso orario, prima che vengano assegnati al file di risorse.</span><span class="sxs-lookup"><span data-stu-id="8c657-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="8c657-139">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8c657-139">Compiling the code</span></span>

<span data-ttu-id="8c657-140">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c657-140">This example requires:</span></span>

* <span data-ttu-id="8c657-141">Aggiungere un riferimento alla DLL e Forms al progetto.</span><span class="sxs-lookup"><span data-stu-id="8c657-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="8c657-142">Che siano importati spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c657-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="8c657-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c657-143">See also</span></span>

- [<span data-ttu-id="8c657-144">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="8c657-144">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="8c657-145">Panoramica sui fusi orari</span><span class="sxs-lookup"><span data-stu-id="8c657-145">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="8c657-146">Procedura: Ripristinare i fusi orari da una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="8c657-146">How to: Restore time zones from an embedded resource</span></span>](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
