---
title: MDA raceOnRCWCleanup
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628790bb8229dc519589c122235f07a38ba57c1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791575"
---
# <a name="raceonrcwcleanup-mda"></a>MDA raceOnRCWCleanup
L'assistente al debug gestito `raceOnRCWCleanup` viene attivato quando Common Language Runtime (CLR) rileva che è in uso un oggetto [Runtime Callable Wrapper (RCW)](../../../docs/framework/interop/runtime-callable-wrapper.md) quando viene eseguita una chiamata per rilasciarlo con un comando come il metodo <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>.  
  
## <a name="symptoms"></a>Sintomi  
 Violazioni di accesso o danneggiamento della memoria durante o dopo il rilascio di un RCW con <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> o un metodo simile.  
  
## <a name="cause"></a>Causa  
 Il wrapper RCW è in uso in un altro thread o durante il rilascio dello stack di thread.  Non è possibile rilasciare un RCW in uso.  
  
## <a name="resolution"></a>Risoluzione  
 Non rilasciare un RCW che potrebbe essere in uso nel thread corrente o in altri.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
 Messaggio che descrive l'errore.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
