---
title: Identificazione delle funzioni nelle DLL
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4c56712460d772426a2d8d6d328cba9bb03373d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648667"
---
# <a name="identifying-functions-in-dlls"></a>Identificazione delle funzioni nelle DLL
L'identità di una funzione di una DLL è costituita dagli elementi seguenti:  
  
- Nome della funzione o numero ordinale  
  
- Nome del file DLL in cui si può trovare l'implementazione  
  
 Ad esempio, specificando la funzione **MessageBox** in User32.dll, vengono identificate la funzione (**MessageBox**) e la sua posizione (User32.dll, User32 o user32). L'Application Programming Interface di Microsoft Windows (API Windows) può contenere due versioni di ogni funzione che gestisce i caratteri e le stringhe: una versione ANSI con caratteri a 1 byte e una versione Unicode con caratteri a 2 byte. Se non è specificato, il set di caratteri, rappresentato dal campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, usa come impostazione predefinita la versione ANSI. Alcune funzioni possono includere più di due versioni.  
  
 **MessageBoxA** è il punto di ingresso ANSI per la funzione **MessageBox**, mentre **MessageBoxW** è la versione Unicode. Per elencare i nomi di funzione per una DLL specifica, ad esempio user32.dll, è possibile eseguire numerosi strumenti della riga di comando. Ad esempio, è possibile usare `dumpbin /exports user32.dll` o `link /dump /exports user32.dll` per ottenere i nomi di funzione.  
  
 È possibile rinominare una funzione non gestita con qualsiasi nome desiderato all'interno del codice, a condizione di eseguire il mapping del nuovo nome al punto di ingresso originale nella DLL. Per istruzioni su come rinominare una funzione DLL non gestita in codice sorgente gestito, vedere [Specifica di un punto di ingresso](../../../docs/framework/interop/specifying-an-entry-point.md).  
  
 Platform invoke consente di controllare una parte significativa del sistema operativo chiamando funzioni nell'API Windows e altre DLL. Oltre all'API Windows, sono disponibili molte altre API e DLL tramite platform invoke.  
  
 La tabella seguente descrive diverse DLL di uso comune nell'API Windows.  
  
|DLL|Descrizione del contenuto|  
|---------|-----------------------------|  
|GDI32.dll|Funzioni Graphics Device Interface (GDI) per l'output del dispositivo, ad esempio per il disegno e la gestione dei tipi di carattere.|  
|Kernel32.dll|Funzioni del sistema operativo di basso livello per la gestione delle memoria e delle risorse.|  
|User32.dll|Funzioni di gestione di Windows per la gestione dei messaggi, i timer, i menu e le comunicazioni.|  
  
 Per la documentazione completa dell'API Windows, vedere l'SDK della piattaforma. Per alcuni esempi che mostrano come costruire dichiarazioni basate su .NET da usare con platform invoke, vedere , vedere [Marshalling dei dati con platform invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di funzioni di DLL non gestite](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
- [Specifica di un punto di ingresso](../../../docs/framework/interop/specifying-an-entry-point.md)
- [Creazione di una classe che contenga le funzioni DLL](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)
- [Creazione di prototipi nel codice gestito](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [Chiamata a una funzione di DLL](../../../docs/framework/interop/calling-a-dll-function.md)
