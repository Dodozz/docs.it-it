---
title: Il nome origine specificato in EventLogSource è registrato in un log diverso da quello indicato in EventLogName
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 03fcc41b0fbb84233aa037d7af17d168050a98b6
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086368"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="0ed91-102">Il nome origine specificato in EventLogSource è registrato in un log diverso da quello indicato in EventLogName</span><span class="sxs-lookup"><span data-stu-id="0ed91-102">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>
<span data-ttu-id="0ed91-103">`EventLog` sta provando a fare riferimento a un'origine registrata in un log diverso.</span><span class="sxs-lookup"><span data-stu-id="0ed91-103">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="0ed91-104">Se si scrivono le voci in un log eventi, è necessario specificare la proprietà <xref:System.Diagnostics.EventLog.Source%2A> .</span><span class="sxs-lookup"><span data-stu-id="0ed91-104">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="0ed91-105">La proprietà <xref:System.Diagnostics.EventLog.Source%2A> registra il componente con il log eventi come origine valida delle voci.</span><span class="sxs-lookup"><span data-stu-id="0ed91-105">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="0ed91-106">Una singola origine può essere associata a (e quindi scrivere voci in) un solo log eventi alla volta.</span><span class="sxs-lookup"><span data-stu-id="0ed91-106">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="0ed91-107">Per impostazione predefinita, se si prova a scrivere una voce senza prima aver registrato il componente come origine valida, il sistema registra automaticamente l'origine con il log eventi, usando il valore della proprietà <xref:System.Diagnostics.EventLog.Source%2A> come stringa di origine.</span><span class="sxs-lookup"><span data-stu-id="0ed91-107">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0ed91-108">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="0ed91-108">To correct this error</span></span>  
  
-   <span data-ttu-id="0ed91-109">Verificare che l'origine sia registrata nel log corretto.</span><span class="sxs-lookup"><span data-stu-id="0ed91-109">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="0ed91-110">A tale scopo, usare il metodo <xref:System.Diagnostics.EventLog.CreateEventSource%2A> o uno dei relativi overload per specificare una stringa che identifica in modo univoco il componente nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="0ed91-110">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed91-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ed91-111">See Also</span></span>  
 [<span data-ttu-id="0ed91-112">Gestione dei log eventi</span><span class="sxs-lookup"><span data-stu-id="0ed91-112">Administering Event Logs</span></span>](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [<span data-ttu-id="0ed91-113">Riferimenti del Log eventi</span><span class="sxs-lookup"><span data-stu-id="0ed91-113">Event Log References</span></span>](https://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [<span data-ttu-id="0ed91-114">Procedura: aggiungere l'applicazione come origine delle voci del registro eventi</span><span class="sxs-lookup"><span data-stu-id="0ed91-114">How to: Add Your Application as a Source of Event Log Entries</span></span>](https://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)  
 [<span data-ttu-id="0ed91-115">Procedura: rimuovere un'origine evento</span><span class="sxs-lookup"><span data-stu-id="0ed91-115">How to: Remove an Event Source</span></span>](https://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
