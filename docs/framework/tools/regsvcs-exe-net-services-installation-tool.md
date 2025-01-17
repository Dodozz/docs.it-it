---
title: Regsvcs.exe (strumento di installazione dei servizi .NET)
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0dc05294ae762b4f896bb7f514df102c1f948fe0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623402"
---
# <a name="regsvcsexe-net-services-installation-tool"></a>Regsvcs.exe (strumento di installazione dei servizi .NET)
Lo strumento di installazione dei servizi .NET effettua le seguenti operazioni:  
  
- Carica e registra un assembly.  
  
- Genera, registra e installa una libreria dei tipi in un'applicazione COM+ specificata.  
  
- Configura i servizi aggiunti alla classe a livello di codice.  
  
 Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
## <a name="parameters"></a>Parametri  
  
|Argomento|Description|  
|--------------|-----------------|  
|*assemblyFile.dll*|File di assembly di origine. L'assembly deve essere firmato con un nome sicuro. Per altre informazioni, vedere [Firma di un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).|  
  
|Opzione|Description|  
|------------|-----------------|  
|**/appdir:** *percorso*|Specifica la directory radice dell'applicazione.|  
|**/appname:** *nomeApplicazione*|Specifica il nome dell'applicazione COM+ da trovare o creare.|  
|**/c**|Crea l'applicazione di destinazione.|  
|**/componly**|Configura solo i componenti, ignorando metodi e interfacce.|  
|**/exapp**|Indica allo strumento di prevedere un'applicazione esistente.|  
|**/extlb**|Utilizza una libreria dei tipi esistente.|  
|**/fc**|Trova o crea l'applicazione di destinazione.|  
|**/help**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|**/noreconfig**|Non riconfigura un'applicazione di destinazione esistente.|  
|**/nologo**|Evita la visualizzazione del messaggio di avvio Microsoft.|  
|**/parname:** *nome*|Specifica il nome o l'ID dell'applicazione COM+ da trovare o creare.|  
|**/reconfig**|Riconfigura un'applicazione di destinazione esistente. Questa è l'impostazione predefinita.|  
|**/tlb:** *filelibreriatipi*|Specifica il file della libreria dei tipi da installare.|  
|**/u**|Disinstalla l'applicazione di destinazione.|  
|**/quiet**|Specifica la modalità non interattiva; non visualizza il logo e i messaggi di esito positivo.|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="remarks"></a>Osservazioni  
 Regsvcs.exe richiede un file di assembly di origine specificato da *FileAssembly.dll*. L'assembly deve essere firmato con un nome sicuro. Per altre informazioni sulla firma con un nome sicuro, vedere [Firma di un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md). I nomi dell'applicazione di destinazione e del file della libreria dei tipi sono facoltativi. L'argomento *nomeApplicazione* può essere generato dal file di assembly di origine e, se non esiste già, viene creato da Regsvcs.exe. L'argomento *filelibreriatipi* può specificare il nome di una libreria dei tipi. Se non lo si specifica, come impostazione predefinita verrà usato il nome dell'assembly.  
  
 Quando Regsvcs.exe registra i metodi di un componente, lo strumento è soggetto a [richieste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) e [richieste di collegamento](../../../docs/framework/misc/link-demands.md) su tali metodi. Poiché lo strumento viene eseguito in un ambiente completamente attendibile, molte richieste di autorizzazione vengono completate. Regsvcs.exe non è tuttavia in grado di registrare componenti con metodi protetti da una richiesta o una richiesta di collegamento per <xref:System.Security.Permissions.StrongNameIdentityPermission> o <xref:System.Security.Permissions.PublisherIdentityPermission>.  
  
 Per usare Regsvcs.exe, è necessario disporre dei privilegi amministrativi sul computer locale.  
  
 Se durante una di queste operazioni l'esecuzione di Regsvcs.exe si interrompe, verranno visualizzati messaggi di errore pertinenti.  
  
## <a name="examples"></a>Esempi  
 Il comando che segue aggiunge a `myTest.dll` (un'applicazione COM+ esistente) tutte le classi pubbliche contenute in `myTargetApp` e produce la libreria dei tipi `myTest.tlb`.  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 Il comando che segue aggiunge a `myTest.dll` (un'applicazione COM+ esistente) tutte le classi pubbliche contenute in `myTargetApp` e produce la libreria dei tipi `newTest.tlb`.  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti](../../../docs/framework/tools/index.md)
- [Procedura: Firmare un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
