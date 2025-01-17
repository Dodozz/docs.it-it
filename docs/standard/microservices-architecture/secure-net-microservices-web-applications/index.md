---
title: Protezione di microservizi e applicazioni Web .NET
description: Protezione di microservizi e applicazioni Web .NET - Informazioni sulle opzioni di autenticazione per le applicazioni Web ASP.NET Core.
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: 0894465858e3503e2eddb5299b404f7ba95fdd6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62019691"
---
# <a name="make-secure-net-microservices-and-web-applications"></a>Proteggere i microservizi e le applicazioni Web .NET

La protezione dei microservizi e delle applicazioni Web è un argomento molto vasto e con un gran numero di aspetti diversi. Questa sezione si concentra sull'autenticazione, l'autorizzazione e i segreti dell'applicazione.

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a>Implementare l'autenticazione in microservizi e applicazioni Web .NET

In molti casi è necessario che le risorse e le API pubblicate da un servizio siano limitate a determinati utenti o client attendibili. Il primo passaggio per prendere questo tipo di decisioni sull'attendibilità a livello di API è l'autenticazione. L'autenticazione è il processo con il quale si verifica in modo affidabile l'identità di un utente.

In scenari con microservizi, l'autenticazione viene in genere gestita a livello centrale. Se si usa un gateway API il gateway è un ottimo strumento per l'autenticazione, come illustrato nella figura 9-1. Se si usa questo approccio, assicurarsi che i singoli microservizi non possano essere raggiunti direttamente (senza il gateway API), a meno che non sia presente un sistema di sicurezza aggiuntivo per autenticare i messaggi, indipendentemente dal fatto che provengano dal gateway.

![Quando il gateway API centralizza l'autenticazione, aggiunge le informazioni utente al momento dell'inoltro delle richieste ai microservizi.](./media/image1.png)

**Figura 9-1**. Autenticazione centralizzata con un gateway API

Se è possibile accedere direttamente ai servizi, per autenticare gli utenti è possibile usare un servizio di autenticazione come Azure Active Directory o un microservizio di autenticazione dedicato con funzione di servizio token di sicurezza. Le decisioni sull'attendibilità vengono condivise tra i servizi con i token di sicurezza o i cookie. (Questi token possono essere condivisi tra le applicazioni ASP.NET Core, se necessario, implementando la [condivisione dei cookie](/aspnet/core/security/cookie-sharing).) Questo scenario è illustrato nella figura 9-2.

![Quando l'accesso ai i microservizi è diretto, l'attendibilità, che include autenticazione e autorizzazione, viene gestita da un token di sicurezza emesso da un microservizio dedicato, condiviso tra i microservizi.](./media/image2.png)

**Figura 9-2**. Autenticazione mediante microservizio di identità; l'attendibilità è condivisa con un token di autorizzazione

### <a name="authenticate-with-aspnet-core-identity"></a>Autenticazione tramite ASP.NET Core Identity

Il meccanismo principale in ASP.NET Core per identificare gli utenti di un'applicazione è il sistema di appartenenze [ASP.NET Core Identity](/aspnet/core/security/authentication/identity). ASP.NET Core Identity archivia informazioni sugli utenti (comprese le informazioni di accesso, i ruoli e le attestazioni) in un archivio dati configurato dallo sviluppatore. In genere l'archivio dati di ASP.NET Core Identity è un archivio Entity Framework incluso nel pacchetto `Microsoft.AspNetCore.Identity.EntityFrameworkCore`. È tuttavia possibile usare archivi personalizzati o altri pacchetti di terze parti per archiviare le informazioni sull'identità in Archiviazione tabelle di Azure, in CosmosDB o in altre posizioni.

Il codice seguente proviene dal modello di progetto applicazione Web di ASP.NET Core con l'autenticazione dell'account utente singolo selezionata. Illustra come configurare ASP.NET Core Identity tramite EntityFramework.Core nel metodo Startup.ConfigureServices.

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

Dopo la configurazione, ASP.NET Core Identity può essere abilitato chiamando app.UseIdentity nel metodo `Startup.Configure` del servizio.

L'uso di ASP.NET Core Identity consente diversi scenari:

- Creazione di nuove informazioni utente usando il tipo UserManager (userManager.CreateAsync).

