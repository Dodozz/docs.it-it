---
title: MDA gcManagedToUnmanaged
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bb4779e300df71a5d075a322bcac8398ce42f34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754440"
---
# <a name="gcmanagedtounmanaged-mda"></a>MDA gcManagedToUnmanaged
L'assistente al debug gestito `gcManagedToUnmanaged` determina un'operazione di Garbage Collection ogni volta che un thread passa dal codice gestito al codice non gestito.  
  
## <a name="symptoms"></a>Sintomi  
 Un componente utente non gestito genera una violazione di accesso quando si cerca di usare un oggetto gestito esposto a COM. L'oggetto COM appare come rilasciato e la violazione di accesso è non deterministica.  
  
## <a name="cause"></a>Causa  
 Se un componente non gestito non esegue correttamente il conteggio dei riferimenti a un oggetto COM gestito, il runtime potrebbe eseguire una Garbage Collection di un oggetto gestito esposto a COM mentre il componente gestito contiene ancora un riferimento all'oggetto. Il runtime chiama il metodo <xref:System.Runtime.InteropServices.Marshal.Release%2A> durante le Garbage Collection. In questo modo, se il componente utente usa l'oggetto prima che si verifichi la Garbage Collection, non sarà ancora stato sottoposto all'operazione. Da ciò deriva il non determinismo.  
  
## <a name="resolution"></a>Risoluzione  
 L'attivazione di questo assistente consente di ridurre il periodo compreso tra il momento in cui l'oggetto è disponibile per la Garbage Collection e la chiamata di <xref:System.Runtime.InteropServices.Marshal.Release%2A> rendendo possibile tenere traccia del componente non gestito che tenta per primo di accedere all'oggetto sottoposto a Garbage Collection.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 Viene causata una Garbage Collection ogni volta che un thread passa dal codice gestito al codice non gestito.  
  
## <a name="output"></a>Output  
 Questo assistente al debug gestito non produce output.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
- [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
