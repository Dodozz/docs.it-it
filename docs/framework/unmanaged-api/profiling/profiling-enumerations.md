---
title: Enumerazioni di profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 996352637f34b0b6c0d12e611a6d9e70ab85230e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757573"
---
# <a name="profiling-enumerations"></a>Enumerazioni di profilatura
Questa sezione descrive le enumerazioni non gestite usate dall'API di profilatura.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Enumerazione COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)  
 Indica il tipo di clausola di eccezione in cui il codice è appena entrato o da cui è appena uscito.  
  
 [Enumerazione COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)  
 Definisce i flag di generazione di codice che possono essere impostati con il [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) (metodo).  
  
 [Enumerazione COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)  
 Descrive il finalizzatore per un oggetto.  
  
 [Enumerazione COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)  
 Identifica una generazione di Garbage Collection.  
  
 [Enumerazione COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)  
 Indica il motivo per cui è in corso la Garbage Collection.  
  
 [Enumerazione COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)  
 Indica le proprietà della radice di un Garbage Collector.  
  
 [Enumerazione COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)  
 Indica il tipo di radice di garbage collector esposto dal [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.  
  
 [Enumerazione COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)  
 Flag oltre a quelle disponibili in offre il [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione che il profiler può specificare per il [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodo durante il caricamento.  
  
 [Enumerazione COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)  
 Indica il risultato della ricerca di una funzione memorizzata nella cache.  
  
 [Enumerazione COR_PRF_MISC](../../../../docs/framework/unmanaged-api/profiling/cor-prf-misc-enumeration.md)  
 Contiene valori costanti che specificano identificatori speciali.  
  
 [Enumerazione COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)  
 Specifica le proprietà di un modulo.  
  
 [Enumerazione COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 Contiene i valori usati per specificare il comportamento, le funzionalità o gli eventi ai quali il profiler intende effettuare la sottoscrizione.  
  
 [Enumerazione COR_PRF_RUNTIME_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-runtime-type-enumeration.md)  
 Contiene valori che indicano la versione di Common Language Runtime.  
  
 [Enumerazione COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)  
 Specifica la quantità di dati da passare di nuovo con uno snapshot dello stack in ogni chiamata alla funzione `StackSnapshotCallback` del profiler.  
  
 [Enumerazione COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)  
 Indica se un campo è statico e, in tal caso, la qualità statica che si applica al campo.  
  
 [Enumerazione COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)  
 Indica il motivo per cui il runtime è stato sospeso.  
  
 [Enumerazione COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)  
 Indica il motivo di una transizione da codice gestito a codice non gestito o viceversa.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Panoramica della profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [Strutture di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
