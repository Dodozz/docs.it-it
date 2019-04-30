---
title: Enumerazione1 CorElementType
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 581c5517144dbc94e16acb777b5c272b8390b212
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046010"
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="68640-102">Enumerazione1 CorElementType</span><span class="sxs-lookup"><span data-stu-id="68640-102">CorElementType Enumeration1</span></span>
<span data-ttu-id="68640-103">Specifica un common language runtime <xref:System.Type>, un modificatore di tipo o informazioni su un tipo in una firma del tipo di metadati.</span><span class="sxs-lookup"><span data-stu-id="68640-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68640-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68640-104">Syntax</span></span>  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a><span data-ttu-id="68640-105">Membri</span><span class="sxs-lookup"><span data-stu-id="68640-105">Members</span></span>  
  
|<span data-ttu-id="68640-106">Member</span><span class="sxs-lookup"><span data-stu-id="68640-106">Member</span></span>|<span data-ttu-id="68640-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68640-107">Description</span></span>|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|<span data-ttu-id="68640-108">Utilizzato internamente.</span><span class="sxs-lookup"><span data-stu-id="68640-108">Used internally.</span></span>|  
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="68640-109">Un tipo void.</span><span class="sxs-lookup"><span data-stu-id="68640-109">A void type.</span></span>|  
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="68640-110">Un tipo Boolean</span><span class="sxs-lookup"><span data-stu-id="68640-110">A Boolean type</span></span>|  
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="68640-111">Tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="68640-111">A character type.</span></span>|  
|`ELEMENT_TYPE_I1`|<span data-ttu-id="68640-112">Un intero con segno a 1 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-112">A signed 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_U1`|<span data-ttu-id="68640-113">Intero senza segno a 1 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-113">An unsigned 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_I2`|<span data-ttu-id="68640-114">Un intero con segno a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-114">A signed 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_U2`|<span data-ttu-id="68640-115">Valore intero senza segno a 2 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-115">An unsigned 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_I4`|<span data-ttu-id="68640-116">Un intero con segno a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-116">A signed 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_U4`|<span data-ttu-id="68640-117">Valore intero senza segno a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-117">An unsigned 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_I8`|<span data-ttu-id="68640-118">Un intero con segno a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-118">A signed 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_U8`|<span data-ttu-id="68640-119">Valore intero senza segno a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-119">An unsigned 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_R4`|<span data-ttu-id="68640-120">Virgola mobile a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-120">A 4-byte floating point.</span></span>|  
|`ELEMENT_TYPE_R8`|<span data-ttu-id="68640-121">Una virgola mobile a 8 byte.</span><span class="sxs-lookup"><span data-stu-id="68640-121">An 8-byte floating point.</span></span>|  
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="68640-122">Un tipo System. String.</span><span class="sxs-lookup"><span data-stu-id="68640-122">A System.String type.</span></span>|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="68640-123">Un modificatore di tipo puntatore.</span><span class="sxs-lookup"><span data-stu-id="68640-123">A pointer type modifier.</span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="68640-124">Un modificatore di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="68640-124">A reference type modifier.</span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="68640-125">Un modificatore di tipo valore.</span><span class="sxs-lookup"><span data-stu-id="68640-125">A value type modifier.</span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="68640-126">Un modificatore di tipo classe.</span><span class="sxs-lookup"><span data-stu-id="68640-126">A class type modifier.</span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="68640-127">Un modificatore di tipo della variabile di classe.</span><span class="sxs-lookup"><span data-stu-id="68640-127">A class variable type modifier.</span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="68640-128">Un modificatore di tipo matrice multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="68640-128">A multi-dimensional array type modifier.</span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="68640-129">Un modificatore di tipo per i tipi generici.</span><span class="sxs-lookup"><span data-stu-id="68640-129">A type modifier for generic types.</span></span>|  
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="68640-130">Riferimento tipizzato.</span><span class="sxs-lookup"><span data-stu-id="68640-130">A typed reference.</span></span>|  
|`ELEMENT_TYPE_I`|<span data-ttu-id="68640-131">Dimensioni di un integer nativo.</span><span class="sxs-lookup"><span data-stu-id="68640-131">Size of a native integer.</span></span>|  
|`ELEMENT_TYPE_U`|<span data-ttu-id="68640-132">Dimensione dell'integer nativo senza segno.</span><span class="sxs-lookup"><span data-stu-id="68640-132">Size of an unsigned native integer.</span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="68640-133">Un puntatore a una funzione.</span><span class="sxs-lookup"><span data-stu-id="68640-133">A pointer to a function.</span></span>|  
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="68640-134">Un tipo System. Object.</span><span class="sxs-lookup"><span data-stu-id="68640-134">A System.Object type.</span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="68640-135">Un singolo-dimensionale, zero modificatore di tipo matrice con limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="68640-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="68640-136">Un modificatore di tipo di variabile (metodo).</span><span class="sxs-lookup"><span data-stu-id="68640-136">A method variable type modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="68640-137">Modificatore obbligatorio del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="68640-137">A C language required modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="68640-138">Un modificatore facoltativo del linguaggio C.</span><span class="sxs-lookup"><span data-stu-id="68640-138">A C language optional modifier.</span></span>|  
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="68640-139">Utilizzato internamente.</span><span class="sxs-lookup"><span data-stu-id="68640-139">Used internally.</span></span>|  
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="68640-140">Tipo non valido.</span><span class="sxs-lookup"><span data-stu-id="68640-140">An invalid type.</span></span>|  
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="68640-141">Utilizzato internamente.</span><span class="sxs-lookup"><span data-stu-id="68640-141">Used internally.</span></span>|  
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="68640-142">Un modificatore di tipo che è un sentinel per un elenco di un numero variabile di parametri.</span><span class="sxs-lookup"><span data-stu-id="68640-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|  
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="68640-143">Utilizzato internamente.</span><span class="sxs-lookup"><span data-stu-id="68640-143">Used internally.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68640-144">Note</span><span class="sxs-lookup"><span data-stu-id="68640-144">Remarks</span></span>  
 <span data-ttu-id="68640-145">I modificatori di tipo costituiscono la base per la rappresentazione di tipi più complessi.</span><span class="sxs-lookup"><span data-stu-id="68640-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="68640-146">Oggetto `CorElementType` valore del modificatore del tipo viene applicato al valore che lo segue immediatamente nella firma del tipo.</span><span class="sxs-lookup"><span data-stu-id="68640-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="68640-147">Il valore che segue il `CorElementType` valore del modificatore del tipo può essere un `CorElementType` valore di tipo semplice, un token di metadati o altro valore, come specificato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="68640-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68640-148">Tutti i numeri (*numero*, *argomento conteggio*, *token di metadati*, *rank*, *conteggio*e *associata*) vengono archiviate come numeri interi compressi.</span><span class="sxs-lookup"><span data-stu-id="68640-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="68640-149">Visualizzare [Standard ECMA-335: Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) sul sito Web di ECMA per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="68640-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>  
  
|<span data-ttu-id="68640-150">Modificatore tipo</span><span class="sxs-lookup"><span data-stu-id="68640-150">Type modifier</span></span>|<span data-ttu-id="68640-151">Formato</span><span class="sxs-lookup"><span data-stu-id="68640-151">Format</span></span>|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="68640-152">ELEMENT_TYPE_PTR < un `CorElementType` valore ></span><span class="sxs-lookup"><span data-stu-id="68640-152">ELEMENT_TYPE_PTR <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="68640-153">ELEMENT_TYPE_BYREF < un `CorElementType` valore ></span><span class="sxs-lookup"><span data-stu-id="68640-153">ELEMENT_TYPE_BYREF <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="68640-154">ELEMENT_TYPE_VALUETYPE < un `mdTypeDef` token di metadati ></span><span class="sxs-lookup"><span data-stu-id="68640-154">ELEMENT_TYPE_VALUETYPE <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="68640-155">ELEMENT_TYPE_CLASS < un `mdTypeDef` token di metadati ></span><span class="sxs-lookup"><span data-stu-id="68640-155">ELEMENT_TYPE_CLASS <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="68640-156">ELEMENT_TYPE_VAR \<number></span><span class="sxs-lookup"><span data-stu-id="68640-156">ELEMENT_TYPE_VAR \<number></span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="68640-157">ELEMENT_TYPE_ARRAY < una `CorElementType` valore > \<rank > \<count1 > \<bound1 >... \<countN > \<boundN ></span><span class="sxs-lookup"><span data-stu-id="68640-157">ELEMENT_TYPE_ARRAY <a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="68640-158">ELEMENT_TYPE_GENERICINST < un' `mdTypeDef` token di metadati > \<argument Count > \<arg1 >... \<argN ></span><span class="sxs-lookup"><span data-stu-id="68640-158">ELEMENT_TYPE_GENERICINST <an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="68640-159">ELEMENT_TYPE_FNPTR \<firma completa per la funzione, inclusi la convenzione di chiamata ></span><span class="sxs-lookup"><span data-stu-id="68640-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="68640-160">ELEMENT_TYPE_SZARRAY < un `CorElementType` valore ></span><span class="sxs-lookup"><span data-stu-id="68640-160">ELEMENT_TYPE_SZARRAY <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="68640-161">ELEMENT_TYPE_MVAR \<number></span><span class="sxs-lookup"><span data-stu-id="68640-161">ELEMENT_TYPE_MVAR \<number></span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="68640-162">ELEMENT_TYPE _ < una `mdTypeRef` o `mdTypeDef` token di metadati ></span><span class="sxs-lookup"><span data-stu-id="68640-162">ELEMENT_TYPE_<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="68640-163">E_T_CMOD_OPT < una `mdTypeRef` o `mdTypeDef` token di metadati ></span><span class="sxs-lookup"><span data-stu-id="68640-163">E_T_CMOD_OPT <a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68640-164">Requisiti</span><span class="sxs-lookup"><span data-stu-id="68640-164">Requirements</span></span>  
 <span data-ttu-id="68640-165">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68640-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68640-166">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="68640-166">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="68640-167">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68640-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68640-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68640-168">See also</span></span>

- [<span data-ttu-id="68640-169">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="68640-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
