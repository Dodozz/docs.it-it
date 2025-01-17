---
title: Elemento <clear> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d4d96143dbd1db440de2247a7dc2f0c66f20403
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301292"
---
# <a name="clear-element-for-appsettings"></a>\<Cancella > (elemento) per \<appSettings >

Cancella le impostazioni dell'applicazione personalizzata.

[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings >** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**

## <a name="syntax"></a>Sintassi

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a>Attributi

nessuno

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [ **\<appSettings>** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | Contiene le impostazioni dell'applicazione personalizzata, ad esempio i percorsi dei file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata. |

## <a name="child-elements"></a>Elementi figlio

nessuno

## <a name="example"></a>Esempio

Nell'esempio seguente illustra come cancellare le impostazioni di configurazione personalizzato:

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a>Vedere anche

- [Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
