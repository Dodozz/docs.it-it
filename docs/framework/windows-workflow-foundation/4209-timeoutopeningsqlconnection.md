---
title: 4209 - TimeoutOpeningSqlConnection
ms.date: 03/30/2017
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
ms.openlocfilehash: d61d710959f99dbc8a91441766a690eb7e9a365c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774270"
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="50d91-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="50d91-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="50d91-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="50d91-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50d91-104">Id</span><span class="sxs-lookup"><span data-stu-id="50d91-104">ID</span></span>|<span data-ttu-id="50d91-105">4209</span><span class="sxs-lookup"><span data-stu-id="50d91-105">4209</span></span>|  
|<span data-ttu-id="50d91-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="50d91-106">Keywords</span></span>|<span data-ttu-id="50d91-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="50d91-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="50d91-108">Livello</span><span class="sxs-lookup"><span data-stu-id="50d91-108">Level</span></span>|<span data-ttu-id="50d91-109">Error</span><span class="sxs-lookup"><span data-stu-id="50d91-109">Error</span></span>|  
|<span data-ttu-id="50d91-110">Canale</span><span class="sxs-lookup"><span data-stu-id="50d91-110">Channel</span></span>|<span data-ttu-id="50d91-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="50d91-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="50d91-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50d91-112">Description</span></span>  
 <span data-ttu-id="50d91-113">Indica che è stato rilevato un timeout durante il tentativo di stabilire una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="50d91-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="50d91-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="50d91-114">Message</span></span>  
 <span data-ttu-id="50d91-115">Timeout durante il tentativo di aprire una connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="50d91-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="50d91-116">Operazione non completata entro il timeout assegnato di %1.</span><span class="sxs-lookup"><span data-stu-id="50d91-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="50d91-117">È possibile che la durata consentita per l'operazione fosse una porzione di un timeout più lungo.</span><span class="sxs-lookup"><span data-stu-id="50d91-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="50d91-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="50d91-118">Details</span></span>  
  
|<span data-ttu-id="50d91-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="50d91-119">Data Item Name</span></span>|<span data-ttu-id="50d91-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="50d91-120">Data Item Type</span></span>|<span data-ttu-id="50d91-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50d91-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="50d91-122">Timeout</span><span class="sxs-lookup"><span data-stu-id="50d91-122">Timeout</span></span>|<span data-ttu-id="50d91-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="50d91-123">xs:string</span></span>|<span data-ttu-id="50d91-124">Valore di timeout per l'apertura della connessione SQL.</span><span class="sxs-lookup"><span data-stu-id="50d91-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="50d91-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="50d91-125">AppDomain</span></span>|<span data-ttu-id="50d91-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="50d91-126">xs:string</span></span>|<span data-ttu-id="50d91-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="50d91-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
