---
title: Elemento <system.web> (impostazioni Web)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b9a43c5f5141e364ab9aac1cfdff577a8fb8a161
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486673"
---
# <a name="systemweb-element-web-settings"></a>\<System. Web > (impostazioni Web)
Contiene informazioni su come il livello di hosting ASP.NET gestisce il comportamento a livello di processo.  
  
 \<configuration>  
\<System. Web > (impostazioni Web)  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Specifica le impostazioni di configurazione per i pool di applicazioni IIS in un file ASPNET config.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Specifica l'elemento radice in ogni file di configurazione che viene usato per il common language runtime e le applicazioni .NET Framework.|  
  
## <a name="remarks"></a>Note  
 Il `system.web` elemento e del relativo figlio `applicationPool` elemento sono stati aggiunti a .NET Framework a partire da .NET Framework 3.5 SP1. Quando si esegue IIS 7.0 o versioni successive in modalità integrata, questa combinazione di elementi consente di configurare come ASP.NET gestisce i thread e mette in coda le richieste quando ASP.NET è ospitato in un pool di applicazioni IIS. Se si esegue IIS 7.0 o versioni successive in modalità classica o di ISAPI, queste impostazioni vengono ignorate.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare il comportamento a livello di processo ASP.NET nel file Aspnet. config quando ASP.NET è ospitato in un pool di applicazioni IIS. Nell'esempio si presuppone che IIS sia in esecuzione in modalità integrata modalità e che l'applicazione usa .NET Framework 3.5 SP1 o versione successiva. Questo comportamento non viene eseguito nelle versioni di .NET Framework precedenti a .NET Framework 3.5 SP1. I valori nell'esempio sono i valori predefiniti.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Informazioni sull'elemento  
  
|||  
|-|-|  
|Spazio dei nomi||  
|Nome di schema||  
|File di convalida||  
|Può essere vuoto||  
  
## <a name="see-also"></a>Vedere anche

- [Elemento \<applicationPool> (impostazioni Web)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
