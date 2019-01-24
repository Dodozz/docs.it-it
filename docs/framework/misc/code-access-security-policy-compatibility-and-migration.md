---
title: Migrazione e compatibilità dei criteri di sicurezza dall'accesso di codice
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR poliicy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 219b511662a2e59fb6e0e55b6630bd54015fcc79
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620097"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a>Migrazione e compatibilità dei criteri di sicurezza dall'accesso di codice
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Gli aspetti relativi ai criteri di sicurezza dall'accesso di codice sono diventati obsoleti a partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]. Di conseguenza, potrebbero verificarsi avvisi di compilazione ed eccezioni di runtime se si chiamano i membri e tipi dei criteri obsoleti [in modo esplicito](#explicit_use) oppure [implicitamente](#implicit_use) (tramite altri tipi e membri).  
  
 È possibile evitare gli avvisi e gli errori nei modi seguenti:  
  
-   [Eseguire la migrazione](#migration) per il [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] sostituzioni per le chiamate obsolete.  
  
     \- oppure -  
  
-   Usando il [elemento di configurazione < NetFx40_LegacySecurityPolicy >](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) per acconsentire esplicitamente il comportamento dei criteri di criteri.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Uso esplicito](#explicit_use)  
  
-   [Uso implicito](#implicit_use)  
  
-   [Errori e avvisi](#errors_and_warnings)  
  
-   [Migrazione: Sostituzione delle chiamate Obsolete](#migration)  
  
-   [Compatibilità: Usando l'opzione Legacy relativa ai criteri CAS](#compatibility)  
  
<a name="explicit_use"></a>   
## <a name="explicit-use"></a>Uso esplicito  
 I membri che modificano direttamente i criteri di sicurezza o richiedono criteri di sicurezza dall'accesso di codice per il sandboxing sono obsoleti e comportano la generazione di errori per impostazione predefinita.  
  
 Di seguito vengono forniti alcuni esempi:  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>  
  
<a name="implicit_use"></a>   
## <a name="implicit-use"></a>Uso implicito  
 Numerosi assembly che caricano overload producono errori a causa dell'uso implicito di criteri di sicurezza dall'accesso di codice. Questi overload accettano un parametro <xref:System.Security.Policy.Evidence> usato per risolvere i criteri di sicurezza dall'accesso di codice e forniscono un set di autorizzazioni per un assembly.  
  
 Ecco alcuni esempi. Gli overload obsoleti sono quelli che accettano <xref:System.Security.Policy.Evidence> come parametro:  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
<a name="errors_and_warnings"></a>   
## <a name="errors-and-warnings"></a>Errori e avvisi  
 Quando vengono usati, i tipi e i membri obsoleti producono i messaggi di errore seguenti. Si noti che il tipo <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> non è obsoleto.  
  
 Avviso in fase di compilazione:  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`  
  
 Eccezioni di runtime:  
  
 <xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`  
  
<a name="migration"></a>   
## <a name="migration-replacement-for-obsolete-calls"></a>Migrazione: Sostituzione delle chiamate Obsolete  
  
### <a name="determining-an-assemblys-trust-level"></a>Determinazione del livello di attendibilità di un assembly  
 I criteri di sicurezza dall'accesso di codice vengono spesso usati per determinare il livello di attendibilità o il set di autorizzazioni di un assembly o di un dominio dell'applicazione. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] espone le utili proprietà seguenti, che non richiedono la risoluzione dei criteri di sicurezza:  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
### <a name="application-domain-sandboxing"></a>Sandboxing di un dominio dell'applicazione  
 Il metodo <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> viene in genere usato per il sandboxing degli assembly in un dominio dell'applicazione. Il [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] espone membri che non sono necessario usare <xref:System.Security.Policy.PolicyLevel> per questo scopo. Per altre informazioni, vedere [Procedura: Eseguire codice parzialmente attendibile in un ambiente Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).  
  
### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a>Determinazione di un set di autorizzazioni ragionevoli o sicure per codice parzialmente attendibile  
 Gli host devono spesso determinare le autorizzazioni appropriate per il sandboxing del codice ospitato. Prima la [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], il criterio CAS fornito un modo per eseguire questa operazione con il <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> (metodo). Rappresenta un sostituto [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] fornisce il <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> metodo, che restituisce un'autorizzazione provvisoria, standard, impostato per l'evidenza fornita.  
  
### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a>Scenari senza Sandboxing: Overload per caricamenti di Assembly  
 Il motivo per usare un overload per il caricamento di un assembly potrebbe essere l'uso di parametri che non sono altrimenti disponibili, anziché l'esecuzione del sandboxing dell'assembly. Inizia con la [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], gli overload di caricamento di assembly che non richiedono una <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> oggetto come parametro, ad esempio, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, abilitare questo scenario.  
  
 Per eseguire il sandboxing di un assembly, usare l'overload <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType>.  
  
<a name="compatibility"></a>   
## <a name="compatibility-using-the-cas-policy-legacy-option"></a>Compatibilità: Usando l'opzione Legacy relativa ai criteri CAS  
 Il [elemento di configurazione < NetFx40_LegacySecurityPolicy >](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) consente di specificare che un processo o la libreria Usa criteri CAS legacy. Quando si abilita questo elemento, gli overload relativi ai criteri e all'evidenza funzionano in modo analogo a quanto avveniva nelle versioni precedenti del framework.  
  
> [!NOTE]
>  Il comportamento dei criteri di sicurezza dall'accesso di codice viene specificato per ogni versione runtime, pertanto la modifica di questi criteri per una versione runtime non influisce sui criteri di sicurezza dall'accesso di codice di un'altra versione.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Eseguire codice parzialmente attendibile in un oggetto Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Linee guida per la generazione di codice sicuro](../../standard/security/secure-coding-guidelines.md)
