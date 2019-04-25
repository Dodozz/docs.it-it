---
title: Ricerca di attestazioni in un ClaimSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: 42e6ee682220913f872da337eb41f6c290082988
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61856426"
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="764c7-102">Ricerca di attestazioni in un ClaimSet</span><span class="sxs-lookup"><span data-stu-id="764c7-102">Finding Claims in a ClaimSet</span></span>
<span data-ttu-id="764c7-103">L'esame del contenuto di una classe <xref:System.IdentityModel.Claims.ClaimSet> per particolari tipi di attestazioni è un'attività comune quando si utilizza l'autorizzazione basata sulle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="764c7-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="764c7-104">Per esaminare una classe <xref:System.IdentityModel.Claims.ClaimSet> al fine di verificare la presenza di attestazioni particolari, utilizzare il metodo <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A>.</span><span class="sxs-lookup"><span data-stu-id="764c7-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="764c7-105">Questo metodo fornisce prestazioni migliori che non l'iterazione diretta su <xref:System.IdentityModel.Claims.ClaimSet>.</span><span class="sxs-lookup"><span data-stu-id="764c7-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="764c7-106">Nell'esempio seguente viene illustrata questa sintassi.</span><span class="sxs-lookup"><span data-stu-id="764c7-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="764c7-107">Si noti che i parametri `claimType` e `claimRight` possono essere `null`.</span><span class="sxs-lookup"><span data-stu-id="764c7-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="764c7-108">In tal caso i parametri corrisponderanno a tutti i tipi e i diritti di attestazione.</span><span class="sxs-lookup"><span data-stu-id="764c7-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="764c7-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="764c7-109">Example</span></span>  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="764c7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="764c7-110">See also</span></span>

- [<span data-ttu-id="764c7-111">Gestione delle attestazioni e dell'autorizzazione con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="764c7-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
