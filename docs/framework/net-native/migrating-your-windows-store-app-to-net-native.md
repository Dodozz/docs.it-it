---
title: Migrazione dell'app di Windows Store a .NET Native
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e4d3d7bc574dd27aaea0d43ee6f507dd0c413f2
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063812"
---
# <a name="migrating-your-windows-store-app-to-net-native"></a>Migrazione dell'app di Windows Store a .NET Native
.NET native fornisce la compilazione statica di App di Windows Store o nel computer dello sviluppatore. Ciò differisce dalla compilazione dinamica eseguita per applicazioni Windows Store dal compilatore just-in-time (JIT) o il [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) sul dispositivo. Nonostante le differenze, .NET Native prova a mantenere la compatibilità con le [le app .NET per Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29). Nella maggior parte, ciò che funziona sulle app .NET per Windows Store funziona anche con .NET Native.  Tuttavia, in alcuni casi, è possibile riscontrare differenze di comportamento. Questo documento vengono illustrate le differenze tra le app .NET per Windows Store standard e .NET Native nelle aree seguenti:  
  
- [Differenze generali di runtime](#Runtime)  
  
- [Differenze di programmazione dinamica](#Dynamic)  
  
- [Altre differenze correlate alla reflection](#Reflection)  
  
- [Scenari e API non supportati](#Unsupported)  
  
- [Differenze di Visual Studio](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a>Differenze generali di runtime  
  
- Le eccezioni, ad esempio <xref:System.TypeLoadException>, che vengono generate dal compilatore JIT quando un'app viene eseguita su common language runtime (CLR), in genere producono errori in fase di compilazione quando vengono elaborati da .NET Native.  
  
- Non chiamare il metodo <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> da un thread UI dell'app. Ciò può comportare un deadlock su .NET Native.  
  
- Non fare affidamento sull'ordine di chiamata del costruttore di classe statica. In .NET Native, l'ordine di chiamata è diverso dall'ordine di runtime standard. (anche con il runtime standard, non è consigliabile fare affidamento sull'ordine di esecuzione dei costruttori di classe statici).  
  
- Un ciclo infinito senza eseguire una chiamata (ad esempio, `while(true);`) su qualsiasi thread può comportare l'arresto dell'applicazione. Allo stesso modo, attese lunghe o infinite possono portare all'arresto dell'applicazione.  
  
- Alcuni cicli di inizializzazione generici non generano eccezioni in .NET Native. Ad esempio, il codice seguente genera un'eccezione <xref:System.TypeLoadException> sul CLR standard, In .NET Native non.  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
- In alcuni casi, .NET Native fornisce implementazioni diverse delle librerie di classi .NET Framework. Un oggetto restituito da un metodo implementerà sempre i membri del tipo restituito. Tuttavia, poiché l'implementazione di supporto è diversa, potrebbe non essere possibile eseguire il cast per la stessa raccolta di tipi come su altre piattaforme di.NET Framework. Ad esempio, in alcuni casi, potrebbe non essere possibile eseguire il cast dell'oggetto di interfaccia <xref:System.Collections.Generic.IEnumerable%601> restituito da metodi quali <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> o <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> a `T[]`.  
  
- La cache di WinInet non è abilitata per impostazione predefinita per le app .NET per Windows Store, ma si trova in .NET Native. Questo migliora le prestazioni, ma ha implicazioni sul working set. Non è necessaria alcuna azione da parte dello sviluppatore.  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a>Differenze di programmazione dinamica  
 .NET native collega in modo statico nel codice da .NET Framework per rendere il codice di app-local per ottenere prestazioni ottimali. Tuttavia, le dimensioni binarie devono rimanere ridotte, in modo da non consentire il passaggio dell'intero.NET Framework. Il compilatore .NET Native risolve questa limitazione usando un riduttore di dipendenza che rimuove i riferimenti a codice inutilizzato. Tuttavia, .NET Native potrebbe non gestire o generare alcune informazioni sul tipo e il codice quando tali informazioni non è possibile dedurre in modo statico in fase di compilazione, ma invece recuperati dinamicamente in fase di esecuzione.  
  
 Abilitare .NET native reflection e la programmazione dinamica. Tuttavia, non tutti i tipi possono essere contrassegnati per la reflection, perché ciò rende eccessive le dimensioni del codice generato (soprattutto perché la reflection sulle API pubbliche in .NET Framework è supportata). Il compilatore .NET Native opera scelte intelligenti su quali tipi devono supportare la reflection e mantiene i metadati e genera codice solo per i tipi.  
  
 Ad esempio, il data binding richiede che un'applicazione possa eseguire il mapping dei nomi di proprietà alle funzioni. In .NET per applicazioni Windows Store, Common Language Runtime usa automaticamente la reflection per fornire questa funzionalità per i tipi gestiti e i tipi nativi disponibili al pubblico. In .NET Native, il compilatore include automaticamente i metadati per tipi a cui associare i dati.  
  
 Il compilatore può gestire anche comunemente .NET Native utilizzati tipi generici come <xref:System.Collections.Generic.List%601> e <xref:System.Collections.Generic.Dictionary%602>, che funzionano senza richiedere suggerimenti o direttive. È supportata anche la parola chiave [dinamica](~/docs/csharp/language-reference/keywords/dynamic.md) entro certi limiti.  
  
> [!NOTE]
>  Quando Converti la tua app a .NET Native, è consigliabile testare accuratamente tutti i percorsi di codice dinamico.  
  
 La configurazione predefinita per .NET Native è sufficiente per la maggior parte degli sviluppatori, ma alcuni sviluppatori potrebbe essere necessario ritoccare le relative configurazioni usando delle direttive di runtime (. RD. XML) file. Inoltre, in alcuni casi, il compilatore .NET Native è in grado di determinare quali metadati devono essere disponibili per la reflection e si basa su suggerimenti, in particolare nei casi seguenti:  
  
- Alcuni costrutti come <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> e <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> non possono essere determinati staticamente.  
  
- Poiché il compilatore non può determinare le istanze create, un tipo generico di cui si vuole effettuare la reflection deve essere specificato dalle direttive di runtime. Ciò non solo perché è necessario includere tutto il codice, ma anche perché la reflection sui tipi può creare un ciclo infinito (ad esempio, quando un metodo generico viene richiamato su un tipo generico).  
  
> [!NOTE]
>  Le direttive di runtime sono definite in un file nelle direttive di runtime (rd.xml). Per informazioni generali sull'uso di questo file, vedere [Introduzione](../../../docs/framework/net-native/getting-started-with-net-native.md). Per informazioni sulle direttive di runtime, vedere [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
 .NET native include anche strumenti che consentono allo sviluppatore di determinare quali tipi all'esterno del set predefinito devono supportare la reflection per la profilatura.  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a>Altre differenze correlate alla reflection  
 Esistono numerose altre differenze correlate alla reflection singoli nel comportamento tra le app .NET per Windows Store e .NET Native.  
  
 In .NET Native:  
  
- La reflection privata su tipi e membri della libreria di classi .NET Framework non è supportata. È tuttavia possibile riflettere sui propri tipi e membri privati, nonché sui tipi e membri nelle librerie di terze parti.  
  
- La proprietà <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> restituisce correttamente `false` per un oggetto <xref:System.Reflection.ParameterInfo> che rappresenta un valore restituito. In .NET per applicazioni Windows Store, restituisce `true`. IL (Intermediate language) non supporta direttamente questa funzione, e quindi l'interpretazione viene lasciata al linguaggio.  
  
- I membri pubblici sulle strutture <xref:System.RuntimeFieldHandle> e <xref:System.RuntimeMethodHandle> non sono supportati. Questi tipi sono supportati solo per LINQ, gli alberi delle espressioni e l'inizializzazione di matrice statica.  
  
- <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> e <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> includono membri nascosi in classi di base e perciò potrebbero essere sottoposti a override esplicito. Ciò vale anche per gli altri metodi [RuntimeReflectionExtensions.GetRuntime*](xref:System.Reflection.RuntimeReflectionExtensions) .  
  
- <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> e <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> non hanno esito negativo quando si prova a creare determinate combinazioni (ad esempio, una matrice di ByRef).  
  
- Non è possibile usare la reflection per richiamare i membri con parametri di puntatore.  
  
- Non è possibile usare la reflection per ottenere o impostare un campo del puntatore.  
  
- Quando il numero di argomenti è errato e il tipo di uno degli argomenti non è corretto, .NET Native genera un' <xref:System.ArgumentException> anziché un <xref:System.Reflection.TargetParameterCountException>.  
  
- In genere la serializzazione binaria delle eccezioni non è supportata. Di conseguenza, è possibile aggiungere gli oggetti non serializzabili al dizionario <xref:System.Exception.Data%2A?displayProperty=nameWithType> .  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a>Scenari e API non supportati  
 Nelle sezioni seguenti vengono elencati gli scenari e le API non supportati per lo sviluppo generale, l'interoperabilità e le tecnologie, ad esempio HTTPClient e Windows Communication Foundation (WCF):  
  
- [Sviluppo generale](#General)  
  
- [HttpClient](#HttpClient)  
  
- [Interoperabilità](#Interop)  
  
- [API non supportate](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a>Differenze generali per lo sviluppo  
 **Tipi di valore**  
  
- Se si esegue l'override dei metodi <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> e <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> per un tipo di valore, non chiamare le implementazioni della classe di base. In .NET per applicazioni Windows Store, questi metodi si basano sulla reflection. In fase di compilazione .NET Native genera un'implementazione che non si basa sulla reflection di runtime. Ciò significa che se si non esegue l'override di questi due metodi, funzioneranno come previsto, perché .NET Native genera l'implementazione in fase di compilazione. Tuttavia, se si esegue l'override di questi metodi, ma si chiama l'implementazione della classe base verrà generata un'eccezione.  
  
- Non sono supportati i tipi di valore superiori a un megabyte.  
  
- I tipi di valore non possono avere un costruttore predefinito in .NET Native. (C# e Visual Basic vietano i costruttori predefiniti sui tipi di valore. Tuttavia, è possibile crearli in IL).  
  
 **Matrici**  
  
- Non sono supportate le matrici con limite inferiore diverso da zero. Solitamente, queste matrici vengono create chiamando l'overload di <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> .  
  
- Non è supportata la creazione dinamica di matrici multidimensionali. Tali matrici vengono in genere creata dalla chiamata di un overload del metodo <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> che include un parametro `lengths` oppure dalla chiamata del metodo <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> .  
  
- Le matrici multidimensionali con quattro o più dimensioni non sono supportate; vale a dire il relativo valore della proprietà <xref:System.Array.Rank%2A?displayProperty=nameWithType> è 4 o superiore. Usare invece le [matrici irregolari](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (una matrice di matrici). Ad esempio, `array[x,y,z]` non è valido, mentre `array[x][y][z]` è valido.  
  
- La varianza per le matrici multidimensionali non è supportata e causa un'eccezione <xref:System.InvalidCastException> in fase di esecuzione.  
  
 **Generics**  
  
- L'espansione di tipo generico infinito genera un errore del compilatore. Ad esempio, questo codice non viene compilato:  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 **Pointers**  
  
- Le matrici di puntatori non sono supportate.  
  
- Non è possibile usare la reflection per ottenere o impostare un campo del puntatore.  
  
 **Serializzazione**  
  
 L'attributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> non è supportato. Usare piuttosto l'attributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .  
  
 **Risorse**  
  
 L'uso di risorse localizzate con la classe <xref:System.Diagnostics.Tracing.EventSource> non è supportato. La proprietà <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> non definisce le risorse localizzate.  
  
 **Delegati**  
  
 `Delegate.BeginInvoke` e `Delegate.EndInvoke` non sono supportati.  
  
 **Varie API**  
  
- Il [TypeInfo.GUID](xref:System.Type.GUID) proprietà genera un' <xref:System.PlatformNotSupportedException> eccezione se un <xref:System.Runtime.InteropServices.GuidAttribute> attributo non viene applicato al tipo. Il GUID viene usato principalmente per il supporto COM.  
  
- Il <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> metodo analizza correttamente stringhe che contengono date brevi in .NET Native. Tuttavia, non mantiene la compatibilità con le modifiche nell'analisi di data e ora descritte negli articoli della Microsoft Knowledge Base [KB2803771](https://support.microsoft.com/kb/2803771) e [KB2803755](https://support.microsoft.com/kb/2803755).  
  
- <xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` è arrotondata correttamente in .NET Native. In alcune versioni di CLR, la stringa di risultato viene troncata anziché arrotondata.  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a>Differenze di HttpClient  
 In .NET Native, il <xref:System.Net.Http.HttpClientHandler> classe Usa internamente WinINet (tramite il <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> classe) anziché le <xref:System.Net.WebRequest> e <xref:System.Net.WebResponse> classi usate in applicazioni .NET per Windows Store standard.  WinINet non supporta tutte le opzioni di configurazione supportate dalla classe <xref:System.Net.Http.HttpClientHandler> .  Di conseguenza, si verifica quanto segue:  
  
- Alcune delle proprietà di capacità su <xref:System.Net.Http.HttpClientHandler> restituire `false` in .NET Native, laddove restituiscono `true` nelle app .NET per Windows Store standard.  
  
- Alcune delle proprietà di configurazione `get` le funzioni di accesso restituiscono sempre un valore fisso in .NET Native che è diverso da quello predefinito configurabile nelle app .NET per Windows Store.  
  
 Nelle sottosezioni riportate di seguito sono descritte alcune differenze di comportamento aggiuntive.  
  
 **Proxy**  
  
 Il <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> classe non supporta la configurazione o l'override del proxy su ogni richiesta.  Ciò significa che tutte le richieste in .NET Native usano server proxy configurato system o alcun server proxy, in base al valore di <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> proprietà.  In .NET per applicazioni Windows Store il server proxy viene definito dalla proprietà <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> .  In .NET Native, impostando il <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> su un valore diverso da `null` genera un <xref:System.PlatformNotSupportedException> eccezione.  Il <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> proprietà restituisce `false` in .NET Native, laddove restituisce `true` nelle app .NET Framework per Windows Store standard.  
  
 **Reindirizzamento automatico**  
  
 Il <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> classi non consentono il numero massimo di reindirizzamenti automatici.  Il valore della proprietà <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> è 50 per impostazione predefinita in .NET per applicazioni Windows Store standard e può essere modificato. In .NET Native, il valore di questa proprietà è 10 e se si prova a modificarlo viene generata una <xref:System.PlatformNotSupportedException> eccezione.  Il <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> proprietà restituisce `false` in .NET Native, laddove restituisce `true` nelle app .NET per Windows Store.  
  
 **Decompressione automatica**  
  
 .NET per applicazioni Windows Store consente di impostare la proprietà <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> su <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, sia <xref:System.Net.DecompressionMethods.Deflate> che <xref:System.Net.DecompressionMethods.GZip>o <xref:System.Net.DecompressionMethods.None>.  Supporta solo .NET native <xref:System.Net.DecompressionMethods.Deflate> assieme <xref:System.Net.DecompressionMethods.GZip>, o <xref:System.Net.DecompressionMethods.None>.  Provare a impostare la proprietà <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> su <xref:System.Net.DecompressionMethods.Deflate> o <xref:System.Net.DecompressionMethods.GZip> da soli comporta l'impostazione automatica su <xref:System.Net.DecompressionMethods.Deflate> e <xref:System.Net.DecompressionMethods.GZip>.  
  
 **Cookie**  
  
 La gestione dei cookie viene eseguita simultaneamente da <xref:System.Net.Http.HttpClient> e WinINet.  I cookie di <xref:System.Net.CookieContainer> vengono combinati con i cookie nella cache dei cookie di WinINet.  La rimozione di un cookie da <xref:System.Net.CookieContainer> impedisce a <xref:System.Net.Http.HttpClient> di inviarlo, ma se è già stato rilevato da WinINet, e i cookie non sono stati eliminati dall'utente, WinINet lo invia.  Non è possibile rimuovere a livello di codice un cookie da WinINet usando le API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>o <xref:System.Net.CookieContainer> .  L'impostazione della proprietà <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> su `false` fa solo sì che <xref:System.Net.Http.HttpClient> smetta di inviare cookie; WinINet potrebbe ancora includere i propri cookie nella richiesta.  
  
 **Credenziali**  
  
 In .NET per applicazioni Windows Store, le proprietà <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> e <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> funzionano in maniera indipendente.  Inoltre, la proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> accetta qualsiasi oggetto che implementa l'interfaccia <xref:System.Net.ICredentials> .  In .NET Native, l'impostazione di <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> proprietà `true` fa sì che il <xref:System.Net.Http.HttpClientHandler.Credentials%2A> proprietà diventi `null`.  Inoltre, la proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> può essere impostata solo su `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>o un oggetto di tipo <xref:System.Net.NetworkCredential>.  L'assegnazione di qualsiasi altro oggetto <xref:System.Net.ICredentials> , il più popolare dei quali è <xref:System.Net.CredentialCache>, alla proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> genera una <xref:System.PlatformNotSupportedException>.  
  
 **Altre funzionalità non supportate o non configurabili**  
  
 In .NET Native:  
  
- Il valore della proprietà <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> è sempre <xref:System.Net.Http.ClientCertificateOption.Automatic>.  In .NET per applicazioni Windows Store, il valore predefinito è <xref:System.Net.Http.ClientCertificateOption.Manual>.  
  
- La proprietà <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> non è configurabile.  
  
- La proprietà <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> è sempre `true`.  In .NET per applicazioni Windows Store, il valore predefinito è `false`.  
  
- L'intestazione `SetCookie2` nelle risposte verrà ignorata come obsoleta.  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a>Differenze di interoperabilità  
 **API deprecate**  
  
 Una serie di API usate con minore frequenza per l'interoperabilità con codice gestito è stata deprecata. Se usato con .NET Native, queste API possono generare una <xref:System.NotImplementedException> o <xref:System.PlatformNotSupportedException> eccezione oppure produrre un errore del compilatore. In .NET per applicazioni Windows Store, queste API vengono contrassegnate come obsolete, anche se la chiamata genera un avviso del compilatore invece di un errore del compilatore.  
  
 Le API deprecate per `VARIANT` marshalling includono:  

- <xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>  
- <xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>  
- <xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>
  
 <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> è supportata, ma genera un'eccezione in alcuni scenari, ad esempio quando viene usata con [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) o varianti di ByRef.  
  
 Le API deprecate per [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) supporto include:  
  
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual?displayProperty=fullName> 
- <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>  

API deprecate per eventi COM classici includono:

- <xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>
  
API deprecate nel <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interfaccia, che non è supportato in .NET Native, includere:  
  
- <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (tutti i membri)  
- <xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (tutti i membri)  
- <xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (tutti i membri)  
- <xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>  
  
Altre funzionalità di interoperabilità non supportate includono:  
  
- <xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (tutti i membri)  
- <xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (tutti i membri)  
- <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.UnmanagedType.AsAny?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler?displayProperty=fullName>  
  
 Utilizzato raramente marshalling di API:  
  
- <xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29?displayProperty=fullName>  
  
 **Compatibilità platform invoke e interoperabilità COM**  
  
 La maggior parte delle PInvoke e scenari di interoperabilità COM sono ancora supportati in .NET Native. In particolare, sono supportate tutte le API di interoperabilità con Windows Runtime (WinRT) e tutti i marshalling richiesti per Windows Runtime. Ciò include il supporto del marshalling per:  
  
- Matrici (inclusa <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)  
  
- `BStr`  
  
- Delegati  
  
- Stringhe (Unicode, Ansi e HSTRING)  
  
- Struct (`byref` e `byval`)  
  
- Unioni  
  
- Handle Win32  
  
- Tutti i costrutti di WinRT  
  
- Supporto parziale per il marshalling dei tipi variant. È supportato quanto segue:  
  
    - <xref:System.Boolean>  
  
    - <xref:System.Byte>  
  
    - <xref:System.Decimal>  
  
    - <xref:System.Double>  
  
    - <xref:System.Int16>  
  
    - <xref:System.Int32>  
  
    - <xref:System.Int64>  
  
    - <xref:System.SByte>  
  
    - <xref:System.Single>  
  
    - <xref:System.UInt16>  
  
    - <xref:System.UInt32>  
  
    - <xref:System.UInt64>  
  
    - `BStr`  
  
    - [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)  
  
 Tuttavia, .NET Native non supporta le operazioni seguenti:  
  
- Utilizzo degli eventi COM classici  
  
- Implementazione dell'interfaccia <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> su un tipo gestito  
  
- Implementazione dell'interfaccia [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) su un tipo gestito tramite l'attributo <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> . Notare tuttavia che non è possibile chiamare oggetti COM tramite `IDispatch`e l'oggetto gestito non può implementare `IDispatch`.  
  
 L'uso della reflection per richiamare un metodo platform invoke non è supportato. È possibile aggirare questa limitazione eseguendo il wrapping della chiamata al metodo in un altro metodo e usando la reflection per chiamare invece il wrapper.  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a>Altre differenze rispetto alle API .NET per app di Windows Store  
 In questa sezione sono elencate le API rimanenti che non sono supportate in .NET Native. Il set più grande di API non supportate è rappresentato dalle API di Windows Communication Foundation (WCF).  
  
 **DataAnnotations (System.ComponentModel.DataAnnotations)**  
  
 I tipi di <xref:System.ComponentModel.DataAnnotations> e <xref:System.ComponentModel.DataAnnotations.Schema> gli spazi dei nomi non sono supportati in .NET Native. Sono inclusi i seguenti tipi che sono presenti nelle app .NET per Windows Store per Windows 8:  
  
- <xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>
- <xref:System.ComponentModel.DataAnnotations.EditableAttribute>  
- <xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>  
- <xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>  
  
 **Visual Basic**  
  
 Visual Basic non è attualmente supportato in .NET Native. I seguenti tipi nel <xref:Microsoft.VisualBasic> e <xref:Microsoft.VisualBasic.CompilerServices> gli spazi dei nomi non sono disponibili in .NET Native:  

- <xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>  
  
 **Contesto Reflection (spazio dei nomi System.Reflection.Context)**  
  
 Il <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> classe non è supportata in .NET Native.  
  
 **RTC (System.Net.Http.Rtc)**  
  
 Il `System.Net.Http.RtcRequestFactory` classe non è supportata in .NET Native.  
  
 **Windows Communication Foundation (WCF) (System.ServiceModel.\*)**  
  
 I tipi di [spazi dei nomi System.ServiceModel.*](xref:System.ServiceModel) non sono supportati in .NET Native. Sono inclusi i tipi seguenti:  
  
- <xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>  
- <xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>  
- <xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>  
- <xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>  
- <xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>  
- <xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>  
- <xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>  
- <xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>  
- <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>  
- <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>  
- <xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>  
- <xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>  
  
### <a name="differences-in-serializers"></a>Differenze nei serializzatori  
 Le differenze riportate di seguito riguardano la serializzazione e la deserializzazione con le classi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>e <xref:System.Xml.Serialization.XmlSerializer> :  
  
- In .NET Native <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non riescono a serializzare o deserializzare una classe derivata che ha un membro di classe di base il cui tipo non è un tipo di serializzazione radice. Ad esempio, nel codice seguente, il tentativo di serializzare o deserializzare `Y` genererà un errore:  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     Il tipo `InnerType` non è noto al serializzatore, perché i membri della classe base non vengono attraversati durante la serializzazione.  
  
- <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non riescono a serializzare una classe o una struttura che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> . Ad esempio, i seguenti tipi non riesco a serializzare o deserializzare:  

- <xref:System.Xml.Serialization.XmlSerializer> non riesce a serializzare il valore dell'oggetto seguente, perché non conoscere il tipo esatto dell'oggetto da serializzare:  

- <xref:System.Xml.Serialization.XmlSerializer> non riesce a serializzare o deserializzare se il tipo di oggetto serializzato è <xref:System.Xml.XmlQualifiedName>.  
  
- Tutti i serializzatori (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>e <xref:System.Xml.Serialization.XmlSerializer>) non riescono a generare un codice di serializzazione per il tipo <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> o per un tipo che contiene <xref:System.Xml.Linq.XElement>, visualizzando invece gli errori in fase di compilazione.  
  
- Il funzionamento corretto dei seguenti costruttori dei tipi di serializzazione non è garantito:  
  
    - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=nameWithType>  
  
- <xref:System.Xml.Serialization.XmlSerializer> non riesce a generare il codice per un tipo che ha metodi con uno qualsiasi dei seguenti attributi:  
  
    - <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    - <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    - <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    - <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
- <xref:System.Xml.Serialization.XmlSerializer> non soddisfa l'interfaccia di serializzazione personalizzata di <xref:System.Xml.Serialization.IXmlSerializable> . Se si ha una classe che implementa questa interfaccia, <xref:System.Xml.Serialization.XmlSerializer> considera il tipo come un oggetto Plain Old CLR Object (POCO) di CLR e ne serializza solo le proprietà pubbliche.  
  
- La serializzazione di un normale <xref:System.Exception> oggetto non funziona bene con <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.

<a name="VS"></a>   
## <a name="visual-studio-differences"></a>Differenze di Visual Studio  
 **Eccezioni e debug**  
  
 Quando si eseguono applicazioni compilate con .NET Native nel debugger, eccezioni first-chance sono abilitate per i tipi di eccezione seguente:  
  
- <xref:System.MemberAccessException>  
  
- <xref:System.TypeAccessException>  
  
 **Creazione di applicazioni**  
  
 Usare gli strumenti di compilazione x86 usati per impostazione predefinita da Visual Studio. Non è consigliabile usare gli strumenti di MSBuild AMD64, disponibili in C:\Program Files (x86)\MSBuild\12.0\bin\amd64, perché possono creare problemi di compilazione.  
  
 **Profiler**  
  
- Il profiler della CPU di Visual Studio e il profiler della memoria XAML non visualizzano Just My Code correttamente.  
  
- Il profiler della memoria di XAML non visualizza in modo accurato i dati di heap gestito.  
  
- Il profiler della CPU non identifica correttamente i moduli e consente di visualizzare i nomi di funzione con prefisso.  
  
 **Progetti di librerie unit test**  
  
 L'abilitazione di .NET Native in una libreria Unit Test per un progetto di App Windows Store non è supportato e fa sì che il progetto di compilazione non riesce.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione](../../../docs/framework/net-native/getting-started-with-net-native.md)
- [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Panoramica delle app .NET per Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)
- [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)
