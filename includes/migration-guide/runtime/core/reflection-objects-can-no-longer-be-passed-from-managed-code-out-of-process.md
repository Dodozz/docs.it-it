---
ms.openlocfilehash: 38c774417fc94fa080bf2b82c04d575e9068cdcb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59234177"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Gli oggetti Reflection non possono essere più passati dal codice gestito ai client DCOM out-of-process

|   |   |
|---|---|
|Dettagli|Gli oggetti di reflection non possono essere più passati dal codice gestito ai client DCOM out-of-process. Sono interessati i tipi seguenti:<ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><xref:System.Reflection.MemberInfo?displayProperty=name> e i tipi derivati, inclusi <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name> e <xref:System.Reflection.TypeInfo?displayProperty=name></li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><xref:System.Reflection.ParameterInfo?displayProperty=name>.</li></ul>Le chiamate a <code>IMarshal</code> per l'oggetto restituiscono <code>E_NOINTERFACE</code>.|
|Suggerimento|Aggiornare il codice di marshalling in modo che funzioni con oggetti non di reflection|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Runtime|