- Autenticazione degli utenti tramite il tipo SignInManager. È possibile usare `signInManager.SignInAsync` per l'accesso diretto o `signInManager.PasswordSignInAsync` per confermare che la password dell'utente sia corretta e quindi consentire l'accesso.

- Identificazione di un utente in base alle informazioni archiviate in un cookie (che viene letto dal middleware di ASP.NET Core Identity) in modo che le successive richieste provenienti da un browser includeranno l'identità e le attestazioni dell'utente connesso.

ASP.NET Core Identity supporta inoltre l'[autenticazione a due fattori](/aspnet/core/security/authentication/2fa).

Per scenari di autenticazione che usano dell'archivio dati degli utenti locale e vengono salvano in modo permanente l'identità tra le richieste tramite dei cookie (come avviene per le applicazioni web MVC), ASP.NET Identity Core è una soluzione consigliata.

### <a name="authenticate-with-external-providers"></a>Eseguire l'autenticazione tramite provider esterni

ASP.NET Core supporta anche l'uso di [provider di autenticazione esterni](/aspnet/core/security/authentication/social/) per consentire agli utenti di accedere tramite flussi di [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2). Ciò significa che gli utenti possono accedere con processi di autenticazione esistenti di provider come Microsoft, Google, Facebook o Twitter e associare queste identità a un'identità di ASP.NET Core nell'applicazione.

Per usare l'autenticazione esterna, includere il middleware di autenticazione appropriato nella pipeline di elaborazione della richiesta HTTP dell'applicazione. Questo middleware è responsabile della gestione delle richieste di route URI dal provider di autenticazione, dell'acquisizione di informazioni di identità e della messa a disponibile delle stesse tramite il metodo SignInManager.GetExternalLoginInfo.

Alcuni provider di autenticazione esterni comuni e i pacchetti NuGet associati sono elencati nella tabella seguente:

| **Provider**  | **Pacchetto**                                          |
| ------------- | ---------------------------------------------------- |
| **Microsoft** | **Microsoft.AspNetCore.Authentication.MicrosoftAccount** |
| **Google**    | **Microsoft.AspNetCore.Authentication.Google**           |
| **Facebook**  | **Microsoft.AspNetCore.Authentication.Facebook**         |
| **Twitter**   | **Microsoft.AspNetCore.Authentication.Twitter**          |

In tutti i casi il middleware è registrato con una chiamata a un metodo di registrazione simile a `app.Use{ExternalProvider}Authentication` in `Startup.Configure`. Questi metodi di registrazione accettano un oggetto di opzioni che contiene un ID applicazione e informazioni segrete (una password, ad esempio), in base alle esigenze dal provider. I provider di autenticazione esterni richiedono la registrazione dell'applicazione (come spiegato nella [documentazione di ASP.NET Core](/aspnet/core/security/authentication/social/)) per poter informare l'utente di quale applicazione richiede l'accesso alla sua identità.

Dopo la registrazione del middleware in `Startup.Configure` è possibile richiedere agli utenti di accedere da qualsiasi azione del controller. Per fare ciò si crea un oggetto `AuthenticationProperties` che include il nome del provider di autenticazione e un URL di reindirizzamento. È quindi possibile restituire una risposta Challenge che passa l'oggetto `AuthenticationProperties`. Nel codice seguente viene illustrato un esempio.

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

Il parametro redirectUrl include l'URL a cui il provider esterno deve reindirizzare l'utente dopo l'autenticazione. L'URL deve rappresentare un'azione che connetterà l'utente in base alle informazioni di identità esterne, come nell'esempio semplificato seguente:

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

Se quando si crea il progetto di applicazione Web ASP.NET Code in Visual Studio si sceglie l'opzione di autenticazione **Account utente individuali**, tutto il codice necessario per l'accesso con un provider esterno è già presente nel progetto, come illustrato nella figura 9-3.

