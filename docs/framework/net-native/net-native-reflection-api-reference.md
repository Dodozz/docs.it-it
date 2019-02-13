---
title: Riferimento all'API Reflection di .NET Native
ms.date: 03/30/2017
ms.assetid: 0429c049-22a3-4ba1-9cc8-f6ee91e31d9c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35dcabcf65af1634533edfba1e300a8746bc97ec
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221368"
---
# <a name="net-native-reflection-api-reference"></a>Riferimento all'API Reflection di .NET Native
[!INCLUDE[net_native](../../../includes/net-native-md.md)] include tre nuovi tipi di eccezione: [System.Runtime.CompilerServices.MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), [System.Reflection.MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), e [missingruntimeartifactexception](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) . Tenere presente quanto segue sui tre tipi di eccezione:  
  
 Questi tipi sono destinati solo all'uso interno.  
 Questi tre tipi di eccezione sono destinati solo per l'uso della catena di strumenti [!INCLUDE[net_native](../../../includes/net-native-md.md)] . Le eccezioni vengono generate quando la catena di strumenti [!INCLUDE[net_native](../../../includes/net-native-md.md)] rileva dati mancanti che non permettono che l'esecuzione del programma continui.  
  
 Non gestire queste eccezioni nel codice.  
 Queste eccezioni indicano che i metadati necessari per l'applicazione sono assenti (eccezioni [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) e [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) ) o che non è presente il codice di implementazione necessario (eccezione [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) ). Per correggere le condizioni di eccezione, è necessario modificare un file di direttive di runtime (rd.xml) per rendere i metadati o il codice di implementazione necessari disponibili durante il runtime. Per altre informazioni, vedere [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Sono disponibili due strumenti di risoluzione dei problemi che forniscono le voci appropriate per il file delle direttive di runtime che eliminerà le eccezioni [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) e [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) :  
  
-   Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) per i tipi.  
  
-   Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) per i metodi.  
  
> [!NOTE]
>  Queste informazioni di riferimento descrivono i tre tipi di eccezione univoci di [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Per documentazione di riferimento per le API reflection di .NET Framework core, vedere la <xref:System.Reflection>, <xref:System.Reflection.Context> e <xref:System.Reflection.Emit> gli spazi dei nomi. Per la documentazione di riferimento per le API di interoperabilità principali di .NET Framework, vedere <xref:System.Runtime.InteropServices>.  
  
## <a name="systemreflection-namespace"></a>Spazio dei nomi System.Reflection  
 Lo spazio dei nomi <xref:System.Reflection> contiene i tipi di base usati per la reflection in .NET Framework. Per [!INCLUDE[net_native](../../../includes/net-native-md.md)], sono inclusi anche due nuovi tipi di eccezioni:  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|[MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)|Eccezione generata quando la reflection viene usata per recuperare i metadati che non sono presenti.|  
|[MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)|L'eccezione generata quando i metadati per un tipo o un membro del tipo sono disponibili ma ne è stata rimossa l'implementazione.|  
  
 Per la documentazione relativa agli altri tipi in questo spazio dei nomi, vedere le pagine di riferimento di <xref:System.Reflection> nella documentazione di .NET Framework.  
  
## <a name="systemruntimecompilerservices-namespace"></a>Spazio dei nomi System.Runtime.CompilerServices  
 Lo spazio dei nomi <xref:System.Runtime.CompilerServices> include tipi progettati per l'utente da compilatori di linguaggio. Per [!INCLUDE[net_native](../../../includes/net-native-md.md)], è incluso anche un nuovo tipo di eccezione:  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|[MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)|Eccezione generata quando viene chiamato un metodo di marshalling manuale, ma i metadati per un tipo non vengono trovati dall'analisi statica o in un file di direttive di runtime.|  
  
 Per la documentazione relativa agli altri tipi in questo spazio dei nomi, vedere le pagine di riferimento di <xref:System.Runtime.CompilerServices> nella documentazione di .NET Framework.  
  
## <a name="see-also"></a>Vedere anche
- [Classe MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)
- [Classe MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)
- [Classe MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)
- [Introduzione](../../../docs/framework/net-native/getting-started-with-net-native.md)
