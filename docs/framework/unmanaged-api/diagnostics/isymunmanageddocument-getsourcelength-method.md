---
title: Metodo ISymUnmanagedDocument::GetSourceLength
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: edafb60e5b6f9b913e89f4785dc34a58bf390f2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638769"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="7b8e4-102">Metodo ISymUnmanagedDocument::GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="7b8e4-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="7b8e4-103">Recupera la lunghezza, in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8e4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b8e4-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b8e4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b8e4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7b8e4-106">[out] Un puntatore a una variabile che indica la lunghezza, espressa in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b8e4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7b8e4-107">Return Value</span></span>  
 <span data-ttu-id="7b8e4-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8e4-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b8e4-109">See also</span></span>
- [<span data-ttu-id="7b8e4-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="7b8e4-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