![Finestra di dialogo per la nuova applicazione Web ASP.NET Core, con il pulsante di modifica dell'autenticazione evidenziato.](./media/image3.png)

**Figura 9-3**. Selezione di un'opzione per l'uso dell'autenticazione esterna quando si crea un progetto di applicazione Web

Oltre all'autenticazione esterna dei provider elencati in precedenza, sono disponibili pacchetti di terze parti che forniscono middleware per l'uso di molti altri provider di autenticazione esterni. Per un elenco, vedere il repository [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) in GitHub.

È anche possibile creare middleware di autenticazione esterna personalizzato per risolvere esigenze particolari.

### <a name="authenticate-with-bearer-tokens"></a>Eseguire l'autenticazione con bearer token

L'autenticazione con ASP.NET Core Identity (o Identity più provider di autenticazione esterni) funziona bene per molti scenari di applicazioni Web in cui è appropriato archiviare le informazioni dell'utente in un cookie. In altri scenari, tuttavia, i cookie non sono un mezzo naturale per salvare in modo permanente e trasmettere i dati.

Ad esempio, in un'API Web di ASP.NET Core che espone endpoint RESTful a cui potrebbero accedere applicazioni a pagina singola, client nativi o anche da altre API Web, in genere è consigliabile usare l'autenticazione con bearer token. Questi tipi di applicazioni non usano i cookie, ma possono recuperare facilmente un bearer token e includerlo nell'intestazione di autorizzazione delle richieste successive. Per consentire l'autenticazione del token, ASP.NET Core supporta diverse opzioni di utilizzo di [OAuth 2.0](https://oauth.net/2/) e [OpenID Connect](https://openid.net/connect/).

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a>Eseguire l'autenticazione con un provider di identità OpenID Connect o OAuth 2.0

Se le informazioni dell'utente sono archiviate in Azure Active Directory o in un'altra soluzione di identità che supporta OpenID Connect o OAuth 2.0, è possibile usare il pacchetto **Microsoft.AspNetCore.Authentication.OpenIdConnect** per eseguire l'autenticazione tramite il flusso di lavoro di OpenID Connect. Ad esempio per eseguire l'autenticazione con il microservizio Identity.Api in eshopOnContainers, un'applicazione Web ASP.NET Core può usare il middleware del pacchetto, come illustrato nell'esempio semplificato seguente in `Startup.cs`:

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = OpenIdConnectDefaults.AuthenticationScheme;
    })
    .AddCookie()
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl;
        options.SignedOutRedirectUri = callBackUrl;
        options.ClientSecret = "secret";
        options.SaveTokens = true;
        options.GetClaimsFromUserInfoEndpoint = true;
        options.RequireHttpsMetadata = false;
        options.Scope.Add("openid");
        options.Scope.Add("profile");
        options.Scope.Add("orders");
        options.Scope.Add("basket");
        options.Scope.Add("marketing");
        options.Scope.Add("locations");
        options.Scope.Add("webshoppingagg");
        options.Scope.Add("orders.signalrhub");
    });
}
```

Si noti che quando si usa questo flusso di lavoro il middleware di ASP.NET Core Identity non è necessario, perché tutte le operazioni di archiviazione e autenticazione delle informazioni degli utenti vengono gestite dal servizio di gestione delle identità.

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a>Rilasciare token di sicurezza da un servizio ASP.NET Core

Se si vuole rilasciare token di sicurezza per gli utenti locali di ASP.NET Core Identity anziché usare un provider di identità esterna, è possibile avvalersi di alcune utili librerie di terze parti.

[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) e [OpenIddict](https://github.com/openiddict/openiddict-core) sono provider OpenID Connect che si integrano facilmente con ASP.NET Core Identity per il rilascio di token di sicurezza da un servizio ASP.NET Core. La [documentazione di IdentityServer4](https://identityserver4.readthedocs.io/en/latest/) contiene istruzioni dettagliate per l'uso della libreria. Di seguito sono indicate le operazioni di base per usare IdentityServer4 per il rilascio di token.

1. Chiamare app.UseIdentityServer nel metodo Startup.Configure per aggiungere IdentityServer4 alla pipeline di elaborazione delle richieste HTTP dell'applicazione. In questo modo, la libreria fornisce richieste agli endpoint OpenID Connect e OAuth2 come /connect/token.

2. IdentityServer4 viene configurato in Startup.ConfigureServices tramite una chiamata a services.AddIdentityServer.

3. Il server delle identità viene configurato impostando i dati seguenti:

   - Le [credenziali](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) da usare per la firma.

   - Le [risorse di identità e API](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) a cui gli utenti potrebbero richiedere l'accesso:

      - Le risorse API rappresentano dati protetti o funzionalità a cui l'utente può accedere con un token di accesso. Un esempio di risorsa API è un'API o un set di API Web che richiede l'autorizzazione.

      - Le risorse di identità rappresentano informazioni (attestazioni) che vengono fornite a un client per identificare un utente. Le attestazioni possono includere il nome utente, l'indirizzo di posta elettronica e così via.

   - I [client](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) che si connetteranno per richiedere i token.

   - Il meccanismo di archiviazione delle informazioni degli utenti, ad esempio [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) o un sistema alternativo.

Quando si specificano i client e le risorse da usare con IdentityServer4, è possibile passare una raccolta <xref:System.Collections.Generic.IEnumerable%601> del tipo appropriato ai metodi che accettano archivi di client o risorse in memoria. In alternativa, per scenari più complessi, è possibile fornire tipi di provider di client o risorse tramite l'inserimento delle dipendenze.

Un esempio di configurazione per IdentityServer4 che usa le risorse e i client in memoria forniti da un tipo IClientStore personalizzato è simile al codice seguente:

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

### <a name="consume-security-tokens"></a>Usare i token di sicurezza

L'autenticazione con un endpoint OpenID Connect o l'emissione di token di sicurezza propri coprono alcuni scenari. Ma occorre considerare anche i casi in cui un servizio necessita semplicemente di limitare l'accesso agli utenti che hanno token di sicurezza validi forniti da un servizio diverso.

Per questo scenario è disponibile il middleware di autenticazione che gestisce i token JWT nel pacchetto **Microsoft.AspNetCore.Authentication.JwtBearer**. JWT è l'acronimo di "[JSON Web Token (token Web JSON)](https://tools.ietf.org/html/rfc7519)" ed è un formato di token di sicurezza comune, definito da RFC 7519, per la comunicazione di attestazioni di sicurezza. Un esempio semplificato dell'uso del middleware con questi token può essere simile a questo frammento di codice, tratto dal microservizio Ordering.Api di eShopOnContainers.

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

I parametri in questo caso sono:

- `Audience` rappresenta il destinatario del token in ingresso o la risorsa a cui il token concede l'accesso. Se il valore specificato in questo parametro non corrisponde al parametro nel token, il token verrà rifiutato.

- `Authority` è l'indirizzo del server di autenticazione che emette i token. Il middleware di autenticazione del bearer token JWT usa questo URI per ottenere la chiave pubblica che può essere usata per convalidare la firma del token. Il middleware verifica anche che il parametro `iss` nel token corrisponda a questo URI.

Un altro parametro, `RequireHttpsMetadata`, è utile per i test. Impostando questo parametro su false è possibile testare l'applicazione in ambienti in cui non sono presenti certificati. Nelle distribuzioni effettive, i bearer token JWT devono sempre essere passati solo su HTTPS.

Con questo middleware, i token JWT vengono estratti automaticamente dalle intestazioni di autorizzazione. Vengono quindi deserializzati, convalidati (tramite i valori nei parametri `Audience` e `Authority`) e archiviati come informazioni utente alle quali fare riferimento in seguito con azioni MVC o filtri di autorizzazione.

Il middleware di autenticazione con bearer token JWT può supportare anche scenari più avanzati, ad esempio l'uso di un certificato locale per convalidare un token se l'autorità non è disponibile. Per questo scenario è possibile specificare un oggetto `TokenValidationParameters` nell'oggetto `JwtBearerOptions`.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Condivisione dei cookie tra applicazioni** \
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- **Introduzione all'identità** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- **Rick Anderson. Autenticazione a due fattori con SMS** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- **Abilitazione dell'autenticazione con Facebook, Google e altri provider esterni** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- **Michell Anicas. An Introduction to OAuth 2 (Introduzione a OAuth 2)** \
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- **AspNet.Security.OAuth.Providers** (repository GitHub per i provider OAuth ASP.NET) \
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- **Danny Strockis. Integrating Azure AD into an ASP.NET Core web app (Integrazione di Azure AD in un'app Web ASP.NET Core)** \
  <https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/>

- **IdentityServer4. Documentazione ufficiale** \
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
>[Precedente](../implement-resilient-applications/monitor-app-health.md)
>[Successivo](authorization-net-microservices-web-applications.md)
