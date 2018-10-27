---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 6266713307846ab953299370835726958196fac1
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185339"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="86f51-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="86f51-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="86f51-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="86f51-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f51-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86f51-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="86f51-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="86f51-105">Methods</span></span>  
 <span data-ttu-id="86f51-106">La classe OperationBehaviorAttribute non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="86f51-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="86f51-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="86f51-107">Properties</span></span>  
 <span data-ttu-id="86f51-108">La classe OperationBehaviorAttribute dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="86f51-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="86f51-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="86f51-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="86f51-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="86f51-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="86f51-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="86f51-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="86f51-112">Stato della funzionalità di eliminazione automatica per i parametri.</span><span class="sxs-lookup"><span data-stu-id="86f51-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="86f51-113">Rappresentazione</span><span class="sxs-lookup"><span data-stu-id="86f51-113">Impersonation</span></span>  
 <span data-ttu-id="86f51-114">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="86f51-114">Data type: string</span></span>  
  
 <span data-ttu-id="86f51-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="86f51-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="86f51-116">Indica il livello di rappresentazione del chiamante supportato dall'operazione.</span><span class="sxs-lookup"><span data-stu-id="86f51-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="86f51-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="86f51-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="86f51-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="86f51-118">Data type: string</span></span>  
  
 <span data-ttu-id="86f51-119">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="86f51-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="86f51-120">Indica quando riciclare l'oggetto nel corso della chiamata a un'operazione.</span><span class="sxs-lookup"><span data-stu-id="86f51-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="86f51-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="86f51-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="86f51-122">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="86f51-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="86f51-123">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="86f51-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="86f51-124">Indica se eseguire automaticamente il commit della transazione corrente se non si verifica alcuna eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="86f51-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="86f51-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="86f51-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="86f51-126">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="86f51-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="86f51-127">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="86f51-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="86f51-128">Indica se l'operazione richiede una transazione.</span><span class="sxs-lookup"><span data-stu-id="86f51-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86f51-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86f51-129">Requirements</span></span>  
  
|<span data-ttu-id="86f51-130">MOF</span><span class="sxs-lookup"><span data-stu-id="86f51-130">MOF</span></span>|<span data-ttu-id="86f51-131">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="86f51-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="86f51-132">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="86f51-132">Namespace</span></span>|<span data-ttu-id="86f51-133">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="86f51-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86f51-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86f51-134">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
