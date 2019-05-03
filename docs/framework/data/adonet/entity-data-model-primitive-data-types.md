---
title: 'Entity Data Model: tipi di dati primitivi'
ms.date: 03/30/2017
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
ms.openlocfilehash: 044a0ed981bb9cda3550fb3a3a9f1cb9bff96f25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667132"
---
# <a name="entity-data-model-primitive-data-types"></a>Entity Data Model: tipi di dati primitivi
Entity Data Model (EDM) supporta un set di tipi di dati primitivi astratti (ad esempio String, Boolean, Int32 e così via) che vengono usate per definire [proprietà](../../../../docs/framework/data/adonet/property.md) in un modello concettuale. Questi tipi di dati primitivi sono proxy per i tipi di dati primitivi effettivi supportati nell'ambiente di archiviazione o host, ad esempio un database SQL Server o Common Language Runtime (CLR). EDM non definisce la semantica di operazioni o conversioni su tipi di dati primitivi. Questa semantica viene definita dall'ambiente di archiviazione o host. I tipi di dati primitivi in EDM sono in genere associati ai corrispondenti tipi di dati primitivi nell'ambiente di archiviazione o host. Per informazioni su come Entity Framework esegue il mapping di tipi primitivi in EDM ai tipi di dati di SQL Server, vedere [SqlClient per tipi Entity FrameworkTypes](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
> [!NOTE]
>  EDM non supporta raccolte di tipi di dati primitivi.  
  
 Per informazioni sui tipi di dati strutturati in EDM, vedere [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) e [tipo complesso](../../../../docs/framework/data/adonet/complex-type.md).  
  
## <a name="primitive-data-types-supported-in-the-entity-data-model"></a>Tipi di dati primitivi supportati in Entity Data Model  
 Nella tabella seguente vengono elencati i tipi di dati primitivi supportati da EDM. La tabella include anche il [facet](../../../../docs/framework/data/adonet/facet.md) che possono essere applicati a ogni tipo di dati primitivi.  
  
|Tipi di dati primitivi|Descrizione|Facet applicabili|  
|-------------------------|-----------------|-----------------------|  
|Binario|Contiene dati binari.|MaxLength, FixedLength, Nullable, Default|  
|Booleano|Contiene il valore `true` o `false`.|Nullable, Default|  
|Byte|Contiene un Unsigned Integer a 8 bit.|Precision, Nullable, Default|  
|DateTime|Rappresenta una data e un'ora.|Precision, Nullable, Default|  
|DateTimeOffset|Contiene una data e un'ora come offset in minuti rispetto all'ora GMT.|Precision, Nullable, Default|  
|Decimale|Contiene un valore numerico con scala e precisione fisse.|Precision, Nullable, Default|  
|Double|Contiene un numero a virgola mobile con precisione a 15 cifre.|Precision, Nullable, Default|  
|Float|Contiene un numero a virgola mobile con precisione a sette cifre.|Precision, Nullable, Default|  
|GUID|Contiene un identificatore univoco a 16 byte.|Precision, Nullable, Default|  
|Int16|Contiene un Signed Integer a 16 bit.|Precision, Nullable, Default|  
|Int32|Contiene un Signed Integer a 32 bit.|Precision, Nullable, Default|  
|Int64|Contiene un Signed Integer a 64 bit.|Precision, Nullable, Default|  
|SByte|Contiene un Signed Integer a 8 bit.|Precision, Nullable, Default|  
|Stringa|Contiene dati di tipo carattere.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|Ora|Contiene un'ora del giorno.|Precision, Nullable, Default|  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
