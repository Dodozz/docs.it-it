---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: e0e5a112b7444872dd74cb70bb044ae233334d2a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181199"
---
# <a name="ienumrawinputdevice"></a>IEnumRAWINPUTDEVICE
Questa interfaccia enumera i dispositivi di input non elaborati e viene usata solo da PresentationHost.exe.  
  
> [!NOTE]
>  Questa API è solo intesa e supportata per l'uso sul computer client locale  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|Vengono enumerati i successivi elementi `celt` successivi (ovvero le strutture RAWINPUTDEVICE) nell'elenco dell'enumeratore, che vengono restituiti in `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched`.|  
|[IEnumRAWINPUTDEVIC:Skip](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|Indica all'enumeratore di ignorare i successivi `celt` gli elementi nell'enumerazione in modo che alla successiva chiamata a [ienumrawinputdevic: Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) non restituirà gli elementi.|  
|[IEnumRAWINPUTDEVIC:Reset](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|Riporta all'inizio la sequenza di enumerazione.|  
|[IEnumRAWINPUTDEVIC:Clone](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.|  
  
## <a name="see-also"></a>Vedere anche  
 [Sull'Input non elaborato](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)
