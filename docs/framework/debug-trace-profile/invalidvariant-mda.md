---
title: MDA invalidVariant
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid variant
- VARIANT type errors
- InvalidVariant MDA
- invalid VARIANT types
- managed debugging assistants (MDAs), invalid variant
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d29d3f3638b3dae4381524fcaf55e1afeddc9f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730802"
---
# <a name="invalidvariant-mda"></a><span data-ttu-id="5c059-102">MDA invalidVariant</span><span class="sxs-lookup"><span data-stu-id="5c059-102">invalidVariant MDA</span></span>
<span data-ttu-id="5c059-103">L'assistente al debug gestito `invalidVariant` viene attivato quando viene rilevata una struttura `VARIANT` non valida durante una chiamata dal codice nativo o non gestito al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5c059-103">The `invalidVariant` managed debugging assistant (MDA) is activated when an invalid `VARIANT` structure is encountered during a call from native or unmanaged code to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5c059-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="5c059-104">Symptoms</span></span>  
 <span data-ttu-id="5c059-105">Comportamento imprevisto durante una transizione tra il codice nativo e quello gestito in cui è previsto il marshalling di una struttura `VARIANT` a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="5c059-105">Unexpected behavior during a transition between native and managed code involving the marshaling of a `VARIANT` to an object.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5c059-106">Causa</span><span class="sxs-lookup"><span data-stu-id="5c059-106">Cause</span></span>  
 <span data-ttu-id="5c059-107">Il codice nativo passa al codice gestito una struttura `VARIANT` in un formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="5c059-107">Native code is passing a malformed `VARIANT` structure to managed code.</span></span>  <span data-ttu-id="5c059-108">Il runtime tenta il marshalling di questa struttura `VARIANT` a un oggetto e, se non ritiene valida la struttura `VARIANT`, attiva l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="5c059-108">The runtime attempts to marshal this `VARIANT` to an object and activates the MDA if the `VARIANT` is not valid.</span></span> <span data-ttu-id="5c059-109">Tra gli esempi di strutture `VARIANT` non valide sono incluse strutture `VARIANT` con `VARTYPE` VT_EMPTY &#124; VT_BYREF o strutture `VARIANT` con `VARTYPE` VT_VARIANT.</span><span class="sxs-lookup"><span data-stu-id="5c059-109">Examples of invalid `VARIANT`S include a `VARIANT` with `VARTYPE` VT_EMPTY &#124; VT_BYREF or a `VARIANT` with `VARTYPE` VT_VARIANT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5c059-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="5c059-110">Resolution</span></span>  
 <span data-ttu-id="5c059-111">Il codice nativo o non gestito che passa la struttura `VARIANT` deve verificare la correttezza del formato e dell'inizializzazione della struttura `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="5c059-111">The native or unmanaged code passing the `VARIANT` must ensure that the `VARIANT` is correctly formed and initialized.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5c059-112">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5c059-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="5c059-113">L'assistente al debug gestito non produce effetti sul comportamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="5c059-113">The MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5c059-114">Output</span><span class="sxs-lookup"><span data-stu-id="5c059-114">Output</span></span>  
 <span data-ttu-id="5c059-115">Un messaggio dell'assistente al debug gestito in cui è indicato che il runtime ha rilevato una struttura `VARIANT` non valida passata al codice gestito da un modulo non gestito.</span><span class="sxs-lookup"><span data-stu-id="5c059-115">An MDA message indicating that the runtime detected an invalid `VARIANT` passed to managed code by an unmanaged module.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="5c059-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="5c059-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c059-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c059-117">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="5c059-118">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="5c059-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="5c059-119">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="5c059-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
