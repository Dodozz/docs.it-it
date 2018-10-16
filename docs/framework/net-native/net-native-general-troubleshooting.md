---
title: Risoluzione dei problemi generale per .NET Native
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45a053d2aefa8a295e0e8d52818472647e4ef834
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347591"
---
# <a name="net-native-general-troubleshooting"></a>Risoluzione dei problemi generale per .NET Native
In questo argomento viene descritto come risolvere i problemi che potrebbero verificarsi durante lo sviluppo di app con [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
-   **Problema:** la finestra di output di compilazione non viene aggiornata correttamente.  
  
     **Risoluzione:** la finestra di output di compilazione non viene aggiornata correttamente finché non viene completata la compilazione. La compilazione può richiedere qualche minuto, quindi è possibile che si verifichi un ritardo nella visualizzazione degli aggiornamenti.  
  
-   **Problema:** il tempo di compilazione per la versione finale dell'app per ARM è aumentato.  
  
     **Risoluzione:** quando si distribuisce un'app nel dispositivo ARM, viene richiamata l'infrastruttura [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Questa compilazione esegue diverse ottimizzazioni, assicurando al tempo stesso il corretto funzionamento della semantica non statica, ad esempio la reflection. Inoltre, la parte di .NET Framework usata dall'app è collegata staticamente per assicurare prestazioni ottimizzate e deve essere compilata anch'essa in codice nativo. Ecco perché la compilazione richiede più tempo.  
  
     Tuttavia, i tempi di compilazione sono ancora compresi nell'intervallo di un minuto rispetto alla compilazione standard della maggior parte delle app in un computer di sviluppo standard.  In genere la semplice generazione di immagini native per .NET Framework in un computer di sviluppo standard richiede alcuni minuti.  Anche considerando tutte le ottimizzazioni per il miglioramento del codice generato e includendo .NET Framework, i tempi di compilazione dell'app corrispondono solitamente a un minuto o due.  
  
     Il processo di miglioramento delle prestazioni di compilazione è costante e viene eseguito analizzando la compilazione multithread e altre ottimizzazioni.  
  
-   **Problema:** non si sa se l'app è stata compilata usando [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
     **Risoluzione:** se viene richiamato il compilatore [!INCLUDE[net_native](../../../includes/net-native-md.md)], i tempi di compilazione saranno più lunghi e Gestione attività visualizzerà diversi processi dei componenti [!INCLUDE[net_native](../../../includes/net-native-md.md)], ad esempio ILC.exe e nutc_driver.exe.  
  
     Dopo aver compilato correttamente il progetto con [!INCLUDE[net_native](../../../includes/net-native-md.md)], l'output è disponibile in obj\\*config*\ *arch*\\*nomeprogetto*.ilc\out.  I contenuti del pacchetto nativo finale sono disponibili in bin\\*arch*\\*config*\AppX. I contenuti del pacchetto nativo finale sono disponibili in \bin\\*arch*\\*config*\AppX se l'app è stata distribuita.  
  
-   **Problema:** l'app compilata in .NET Native sta generando eccezioni di runtime (in genere eccezioni [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) o [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)) che non sono state generate al momento della compilazione senza .NET Native.  
  
     **Risoluzione:** le eccezioni vengono generate perché .NET Native non ha fornito metadati o il codice di implementazione altrimenti disponibile attraverso la reflection. Per altre informazioni, vedere [Compilazione e .NET Native](../../../docs/framework/net-native/net-native-and-compilation.md). Per eliminare l'eccezione, si deve aggiungere una voce al proprio [file di direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) in modo che la catena di strumenti di .NET Native possa rendere i metadati o il codice di implementazione disponibile in fase di esecuzione. Sono disponibili due strumenti di risoluzione dei problemi che genereranno la voce necessaria per l'aggiunta del file di direttive di runtime:  
  
    -   Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) per i tipi.  
  
    -   Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) per i metodi.  
  
     Per altre informazioni, vedere [Reflection e .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Migrazione dell'app di Windows Store a .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)
