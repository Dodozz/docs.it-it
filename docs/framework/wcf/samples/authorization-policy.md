---
title: Criteri di autorizzazione
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: 87deedb2bd28cd86619eb48d0ff9c3e566174d31
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332676"
---
# <a name="authorization-policy"></a>Criteri di autorizzazione

In questo esempio viene illustrato come implementare i criteri di autorizzazione dell'attestazione personalizzati e un gestore autorizzazioni personalizzato del servizio associato. Questa procedura è utile quando il servizio esegue i controlli di accesso basati sull'attestazione nelle operazioni del servizio e prima dei controlli di accesso, concede al chiamante alcuni diritti. In questo esempio viene illustrato sia il processo di aggiunta delle attestazioni che il processo di controllo dell'accesso a fronte del set finalizzato di attestazioni. Tutti i messaggi dell'applicazione tra il client e il server vengono firmati e crittografati. Per impostazione predefinita, con l'associazione `wsHttpBinding` vengono utilizzati un nome utente e una password forniti dal client per accedere con un account Windows NT valido. In questo esempio viene illustrato come utilizzare un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizzato per autenticare il client. Viene inoltre illustrata l'autenticazione del client nel servizio tramite un certificato X.509. In questo esempio viene illustrata un'implementazione di <xref:System.IdentityModel.Policy.IAuthorizationPolicy> e <xref:System.ServiceModel.ServiceAuthorizationManager> che, insieme, concedono l'accesso a metodi specifici del servizio per utenti specifici. In questo esempio si basa sul [sicurezza messaggi tramite nome utente](../../../../docs/framework/wcf/samples/message-security-user-name.md), ma viene illustrato come eseguire una trasformazione delle attestazioni nelle versioni precedenti al <xref:System.ServiceModel.ServiceAuthorizationManager> chiamato.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

 In sintesi, nell'esempio viene illustrato in che modo eseguire le operazioni seguenti:

-   Il client può essere autenticato utilizzando un nome utente e una password.

-   Il client può essere autenticato tramite un certificato X.509.

-   Il server verifica le credenziali client rispetto a un validator `UsernamePassword` personalizzato.

-   Il server viene autenticato tramite il certificato X.509 del server.

-   Il server può utilizzare <xref:System.ServiceModel.ServiceAuthorizationManager> per controllare l'accesso a determinati metodi nel servizio.

-   Come implementare <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.

