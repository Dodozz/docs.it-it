---
title: Elemento <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 236ae880fff24f7ccbf5d6c9c03c0208d446688f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704414"
---
# <a name="claimtyperequirements-element"></a>\<claimTypeRequirements > elemento
Specifica una raccolta di tipi di attestazione obbligatori.  
  
 In un scenario federato, i servizi attestano i requisiti per le credenziali in ingresso. Ad esempio, le credenziali in ingresso devono disporre di un certo set di tipi di attestazioni. Ogni elemento figlio di questa raccolta specifica i tipi di attestazione obbligatori e facoltativi previsti in una credenziale federata.  
  
 Un requisito del tipo di attestazione è costituito da un URI del tipo di attestazione necessario nel token rilasciato e da un parametro booleano che indica se il tipo attestazione specifico è necessario nel token rilasciato o è facoltativo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Funzionalità di sicurezza con associazioni personalizzate](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Sicurezza delle associazioni personalizzate](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
