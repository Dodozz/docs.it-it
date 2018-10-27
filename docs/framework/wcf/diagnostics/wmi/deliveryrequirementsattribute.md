---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: 7bfc03299fffc8070a7d8a4b3885706ea861bdf6
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2018
ms.locfileid: "50042896"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="3076f-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="3076f-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="3076f-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="3076f-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3076f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3076f-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3076f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3076f-105">Methods</span></span>  
 <span data-ttu-id="3076f-106">La classe DeliveryRequirementsAttribute non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="3076f-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3076f-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3076f-107">Properties</span></span>  
 <span data-ttu-id="3076f-108">La classe DeliveryRequirementsAttribute dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3076f-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="3076f-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="3076f-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="3076f-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3076f-110">Data type: string</span></span>  
  
 <span data-ttu-id="3076f-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3076f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3076f-112">Specifica se l'associazione di un servizio supporta i contratti.</span><span class="sxs-lookup"><span data-stu-id="3076f-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="3076f-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="3076f-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="3076f-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="3076f-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="3076f-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3076f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3076f-116">Specifica se l'associazione supporta i messaggi ordinati.</span><span class="sxs-lookup"><span data-stu-id="3076f-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="3076f-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="3076f-117">TargetContract</span></span>  
 <span data-ttu-id="3076f-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3076f-118">Data type: string</span></span>  
  
 <span data-ttu-id="3076f-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3076f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3076f-120">Contratto a cui viene applicato.</span><span class="sxs-lookup"><span data-stu-id="3076f-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3076f-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3076f-121">Requirements</span></span>  
  
|<span data-ttu-id="3076f-122">MOF</span><span class="sxs-lookup"><span data-stu-id="3076f-122">MOF</span></span>|<span data-ttu-id="3076f-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3076f-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3076f-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3076f-124">Namespace</span></span>|<span data-ttu-id="3076f-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3076f-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3076f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3076f-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
