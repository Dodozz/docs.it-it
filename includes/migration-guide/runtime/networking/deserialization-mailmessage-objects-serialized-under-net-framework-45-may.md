---
ms.openlocfilehash: a6f93bbdf39a1b525e2daeb12afc3a6392a66e30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235754"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="e425e-101">La deserializzazione di oggetti MailMessage serializzati in .NET Framework 4.5 può non riuscire</span><span class="sxs-lookup"><span data-stu-id="e425e-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e425e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e425e-102">Details</span></span>|<span data-ttu-id="e425e-103">A partire da .NET Framework 4.5, gli oggetti <xref:System.Web.Mail.MailMessage> possono includere caratteri non ASCII.</span><span class="sxs-lookup"><span data-stu-id="e425e-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="e425e-104">In .NET Framework 4, sono supportati solo caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="e425e-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="e425e-105">Gli oggetti <xref:System.Web.Mail.MailMessage> che contengono caratteri non ASCII e che vengono serializzati in .NET Framework 4.5 o versione successiva non possono essere deserializzati in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e425e-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>|
|<span data-ttu-id="e425e-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="e425e-106">Suggestion</span></span>|<span data-ttu-id="e425e-107">Quando si deserializza un oggetto <xref:System.Web.Mail.MailMessage>, verificare che il codice consenta la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e425e-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>|
|<span data-ttu-id="e425e-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="e425e-108">Scope</span></span>|<span data-ttu-id="e425e-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="e425e-109">Minor</span></span>|
|<span data-ttu-id="e425e-110">Versione</span><span class="sxs-lookup"><span data-stu-id="e425e-110">Version</span></span>|<span data-ttu-id="e425e-111">4.5</span><span class="sxs-lookup"><span data-stu-id="e425e-111">4.5</span></span>|
|<span data-ttu-id="e425e-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="e425e-112">Type</span></span>|<span data-ttu-id="e425e-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="e425e-113">Runtime</span></span>|
|<span data-ttu-id="e425e-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="e425e-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
