---
ms.openlocfilehash: ef0381dc2ce4373b2a62e8ebefa44152059ca332
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234696"
---
### <a name="xml-schema-validation-is-stricter"></a>La convalida di XML Schema è più rigida

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5 la convalida XML Schema è più rigida. Se si usa xsd:anyURI per convalidare un URI, come un protocollo mailto, la convalida ha esito negativo se sono presenti spazi nell'URI. Nelle versioni precedenti di .NET Framework la convalida aveva esito positivo. La modifica influisce solo sulle applicazioni destinate a .NET Framework 4.5.|
|Suggerimento|Se è necessario usare la convalida .NET Framework 4.0 meno restrittiva, l'applicazione da convalidare può essere destinata alla versione 4.0 di .NET Framework. In caso di ridestinazione a .NET Framework 4.5, tuttavia, è necessario rivedere il codice per assicurarsi che gli URI non validi (con spazi) non siano previsti come valori di attributo con il tipo di dati anyURI.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Ridestinazione|
