---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 30084143949d2243fd310448c52e6b861505ad66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947966"
---
# <a name="getcustomui"></a>GetCustomUI
Chiamato dal PresentationHost.exe per ottenere lo stato personalizzato e messaggi di errore dall'host, se è implementato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzProgressAssemblyName`  
  
 [out] Un puntatore all'assembly che contiene l'interfaccia utente lo stato di avanzamento fornita dall'host.  
  
 `pwzProgressClassName`  
  
 [out] Il nome della classe che è l'interfaccia utente lo stato di avanzamento fornita dall'host, preferibilmente una [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file con <xref:System.Windows.Controls.Page> elemento di primo livello. Questa classe si trova nell'assembly specificato da `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 [out] Un puntatore all'assembly che contiene l'interfaccia utente di errore fornito dall'host.  
  
 `pwzErrorClassName`  
  
 [out] Il nome della classe che corrisponde all'utente di errore fornito dall'host di interfaccia, preferibilmente un file XAML con <xref:System.Windows.Controls.Page> elemento di primo livello. Questa classe si trova nell'assembly specificato da `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: Ignorato.  
  
## <a name="remarks"></a>Note  
 Un'applicazione host può avere un tema specifico che interfacce utente predefinite del PresentationHost.exe potrebbero non essere conforme a. In questo caso, l'applicazione host può implementare [GetCustomUI](getcustomui.md) per restituire lo stato di avanzamento ed errore interfacce utente a PresentationHost.exe. Chiama sempre PresentationHost.exe [GetCustomUI](getcustomui.md) prima di usare le interfacce utente predefinite.  
  
 Questa funzione viene chiamata una volta durante l'inizializzazione di PresentationHost.  
  
## <a name="see-also"></a>Vedere anche

- [IWpfHostSupport](iwpfhostsupport.md)
