---
title: MDA invalidMemberDeclaration
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e5b4cb4a04a79a748f4ea2292bac67a88a6e9f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754362"
---
# <a name="invalidmemberdeclaration-mda"></a>MDA invalidMemberDeclaration
L'assistente al debug gestito `invalidMemberDeclaration` viene attivato per segnalare un errore che si è verificato durante l'identificazione della modalità di marshalling dei parametri di un membro che deve essere chiamato da COM.  
  
## <a name="symptoms"></a>Sintomi  
 A COM viene restituito un HRESULT di errore senza che sia stato chiamato il metodo gestito.  
  
## <a name="cause"></a>Causa  
 La causa più probabile è la presenza di un attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatibile in uno dei parametri.  
  
## <a name="resolution"></a>Risoluzione  
 Specificare attributi <xref:System.Runtime.InteropServices.MarshalAsAttribute> validi nei parametri.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
 Un messaggio informativo che contiene il nome del membro, il nome del tipo e il messaggio di errore.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
