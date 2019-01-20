---
title: Strutture di debug
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23aa619d666f2e0b9eb67ab4cf8d4f92761865d3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415325"
---
# <a name="debugging-structures"></a>Strutture di debug
Questa sezione descrive le strutture non gestite usate dall'API di debug.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Struttura CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 Definisce la versione del prodotto di Common Language Runtime (CLR) per fini di debug.  
  
 [Struttura1 CodeChunkInfo](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 Rappresenta un singolo blocco di codice in memoria.  
  
 [Struttura CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 Definisce un oggetto che blocca un thread e il motivo del blocco del thread.  
  
 [Struttura CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 Rappresenta una clausola di gestione delle eccezioni (EH, Exception Handling) per una determinata parte di codice del linguaggio intermedio (IL, Intermediate Language).  
  
 [Struttura CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 Rappresenta le informazioni sullo stack frame da un oggetto di eccezione.  
  
 [Struttura CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 Esegue il mapping una [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID all'oggetto corrispondente [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) oggetto.  
  
 COR_ACTIVE_FUNCTION  
 Contiene informazioni sulle funzioni attualmente attive nei frame di un thread.  
  
 [Struttura COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 Fornisce informazioni sul layout di un oggetto Array in memoria.  
  
 COR_DEBUG_IL_TO_NATIVE_MAP  
 Contiene gli offset usati per mappare il codice MSIL (Microsoft Intermediate Language) al codice nativo.  
  
 COR_DEBUG_STEP_RANGE  
 Contene le informazioni sugli offset per un intervallo di codice.  
  
 [Struttura COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 Fornisce informazioni su un campo in un oggetto.  
  
 [Struttura COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 Contiene informazioni su on oggetto da sottoporre a Garbage Collection.  
  
 [Struttura COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 Fornisce informazioni generali sull'heap di Garbage Collection, specificando anche se è enumerabile.  
  
 [Struttura COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 Fornisce informazioni su un oggetto nell'heap gestito.  
  
 COR_IL_MAP  
 Specifica le modifiche nell'offset relativo di una funzione.  
  
 [Struttura COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 Contiene informazioni su un'area della memoria nell'heap gestito.  
  
 [Struttura COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 Contiene un identificatore di tipo.  
  
 [Struttura COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 Fornisce informazioni sul layout di un oggetto in memoria.  
  
 COR_VERSION  
 Archivia il numero di versione in quattro parti standard di Common Language Runtime.  
  
 [Struttura StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 Fornisce un contesto semplice che può essere usato invece di una struttura `CONTEXT` completa.

 [Struttura CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) definisce un intervallo di indirizzi.
 
 [Struttura CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) definisce un livello di integrità per il mapping dell'indirizzo
 
 [Struttura DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) definisce il contenitore per una richiesta del modulo di indirizzo.

  
## <a name="related-sections"></a>Sezioni correlate  
 [Coclassi di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Funzioni statiche globali di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
