---
title: 'Procedura: Usare un nome utente personalizzato e il Validator della Password'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 619d3e80a8206ae3ceef2d7ff822dc3bfa8f65be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700533"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>Procedura: Usare un nome utente personalizzato e il Validator della Password
Per impostazione predefinita, quando viene utilizzato un nome utente e una password per l'autenticazione, Windows Communication Foundation (WCF) viene utilizzato Windows per convalidare il nome utente e password. Tuttavia, WCF consente agli utente personalizzata nome e una password schemi di autenticazione, noto anche come *validator*. Per incorporare un validator personalizzato di nome utente e password, creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> e configurarla.  
  
 Per un'applicazione di esempio, vedere [Validator nome utente e Password](../../../../docs/framework/wcf/samples/user-name-password-validator.md).  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a>Per creare un validator di nome utente e password personalizzato  
  
1.  Creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  Implementare lo schema di autenticazione personalizzato eseguendo l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     Non utilizzare il codice contenuto nell'esempio seguente, che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, in un ambiente di produzione. Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.  
  
     Affinché gli errori di autenticazione vengano restituiti al client, generare una classe <xref:System.ServiceModel.FaultException> nel metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>Per configurare un servizio per l'utilizzo di un validator di nome utente e password personalizzato  
  
1.  Configurare un'associazione che utilizza meccanismi di sicurezza a livello di messaggio su qualsiasi trasporto o meccanismi di sicurezza a livello di trasporto su HTTP(S).  
  
     Quando si usa la sicurezza dei messaggi, aggiungere una delle associazioni fornite dal sistema, ad esempio un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), o un' [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) che supporta la sicurezza dei messaggi e il `UserName` il tipo di credenziale.  
  
     Quando si usa la sicurezza a livello di trasporto su HTTP (S), aggiungere il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) oppure [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)un [ \< netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) o un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) che utilizza HTTP (S) e il `Basic` lo schema di autenticazione.  
  
    > [!NOTE]
    >  Quando si utilizza [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] o versioni successive, è possibile utilizzare un validator di nome utente e password personalizzato con modalità di sicurezza dei messaggi e del trasporto. Quando si utilizza [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], un validator di nome utente e password personalizzato può essere utilizzato solo con la modalità di sicurezza dei messaggi.  
  
    > [!TIP]
    >  Per altre informazioni sull'uso \<netTcpBinding > in questo contesto, vedere [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
  
    1.  Nel file di configurazione, sotto il [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.  
  
    2.  Aggiungere un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) oppure [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento alla sezione delle associazioni. Per altre informazioni sulla creazione di un elemento di binding WCF, vedere [come: Specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
    3.  Impostare il `mode` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) a `Message`, `Transport`, o `TransportWithMessageCredential`.  
  
    4.  Impostare il `clientCredentialType` attributo del [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) oppure [ \<trasporto >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).  
  
         Quando si utilizza la sicurezza dei messaggi, impostare il `clientCredentialType` attributo del [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) a `UserName`.  
  
         Quando si utilizza la sicurezza a livello di trasporto su HTTP (S), impostare il `clientCredentialType` attributo del [ \<trasporto >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) o [ \<trasporto >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) a `Basic`.  
  
        > [!NOTE]
        >  Quando un servizio WCF è ospitato in Internet Information Services (IIS) utilizzando la sicurezza a livello di trasporto e il <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> è impostata su <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, lo schema di autenticazione personalizzato utilizza un subset dell'autenticazione di Windows. Questo avviene perché in questo scenario IIS esegue l'autenticazione di Windows prima di WCF richiamando l'autenticatore personalizzato.  
  
     Per altre informazioni sulla creazione di un elemento di binding WCF, vedere [come: Specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
     Nell'esempio seguente viene illustrato il codice di configurazione per l'associazione.  
  
    ```xml  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2.  Configurare un comportamento che specifica che un validator personalizzato di nome utente e password viene utilizzato per convalidare coppie di nome utente e password per i token di sicurezza <xref:System.IdentityModel.Tokens.UserNameSecurityToken> in arrivo.  
  
    1.  Come elemento figlio per il [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.  
  
    2.  Aggiungere un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per il [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.  
  
    3.  Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) e impostare il `name` attributo su un valore appropriato.  
  
    4.  Aggiungere un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) per il [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento.  
  
    5.  Aggiungere un [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) per il [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
    6.  Impostare `userNamePasswordValidationMode` su `Custom`.  
  
        > [!IMPORTANT]
        >  Se il `userNamePasswordValidationMode` valore non è impostato, WCF Usa l'autenticazione di Windows anziché il validator di nome e una password utente personalizzata.  
  
    7.  Impostare `customUserNamePasswordValidatorType` sul tipo che rappresenta il validator personalizzato di nome utente e password.  
  
     Nell'esempio seguente viene illustrato il frammento `<serviceCredentials>` fino a questo punto.  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a>Esempio  
 Nel codice di esempio seguente viene dimostrato come creare un validator personalizzato di nome utente e password. Non utilizzare il codice che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> in un ambiente di produzione. Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [Procedura: Usare il Provider di appartenenze ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [Autenticazione](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
