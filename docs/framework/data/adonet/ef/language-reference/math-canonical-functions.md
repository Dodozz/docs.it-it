---
title: Funzioni matematiche canoniche
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: f575785bb198251ef50ba3563e736946253c9526
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760636"
---
# <a name="math-canonical-functions"></a>Funzioni matematiche canoniche

Entity SQL include le funzioni canoniche matematiche seguenti:
  
## <a name="absvalue"></a>Abs(value)

Restituisce il valore assoluto di `value`.

**Argomenti**

Un' `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, e `Decimal`.

**Valore restituito**

Tipo di `value`.

**Esempio**

`Abs(-2)`

## <a name="ceilingvalue"></a>Ceiling(value)

Restituisce il valore integer più piccolo non minore di `value`.

**Argomenti**

Oggetto `Single`, `Double`, e `Decimal`.

**Valore restituito**

Tipo di `value`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a>Floor(value)

Restituisce il valore integer più grande non maggiore di `value`.

**Argomenti**

Oggetto `Single`, `Double`, e `Decimal`.

**Valore restituito**

Tipo di `value`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a>Power(value, exponent)

Restituisce il risultato dell'oggetto `value` specificato all'oggetto `exponent` specificato.

**Argomenti**

|  |  |
|--|--|
|`value` | Un' `Int32, Int64, Double`, o `Decimal`. |
|`exponent` | Un' `Int64`, `Double`, o `Decimal`. |

**Valore restituito**

Tipo di `value`.

**Esempio**

`Power(748.58,2)`

## <a name="roundvalue"></a>Round(value)

Restituisce la parte intera di `value` arrotondata al valore integer più vicino.

**Argomenti**

Oggetto `Single`, `Double`, e `Decimal`.

**Valore restituito**

Tipo di `value`.

**Esempio**

`Round(748.58)`

## <a name="roundvalue-digits"></a>Round(value, digits)

Restituisce `value`, arrotondato al valore di `digits` specificato più vicino.

**Argomenti**

|  |  |
|--|--|
|`value`|`Double` o `Decimal`.|
|`digits`|`Int16` o `Int32`.|

**Valore restituito**

Tipo di `value`.

**Esempio**

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a>Truncate(value, digits)

Restituisce `value`, troncato al valore di `digits` specificato più vicino.

**Argomenti**

|  |  |
|--|--|
|`value`|`Double` o `Decimal`.|
|`digits`|`Int16` o `Int32`.|

**Valore restituito**

Tipo di `value`.

**Esempio**

`Truncate(748.58,1)`  
  
 Queste funzioni restituiscono `null` se l'input è `null`.  
  
 Una funzionalità equivalente è disponibile nel provider gestito del client Microsoft SQL. Per altre informazioni, vedere [SqlClient per funzioni Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
