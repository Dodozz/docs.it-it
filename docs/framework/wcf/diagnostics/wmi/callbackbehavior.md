---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 38a38a71db2927d187ccdd93e5e364b0d4955373
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452612"
---
# <a name="callbackbehavior"></a><span data-ttu-id="535d6-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="535d6-102">CallbackBehavior</span></span>
<span data-ttu-id="535d6-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="535d6-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="535d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="535d6-104">Syntax</span></span>  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="535d6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="535d6-105">Methods</span></span>  
 <span data-ttu-id="535d6-106">La classe CallbackBehavior non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="535d6-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="535d6-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="535d6-107">Properties</span></span>  
 <span data-ttu-id="535d6-108">La classe CallbackBehavior dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="535d6-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="535d6-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="535d6-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="535d6-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="535d6-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="535d6-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="535d6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="535d6-112">Se True, la sessione viene chiusa automaticamente quando un servizio chiude una sessione duplex.</span><span class="sxs-lookup"><span data-stu-id="535d6-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="535d6-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="535d6-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="535d6-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="535d6-114">Data type: string</span></span>  
<span data-ttu-id="535d6-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="535d6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="535d6-116">Specifica se il servizio supporta un solo thread, più thread o chiamate rientranti.</span><span class="sxs-lookup"><span data-stu-id="535d6-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="535d6-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="535d6-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="535d6-118">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="535d6-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="535d6-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="535d6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="535d6-120">Valore che specifica se inviare dati di serializzazione sconosciuti in transito.</span><span class="sxs-lookup"><span data-stu-id="535d6-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="535d6-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="535d6-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="535d6-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="535d6-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="535d6-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="535d6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="535d6-124">Se attivato, i dettagli sulle eccezioni nel callback vengono collegati agli errori restituiti al servizio.</span><span class="sxs-lookup"><span data-stu-id="535d6-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="535d6-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="535d6-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="535d6-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="535d6-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="535d6-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="535d6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="535d6-128">Numero massimo di elementi consentiti in un oggetto serializzato.</span><span class="sxs-lookup"><span data-stu-id="535d6-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="535d6-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="535d6-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="535d6-130">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="535d6-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="535d6-131">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="535d6-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="535d6-132">Specifica se utilizzare il contesto di sincronizzazione corrente per scegliere il thread di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="535d6-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="535d6-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="535d6-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="535d6-134">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="535d6-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="535d6-135">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="535d6-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="535d6-136">Specifica se il sistema o l'applicazione impone l'elaborazione delle intestazioni MustUnderstand SOAP.</span><span class="sxs-lookup"><span data-stu-id="535d6-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="535d6-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="535d6-137">Requirements</span></span>  
  
|<span data-ttu-id="535d6-138">MOF</span><span class="sxs-lookup"><span data-stu-id="535d6-138">MOF</span></span>|<span data-ttu-id="535d6-139">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="535d6-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="535d6-140">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="535d6-140">Namespace</span></span>|<span data-ttu-id="535d6-141">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="535d6-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="535d6-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="535d6-142">See Also</span></span>  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
