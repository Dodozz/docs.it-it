---
title: Crittografia di firme digitali
ms.date: 03/30/2017
helpviewer_keywords:
- encryption of digital signatures [WCF]
- digital signatures [WCF], encryption
- digital signatures [WCF]
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
ms.openlocfilehash: ea53a575802f1e7903a66c2eda466c8937fb02f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341595"
---
# <a name="encryption-of-digital-signatures"></a>Crittografia di firme digitali
Per impostazione predefinita, un messaggio viene firmato e crittografato e la firma viene crittografata digitalmente. È possibile controllare questo comportamento creando un'associazione personalizzata con un'istanza della classe <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e quindi impostando la proprietà `MessageProtectionOrder` della classe su un valore dell'enumerazione <xref:System.ServiceModel.Security.MessageProtectionOrder>. Il valore predefinito è <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Questo processo richiede un tempo superiore dal 10 al 40 percento rispetto alla semplice firma e crittografia. La disattivazione della crittografia della firma può tuttavia consentire all'autore di un attacco di individuare il contenuto del messaggio, poiché l'elemento di firma contiene il codice hash del testo normale di ogni parte firmata del messaggio. Ad esempio, anche se il corpo del messaggio è crittografato per impostazione predefinita, la firma non crittografata contiene il codice hash del corpo del messaggio. Se il messaggio è di piccole dimensioni, l'autore dell'attacco potrebbe essere in grado di dedurre il contenuto. Con la crittografia della firma si riduce o si elimina questa possibilità.  
  
 Disattivare pertanto la crittografia della firma solo quando il valore del contenuto è basso e il miglioramento delle prestazioni sarà significativo, ad esempio in caso di invio di file binari di grandi dimensioni senza implicazioni di sicurezza.  
  
### <a name="to-disable-digital-signing"></a>Per disattivare la firma digitale  
  
1. Creare un oggetto <xref:System.ServiceModel.Channels.CustomBinding>. Per altre informazioni, vedere [Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2. Aggiungere un elemento <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> alla raccolta di associazioni.  
  
3. Impostare la proprietà <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> oppure impostare la proprietà <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.  
  
 Per altre informazioni sulla creazione di associazioni personalizzate, vedere [associazioni Creating User-Defined](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md). Per altre informazioni sulla creazione di un'associazione personalizzata per una modalità di autenticazione specifica, vedere [come: Creare un elemento SecurityBindingElement per una modalità di autenticazione specificato](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Security.MessageProtectionOrder>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- [Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Creazione di associazioni definite dall'utente](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)
- [Procedura: Creare un elemento SecurityBindingElement per una modalità di autenticazione specificata](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
