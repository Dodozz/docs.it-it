---
title: Proprietà SqlStreamChars.CanSeek (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: b85e21c6bc89d2a00ff8d302f67a3d074d5e7b8f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634379"
---
# <a name="sqlstreamcharscanseek-property"></a>Proprietà SqlStreamChars.CanSeek

Quando sottoposto a override in una classe derivata, ottiene un valore che indica se il flusso corrente supporta l'operazione di ricerca. L'assembly che contiene questa proprietà ha una relazione di tipo friend SQLAccess. Si tratta per l'uso da SQL Server. Per altri database, usare il meccanismo di hosting fornito da tale database.

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a>Valore della proprietà

<xref:System.Boolean>\
`true` Se il flusso corrente supporta l'operazione di ricerca; in caso contrario, `false`.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `SqlStreamChars.CanSeek` proprietà è privato e non deve essere utilizzato direttamente nel codice.
>
> Microsoft non supporta l'uso di questo campo in un'applicazione di produzione in alcuna circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Data.SqlTypes>

**Assembly:** System. Data (in System)

**Versioni di .NET framework:** Disponibile dalla 2.0.
