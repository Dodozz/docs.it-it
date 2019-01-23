---
title: Metodo ISymUnmanagedDocument::GetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 406fdfcfc0b6db988b317245aaaa4f4a643b2079
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561400"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="cd5be-102">Metodo ISymUnmanagedDocument::GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="cd5be-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="cd5be-103">Ottiene il checksum.</span><span class="sxs-lookup"><span data-stu-id="cd5be-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd5be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd5be-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd5be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cd5be-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="cd5be-106">[in] La lunghezza del buffer fornito dal `data` parametro</span><span class="sxs-lookup"><span data-stu-id="cd5be-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="cd5be-107">[out] Le dimensioni e lunghezza del checksum, in byte.</span><span class="sxs-lookup"><span data-stu-id="cd5be-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="cd5be-108">[out] Buffer che riceve il valore di checksum.</span><span class="sxs-lookup"><span data-stu-id="cd5be-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd5be-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cd5be-109">Return Value</span></span>  
 <span data-ttu-id="cd5be-110">S_OK se il metodo ha esito positivo; in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cd5be-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd5be-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd5be-111">See also</span></span>
- [<span data-ttu-id="cd5be-112">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="cd5be-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