Il servizio espone due endpoint per comunicare con il servizio definito mediante il file di configurazione App.config. Ciascun endpoint è costituito da un indirizzo, un binding e un contratto. Un'associazione è configurata con un'associazione `wsHttpBinding` standard che utilizza WS-Security e l'autenticazione del nome utente del client. L'altra associazione è configurata con un'associazione `wsHttpBinding` standard che utilizza WS-Security e l'autenticazione del certificato client. Il [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) specifica che le credenziali dell'utente da utilizzare per l'autenticazione del servizio. Il certificato del server deve contenere lo stesso valore per il `SubjectName` proprietà come il `findValue` attributo il [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <!-- configure base address provided by host -->
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>
        </baseAddresses>
      </host>
      <!-- use base address provided by host, provide two endpoints -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <endpoint address="certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding2"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
    <message clientCredentialType="UserName" />
        </security>
      </binding>
      <!-- X509 certificate binding -->
      <binding name="Binding2">
        <security mode="Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior" >
        <serviceDebug includeExceptionDetailInFaults ="true" />
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.
          -->
          <clientCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
          <!--
          The serviceAuthorization behavior allows one to specify custom authorization policies.
          -->
          <authorizationPolicies>
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />
          </authorizationPolicies>
        </serviceAuthorization>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

Ogni configurazione dell'endpoint client è costituita da un nome di configurazione, un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto. L'associazione client viene configurata con la modalità di sicurezza appropriato come specificato in questo caso nel [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) e `clientCredentialType` come specificato nella [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
            address="http://localhost:8001/servicemodelsamples/service/username"
    binding="wsHttpBinding"
    bindingConfiguration="Binding1"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" >
      </endpoint>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
                        address="http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
            bindingConfiguration="Binding2"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
        <!-- X509 certificate binding -->
        <binding name="Binding2">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
    </wsHttpBinding>
    </bindings>

    <behaviors>
      <behavior name="ClientCertificateBehavior">
        <clientCredentials>
          <serviceCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust
            means that if the certificate
            is in the user's Trusted People store, then it will be
            trusted without performing a
            validation of the certificate's issuer chain. This setting
            is used here for convenience so that the
            sample can be run without having to have certificates
            issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust.
            The security implications of this
            setting should be carefully considered before using
            PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode = "PeerOrChainTrust" />
          </serviceCertificate>
        </clientCredentials>
      </behavior>
    </behaviors>

  </system.serviceModel>
```

Per l'endpoint basato sul nome utente, l'implementazione client imposta il nome utente la e password da utilizzare.

```csharp
// Create a client with Username endpoint configuration
CalculatorClient client1 = new CalculatorClient("Username");

client1.ClientCredentials.UserName.UserName = "test1";
client1.ClientCredentials.UserName.Password = "1tset";

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client1.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client1.Close();
```

Per l'endpoint basato sul certificato, l'implementazione client imposta il certificato client da utilizzare.

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client2 = new CalculatorClient("Certificate");

client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client2.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client2.Close();
```

In questo esempio viene utilizzato un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizzato per convalidare i nomi utente e le password. Nell'esempio viene implementato `MyCustomUserNamePasswordValidator`, derivato da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. Per ulteriori informazioni, vedere la documentazione relativa a <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. Allo scopo di illustrare l'integrazione con <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, in questo esempio di validator personalizzato viene implementato il metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> per accettare coppie di nome utente/password quando il nome utente corrisponde alla password come mostrato nel codice seguente.

```csharp
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator
{
  // This method validates users. It allows in two users,
  // test1 and test2 with passwords 1tset and 2tset respectively.
  // This code is for illustration purposes only and
  // MUST NOT be used in a production environment because it
  // is NOT secure.
  public override void Validate(string userName, string password)
  {
    if (null == userName || null == password)
    {
      throw new ArgumentNullException();
    }

    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
    {
      throw new SecurityTokenException("Unknown Username or Password");
    }
  }
}
```

Quando il validator è stato implementato nel codice del servizio, l'host del servizio deve essere informato dell'istanza del validator da utilizzare. Questa operazione viene eseguita usando il codice seguente:

```csharp
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();
```

In alternativa, è possibile eseguire la stessa operazione nella configurazione:

```xml
<behavior ...>
    <serviceCredentials>
      <!--
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
      -->
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
    ...
    </serviceCredentials>
</behavior>
```

Windows Communication Foundation (WCF) offre un modello dettagliato basato sulle attestazioni per l'esecuzione di controlli di accesso. L'oggetto <xref:System.ServiceModel.ServiceAuthorizationManager> viene utilizzato per eseguire il controllo dell'accesso e determinare se le attestazioni associate al client soddisfano i requisiti necessari per accedere al metodo del servizio.

Ai fini della dimostrazione, in questo esempio viene illustrata un'implementazione di <xref:System.ServiceModel.ServiceAuthorizationManager> che implementa le <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> metodo per consentire l'accesso dell'utente ai metodi basate sulle attestazioni di tipo `http://example.com/claims/allowedoperation` il cui valore è l'URI di azione dell'operazione che è può essere chiamato.

```csharp
public class MyServiceAuthorizationManager : ServiceAuthorizationManager
{
  protected override bool CheckAccessCore(OperationContext operationContext)
  {
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;
    Console.WriteLine("action: {0}", action);
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)
    {
      if ( cs.Issuer == ClaimSet.System )
      {
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))
        {
          Console.WriteLine("resource: {0}", c.Resource.ToString());
          if (action == c.Resource.ToString())
            return true;
        }
      }
    }
    return false;
  }
}
```

Quando il <xref:System.ServiceModel.ServiceAuthorizationManager> personalizzato è stato implementato, l'host del servizio deve essere informato del <xref:System.ServiceModel.ServiceAuthorizationManager> da utilizzare. Questa operazione viene eseguita come mostrato nel codice seguente.

```xml
<behavior ...>
    ...
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
        ...
    </serviceAuthorization>
</behavior>
```

Il metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy> principale da implementare è il metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>.

```csharp
public class MyAuthorizationPolicy : IAuthorizationPolicy
{
    string id;

    public MyAuthorizationPolicy()
    {
    id =  Guid.NewGuid().ToString();
    }

    public bool Evaluate(EvaluationContext evaluationContext,
                                            ref object state)
    {
        bool bRet = false;
        CustomAuthState customstate = null;

        if (state == null)
        {
            customstate = new CustomAuthState();
            state = customstate;
        }
        else
            customstate = (CustomAuthState)state;
        Console.WriteLine("In Evaluate");
        if (!customstate.ClaimsAdded)
        {
           IList<Claim> claims = new List<Claim>();

           foreach (ClaimSet cs in evaluationContext.ClaimSets)
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,
                                         Rights.PossessProperty))
                  foreach (string s in
                        GetAllowedOpList(c.Resource.ToString()))
                  {
                       claims.Add(new
               Claim("http://example.com/claims/allowedoperation",
                                    s, Rights.PossessProperty));
                            Console.WriteLine("Claim added {0}", s);
                      }
                   evaluationContext.AddClaimSet(this,
                           new DefaultClaimSet(this.Issuer,claims));
                   customstate.ClaimsAdded = true;
                   bRet = true;
                }
         else
         {
              bRet = true;
         }
         return bRet;
     }
...
}
```

Il codice precedente mostra come il metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> controlla che non sia stata aggiunta nessuna nuova attestazione che influisce sull'elaborazione e aggiunge attestazioni specifiche. Le attestazioni consentite vengono ottenute dal metodo `GetAllowedOpList`, implementato per restituire un elenco specifico di operazioni che l'utente può eseguire. I criteri di autorizzazione aggiungono attestazioni per l'accesso alla specifica operazione. Tale accesso verrà utilizzato in un secondo momento da <xref:System.ServiceModel.ServiceAuthorizationManager> per effettuare scelte in relazione al controllo dell'accesso.

Quando l'interfaccia <xref:System.IdentityModel.Policy.IAuthorizationPolicy> personalizzata è stata implementata, l'host del servizio deve essere informato dei criteri di autorizzazione da utilizzare.

```xml
<serviceAuthorization ...>
       <authorizationPolicies>
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />
       </authorizationPolicies>
</serviceAuthorization>
```

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Il client chiama correttamente i metodi Add, Subtract e Multiple e ottiene un messaggio "Accesso negato" quando tenta di chiamare il metodo Divide. Premere INVIO nella finestra del client per arrestare il client.

## <a name="setup-batch-file"></a>File batch di installazione

Il file batch Setup.bat incluso in questo esempio consente di configurare il server con i certificati attinenti per eseguire un'applicazione indipendente che richiede la sicurezza server basata su certificato.

Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.

-   Creazione del certificato server.

     Le righe seguenti del file batch Setup.bat creano il certificato server da usare. La variabile %SERVER_NAME% specifica il nome del server. Modificare questa variabile per specificare nome del server. Il valore predefinito è localhost.

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

-   Installazione del certificato server nell'archivio certificati attendibili del client

     Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client. Questo passaggio è necessario perché i certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client. Se è già disponibile un certificato con radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio del popolamento dell'archivio certificati client con il certificato server non è necessario.

    ```
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

-   Creazione del certificato del client.

     Le righe seguenti del file batch Setup.bat creano il certificato client da utilizzare. La variabile %USER_NAME% specifica il nome del server. Questo valore è impostato su "test1" perché questo è il nome cercato da `IAuthorizationPolicy`. Se si modifica il valore di %USER_NAME%, è necessario modificare il valore corrispondente nel metodo `IAuthorizationPolicy.Evaluate`.

     Il certificato viene memorizzato nell'archivio personale nel percorso di archivio CurrentUser.

    ```
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

-   Installazione del certificato client nell'archivio certificati attendibili del server

     Le righe seguenti nel file batch Setup.bat copiano il certificato client nell'archivio delle persone attendibile. Questo passaggio è necessario perché i certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema del server. Se è già disponibile un certificato che è impostato come radice in un certificato radice attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio della popolazione dell'archivio certificati server con il certificato client non è necessario.

    ```
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

### <a name="to-set-up-and-build-the-sample"></a>Per impostare e compilare l'esempio

1. Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

2. Per eseguire l'esempio su un solo computer o tra computer diversi, seguire le istruzioni indicate di seguito.

> [!NOTE]
> Se si usa Svcutil.exe per rigenerare la configurazione di questo esempio, assicurarsi di modificare il nome dell'endpoint nella configurazione client in modo che corrisponda al codice client.

### <a name="to-run-the-sample-on-the-same-computer"></a>Per eseguire l'esempio nello stesso computer

1. Aprire il prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire *Setup. bat* dalla cartella di installazione dell'esempio. In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.

    > [!NOTE]
    > Il file batch Setup. bat è progettato per essere eseguito dal prompt dei comandi per gli sviluppatori per Visual Studio. Variabile di ambiente PATH impostata nel prompt dei comandi per gli sviluppatori per Visual Studio punti alla directory che contiene file eseguibili richiesti dal *Setup. bat* script.

1. Avviare Service.exe dal *service\bin*.

1. Avviare Client.exe dal *\client\bin*. L'attività del client viene visualizzata nella finestra dell'applicazione console.

  Se il client e il servizio non è in grado di comunicare, vedere [suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).

### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer

1. Creare una directory sul computer del servizio.

2. Copiare i file di programma servizio dalla *\service\bin* alla directory nel computer del servizio. Copiare inoltre i file Setup.bat, Cleanup.bat,GetComputerName.vbs e ImportClientCert.bat nel computer del servizio.

3. Creare una directory sul client del servizio per i file binari del client.

4. Copiare i file di programma del client nella directory del client sul computer relativo e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.

5. Nel server, eseguire `setup.bat service` nel prompt dei comandi sviluppatore per Visual Studio aperto con privilegi di amministratore.

   In esecuzione `setup.bat` con il `service` argomento consente di creare un certificato di servizio con il nome di dominio completo del computer e il certificato di servizio viene esportato in un file denominato *CER*.

6. Modificare *Service.exe.config* in modo da riflettere il nuovo nome del certificato (nelle `findValue` attributo il [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) che corrisponde al nome di dominio completo del computer. Modificare anche il **computername** nel \<service > /\<baseAddresses > elemento da localhost al nome completo del computer del servizio.

7. Copia il *CER* file dalla directory del servizio alla directory del client nel computer client.

8. Nel client, eseguire `setup.bat client` nel prompt dei comandi sviluppatore per Visual Studio aperto con privilegi di amministratore.

   In esecuzione `setup.bat` con il `client` argomento consente di creare un certificato client denominato **test1** e il certificato client viene esportato in un file denominato *CER*.

9. Nel *exe* file nel computer client, modificare il valore dell'indirizzo dell'endpoint affinché corrisponda al nuovo indirizzo del servizio. Eseguire questa operazione sostituendo **localhost** con il nome di dominio completo del server.

10. Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.

11. Nel client, eseguire *Importservicecert* nel prompt dei comandi sviluppatore per Visual Studio aperto con privilegi di amministratore.

   Questo modo viene importato il certificato del servizio dal file Service CER nel **CurrentUser - TrustedPeople** archiviare.

12. Nel server, eseguire *importclientcert. bat* nel prompt dei comandi sviluppatore per Visual Studio aperto con privilegi di amministratore.

   In questo modo il certificato client dal file client CER nel **LocalMachine - TrustedPeople** archiviare.

13. Sul computer server avviare Service.exe dalla finestra del prompt dei comandi.

14. Sul computer client avviare Client.exe da una finestra del prompt dei comandi.

   Se il client e il servizio non è in grado di comunicare, vedere [suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).

### <a name="clean-up-after-the-sample"></a>La pulizia dopo il codice di esempio

Per eseguire la pulizia dopo il codice di esempio, eseguire *Cleanup. bat* nella cartella degli esempi è terminata l'esecuzione dell'esempio. In questo modo i certificati server e client vengono rimossi dall'archivio certificati.

> [!NOTE]
> Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer. Se sono stati eseguiti esempi WCF che utilizzano certificati in più computer, assicurarsi di cancellare i certificati del servizio che sono stati installati in CurrentUser - TrustedPeople archiviare. A tale scopo, usare il comando seguente: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.