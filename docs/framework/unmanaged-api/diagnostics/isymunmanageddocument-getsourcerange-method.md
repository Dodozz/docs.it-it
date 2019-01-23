---
title: Metodo ISymUnmanagedDocument::GetSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a89c706ece0949ffa3c182d53b57221acf81b18d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515070"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="45ae6-102">Metodo ISymUnmanagedDocument::GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="45ae6-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="45ae6-103">Restituisce l'intervallo specificato dell'origine incorporata al buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="45ae6-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="45ae6-104">Il buffer deve essere sufficientemente grande da contenere l'origine.</span><span class="sxs-lookup"><span data-stu-id="45ae6-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ae6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45ae6-105">Syntax</span></span>  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45ae6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="45ae6-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="45ae6-107">[in] La riga iniziale del documento corrente.</span><span class="sxs-lookup"><span data-stu-id="45ae6-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="45ae6-108">[in] La colonna iniziale del documento corrente.</span><span class="sxs-lookup"><span data-stu-id="45ae6-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="45ae6-109">[in] La riga finale nel documento corrente.</span><span class="sxs-lookup"><span data-stu-id="45ae6-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="45ae6-110">[in] La colonna finale del documento corrente.</span><span class="sxs-lookup"><span data-stu-id="45ae6-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="45ae6-111">[in] Le dimensioni dell'origine, in byte.</span><span class="sxs-lookup"><span data-stu-id="45ae6-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="45ae6-112">[out] Puntatore a una variabile che riceve le dimensioni di origine.</span><span class="sxs-lookup"><span data-stu-id="45ae6-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="45ae6-113">[out] Le dimensioni e la lunghezza dell'intervallo specificato del documento di origine, in byte.</span><span class="sxs-lookup"><span data-stu-id="45ae6-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45ae6-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="45ae6-114">Return Value</span></span>  
 <span data-ttu-id="45ae6-115">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="45ae6-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ae6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45ae6-116">See also</span></span>
- [<span data-ttu-id="45ae6-117">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="45ae6-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
