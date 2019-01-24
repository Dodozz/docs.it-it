---
title: Il nome origine specificato in EventLogSource è registrato in un log diverso da quello indicato in EventLogName
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 4de98bef87b871036c3c5730ff09cf94c1df2918
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584571"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>Il nome origine specificato in EventLogSource è registrato in un log diverso da quello indicato in EventLogName
`EventLog` sta provando a fare riferimento a un'origine registrata in un log diverso. Se si scrivono le voci in un log eventi, è necessario specificare la proprietà <xref:System.Diagnostics.EventLog.Source%2A> . La proprietà <xref:System.Diagnostics.EventLog.Source%2A> registra il componente con il log eventi come origine valida delle voci. Una singola origine può essere associata a (e quindi scrivere voci in) un solo log eventi alla volta.  
  
 Per impostazione predefinita, se si prova a scrivere una voce senza prima aver registrato il componente come origine valida, il sistema registra automaticamente l'origine con il log eventi, usando il valore della proprietà <xref:System.Diagnostics.EventLog.Source%2A> come stringa di origine.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Verificare che l'origine sia registrata nel log corretto. A tale scopo, usare il metodo <xref:System.Diagnostics.EventLog.CreateEventSource%2A> o uno dei relativi overload per specificare una stringa che identifica in modo univoco il componente nel log eventi.  
  
## <a name="see-also"></a>Vedere anche
- [Gestione dei log eventi](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)
- [Riferimenti del Log eventi](https://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)
- [Procedura: Aggiungere l'applicazione come origine delle voci del registro eventi](https://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)
- [Procedura: Rimuovere un'origine evento](https://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
