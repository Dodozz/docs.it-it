---
title: '&lt;assemblyBinding&gt; (elemento) per &lt;configurazione&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 12065d8bc484f7bbf77ae18c67df1de0845167b2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083899"
---
# <a name="assemblybinding-element-for-configuration"></a>\<assemblyBinding > (elemento) per \<configuration >

Specifica i criteri di associazione degli assembly al livello di configurazione.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<assemblyBinding>**

## <a name="syntax"></a>Sintassi

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>Attributo

|           | Descrizione |
| --------- | ----------- |
| **xmlns** | Attributo obbligatorio.<br><br>Specifica lo spazio dei nomi XML necessario per il binding di assembly. Usare la stringa "urn:schemas-microsoft-com:asm.v1" come valore. |

## <a name="parent-element"></a>Elemento padre

|     | Descrizione |
| --- | ----------- |
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework. |

## <a name="child-element"></a>Elemento figlio

|     | Descrizione |
| --- | ----------- |
| [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | Specifica un file di configurazione da includere. |

## <a name="remarks"></a>Note

Il [  **\<linkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) elemento semplifica la gestione di assembly del componente, consentendo a file di configurazione in file di configurazione dell'applicazione per includere assembly percorsi noti, invece di duplicare le impostazioni di configurazione di assembly.

> [!NOTE]
> Il  **\<linkedConfiguration >** elemento non è supportato per le applicazioni con i manifesti side-by-side di Windows.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come includere un file di configurazione sul disco rigido locale:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- [Schema di file di configurazione per .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
