---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 5a4cf8d429198b889f2bb362294ba3841c814b26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788700"
---
# <a name="usernameauthentication"></a>\<userNameAuthentication>
Specifica le credenziali di un servizio in base a nome utente e password.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<userNameAuthentication>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<xref:System.TimeSpan> specifica il periodo massimo di tempo durante il quale un token è memorizzato nella cache. L'impostazione predefinita è 00:15:00.|  
|`cacheLogonTokens`|Valore booleano che specifica se i token di accesso vengono memorizzati nella cache. Il valore predefinito è `false`.|  
|`customUserNamePasswordValidatorType`|Stringa che specifica il tipo di convalida personalizzata della password nome utente da usare. Il valore predefinito è una stringa vuota.|  
|`includeWindowsGroups`|Valore booleano che specifica se i gruppi di Windows sono inclusi nel contesto di sicurezza. Il valore predefinito è `true`.<br /><br /> L'impostazione di questo attributo su `true` determina un effetto sulle prestazioni in quanto comporta un'espansione completa del gruppo. Impostare questa proprietà su `false` se non è necessario stabilire l'elenco di gruppi a cui appartiene un utente.|  
|`maxCacheLogonTokens`|Numero intero che specifica il numero massimo di token di accesso da memorizzare nella cache. Questo valore deve essere maggiore di zero. Il valore predefinito è 128.|  
|`membershipProviderName`|Quando l'attributo `clientCredentialType` di un'associazione viene impostato su `username`, viene eseguito il mapping del nome utente sugli account di Windows. È possibile eseguire l'override di questo comportamento usando questo attributo, il quale è una stringa che contiene il nome del valore <xref:System.Web.Security.MembershipProvider> che fornisce il meccanismo di convalida della password appropriato.|  
|`userNamePasswordValidationMode`|Specifica il modo in cui viene convalidata la password del nome utente. I valori validi sono:<br /><br /> -   Windows<br />-MembershipProvider<br />-Custom<br /><br /> L'impostazione predefinita è Windows. L'attributo è di tipo <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.|  
  
## <a name="remarks"></a>Note  
 Se nessuna delle associazioni usate da un servizio viene configurata per l'autenticazione basata su nome utente/password, gli attributi rilevanti per questo elemento vengono ignorate. Tali attributi includono `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` e `userNamePasswordValidationMode`.  
  
 Se nessuna delle associazioni usate da un servizio viene configurata per usare l'autenticazione di Windows per nome utente/password, le impostazioni relative alla memorizzazione nella cache dei token di accesso vengono ignorate. Tali impostazioni includono `cacheLogonTokenLifetime`, `cacheLogonTokens` e `maxCacheLogonTokens`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
