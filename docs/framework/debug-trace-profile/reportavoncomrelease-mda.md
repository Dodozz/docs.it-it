---
title: MDA reportAvOnComRelease
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c70c70f251fca9312019d4c63304e8354bf87fd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729158"
---
# <a name="reportavoncomrelease-mda"></a>MDA reportAvOnComRelease
L'assistente al debug gestito `reportAvOnComRelease` viene attivato quando vengono generate eccezioni a causa di errori nel conteggio dei riferimenti utente durante l'esecuzione dell'interoperabilità COM e l'uso del metodo <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> in combinazione con chiamate COM non elaborate.  
  
## <a name="symptoms"></a>Sintomi  
 Violazioni di accesso e danneggiamento della memoria.  
  
## <a name="cause"></a>Causa  
 Occasionalmente viene generata un'eccezione a causa di errori nel conteggio dei riferimenti utente durante l'esecuzione dell'interoperabilità COM e l'uso del metodo <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> in combinazione con chiamate COM non elaborate. Di solito questa eccezione viene eliminata in quanto, in caso contrario, si verificherebbe una violazione di accesso in CLR con il conseguente arresto di quest'ultimo. Quando l'assistente è abilitato, le eccezioni di questo tipo possono essere rilevate e segnalate anziché semplicemente eliminate.  
  
## <a name="resolution"></a>Risoluzione  
 Esaminare il codice del conteggio dei riferimenti e cercare gli errori e verificare la presenza di errori nel conteggio dei riferimenti sui client nativi dell'oggetto.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 Sono disponibili due modalità. Se l'attributo `allowAv` è `true`, l'assistente impedisce al runtime l'eliminazione della violazione di accesso. Se invece l'attributo `allowAv` è `false`, impostazione predefinita, il runtime elimina la violazione di accesso ma l'utente riceve un messaggio di avviso nel quale è indicato che un'eccezione è stata generata ed eliminata.  
  
## <a name="output"></a>Output  
 Se possibile, l'output contiene il vtable originale del puntatore a interfaccia COM. In caso contrario, viene visualizzato un messaggio informativo.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
