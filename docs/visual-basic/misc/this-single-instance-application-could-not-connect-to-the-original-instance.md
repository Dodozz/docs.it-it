---
title: Impossibile connettere l'applicazione a istanza singola con l'istanza originale
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 7ffa9b185e16cfdf8223ce84e77d1a0e1fa67f65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322654"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a>Impossibile connettere l'applicazione a istanza singola con l'istanza originale
Impossibile connettere l'applicazione a istanza singola con l'istanza originale. Alcune possibili cause di questo problema sono le seguenti:  
  
-   L'istanza originale attualmente non risponde.  
  
-   L'applicazione non dispone di autorizzazioni per la creazione di oggetti del kernel. Per altre informazioni sugli oggetti kernel, vedere [mutex](../../standard/threading/mutexes.md).  
  
     Il nome base degli oggetti del kernel deriva dalla concatenazione del GUID dell'assembly, del numero di versione principale e del numero di versione secondario. Il nome base ad esempio potrebbe essere `3639f15d-9547-43da-8145-60da347829915.1`.  
  
## <a name="to-correct-this-error-when-developing-the-application"></a>Per correggere questo errore quando si sviluppa l'applicazione  
  
1. Verificare che l'applicazione non passi allo stato di non reattività.  
  
2. Verificare che l'applicazione abbia autorizzazioni sufficienti per creare oggetti kernel.  
  
3. Riavviare l'istanza originale dell'applicazione.  
  
4. Riavviare il computer per cancellare i processi che stanno usando la risorsa necessaria per la connessione all'istanza originale.  
  
5. Prendere nota delle circostanze in cui si è verificato l'errore e chiamare il Servizio supporto tecnico Microsoft.  
  
## <a name="see-also"></a>Vedere anche

- [Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)
