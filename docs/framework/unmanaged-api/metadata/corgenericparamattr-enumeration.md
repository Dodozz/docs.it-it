---
title: Enumerazione CorGenericParamAttr
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0aa9b84c9e16811f799a3cd2ad096508db3f7d34
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045789"
---
# <a name="corgenericparamattr-enumeration"></a>Enumerazione CorGenericParamAttr
Contiene valori che descrivono il <xref:System.Type> parametri per i tipi generici, come usati nelle chiamate al [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,   
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,   
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`gpVarianceMask`|La varianza di parametro si applica solo a parametri generici per interfacce e delegati.|  
|`gpNonVariant`|Indica l'assenza di varianza.|  
|`gpCovariant`|Indica la covarianza.|  
|`gpContravariant`|Indica la controvarianza.|  
|`gpSpecialConstraintMask`|I vincoli speciali possono applicare a qualsiasi <xref:System.Type> parametro.|  
|`gpNoSpecialConstraint`|Indica che nessun vincolo si applica al <xref:System.Type> parametro.|  
|`gpReferenceTypeConstraint`|Indica che il <xref:System.Type> parametro deve essere un tipo di riferimento.|  
|`gpNotNullableValueTypeConstraint`|Indica che il <xref:System.Type> parametro deve essere un tipo di valore che non può essere un valore null.|  
|`gpDefaultConstructorConstraint`|Indica che il <xref:System.Type> parametro deve avere un costruttore pubblico predefinito che non accetta parametri.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
