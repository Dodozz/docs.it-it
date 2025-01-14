---
title: <httpDigest> Elemento
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 914711e4d6c3dbb1ccc741af1b3abd6b8de716a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751046"
---
# <a name="httpdigest-element"></a>\<httpDigest > elemento
Specifica una credenziale di tipo digest usata per autenticare il client presso un servizio.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<clientCredentials>  
\<httpDigest>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`impersonationLevel`|Imposta la preferenza di rappresentazione che il client comunica al server. La modalità di rappresentazione selezionata dal client non viene imposta sul server. Di seguito vengono elencati i valori validi:<br /><br /> -Identificazione: Il server può ottenere l'identità e i privilegi del client, ma non può rappresentare il client.<br />-Rappresentazione: Il server può rappresentare il contesto di sicurezza del client nel sistema locale.<br />-Delega: Il server può rappresentare il contesto di sicurezza del client nei sistemi remoti.<br />-Anonimo: Il server non può rappresentare o identificare il client.<br />-None: Non è assegnato un livello di rappresentazione.<br /><br /> L'impostazione predefinita è Identification. L'attributo è di tipo <xref:System.Security.Principal.TokenImpersonationLevel>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Specifica le credenziali usate per autenticare un client presso un servizio.|  
  
## <a name="remarks"></a>Note  
 Un digest è un hash determinato mediante un algoritmo e un insieme di input. L'autenticatore e l'autenticato concordano un algoritmo e scambiamo i dati usati come input. Il client può calcolare l'hash e inviarlo al servizio. Il servizio calcola anche l'hash e confronta i valori. Una corrispondenza convalida il client.  
  
 Questa funzionalità deve essere abilitata con Active Directory in Windows e Internet Information Services (IIS). Per altre informazioni, vedere [l'autenticazione del Digest in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Protezione di client](../../../../../docs/framework/wcf/securing-clients.md)
- [Uso di certificati](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
