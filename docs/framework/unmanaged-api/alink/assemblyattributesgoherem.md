---
title: AssemblyAttributesGoHereM
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHereM
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bbd5428039144fd38796ed6865c24a605f236ccd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733805"
---
# <a name="assemblyattributesgoherem"></a><span data-ttu-id="3913a-102">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="3913a-102">AssemblyAttributesGoHereM</span></span>
<span data-ttu-id="3913a-103">Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3913a-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3913a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3913a-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHereM  
```  
  
## <a name="remarks"></a><span data-ttu-id="3913a-105">Note</span><span class="sxs-lookup"><span data-stu-id="3913a-105">Remarks</span></span>  
 <span data-ttu-id="3913a-106">I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3913a-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="3913a-107">Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3913a-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="3913a-108">Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.</span><span class="sxs-lookup"><span data-stu-id="3913a-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="3913a-109">I riferimenti a questo tipo indicano gli attributi personalizzati che non sono correlati alla sicurezza ma sono multiuso.</span><span class="sxs-lookup"><span data-stu-id="3913a-109">References to this type indicate custom attributes that are not security related but are multiple-use.</span></span>  
  
 <span data-ttu-id="3913a-110">Tali tipi sono contrassegnati come "interni" in .NET Framework e sono disponibili in <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="3913a-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3913a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3913a-111">Requirements</span></span>  
 <span data-ttu-id="3913a-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="3913a-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3913a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3913a-113">See also</span></span>
- [<span data-ttu-id="3913a-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="3913a-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)
- [<span data-ttu-id="3913a-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="3913a-115">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)
- [<span data-ttu-id="3913a-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="3913a-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
