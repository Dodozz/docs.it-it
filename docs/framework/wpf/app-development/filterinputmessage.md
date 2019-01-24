---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: 979fa7b70dc4b43af841c7219d64125caf99e33a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642620"
---
# <a name="filterinputmessage"></a><span data-ttu-id="8c4aa-102">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="8c4aa-102">FilterInputMessage</span></span>
<span data-ttu-id="8c4aa-103">Chiamato da PresentationHost.exe ogni volta che viene ricevuto un messaggio, a meno che non venga restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="8c4aa-103">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c4aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c4aa-104">Syntax</span></span>  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c4aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8c4aa-105">Parameters</span></span>  
 `pMsg`  
  
 <span data-ttu-id="8c4aa-106">[in] Messaggio WM_INPUT inviato alla finestra che sta ricevendo l'input non elaborato.</span><span class="sxs-lookup"><span data-stu-id="8c4aa-106">[in] The WM_INPUT message sent to the window that is getting raw input.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8c4aa-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8c4aa-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="8c4aa-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="8c4aa-108">HRESULT:</span></span>  
  
 <span data-ttu-id="8c4aa-109">S_OK: il filtro non ha elaborato il messaggio e l'elaborazione può proseguire.</span><span class="sxs-lookup"><span data-stu-id="8c4aa-109">S_OK - The filter did not process the message and further processing may occur.</span></span>  
  
 <span data-ttu-id="8c4aa-110">S_FALSE: il filtro ha elaborato questo messaggio e non viene eseguita alcuna ulteriore elaborazione.</span><span class="sxs-lookup"><span data-stu-id="8c4aa-110">S_FALSE - The filter processed this message and no further processing should occur.</span></span>  
  
 <span data-ttu-id="8c4aa-111">E_NOTIMPL: se questo valore viene restituito, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) non viene chiamato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="8c4aa-111">E_NOTIMPL – If this value is returned, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) is not called again.</span></span> <span data-ttu-id="8c4aa-112">È possibile che venga restituito da un'applicazione host interessata solo a fornire interfacce utente personalizzate di stato ed errore a PresentationHost.exe e non a ricevere messaggi di input non elaborato da PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="8c4aa-112">This might be returned from a host application that is only interested in providing custom progress and error user interfaces to PresentationHost.exe is not interested in being forwarded raw input messages from PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c4aa-113">Note</span><span class="sxs-lookup"><span data-stu-id="8c4aa-113">Remarks</span></span>  
 <span data-ttu-id="8c4aa-114">PresentationHost.exe è la destinazione di vari dispositivi di input non elaborato, tra cui tastiere, mouse e telecomandi.</span><span class="sxs-lookup"><span data-stu-id="8c4aa-114">PresentationHost.exe is the target of various raw input devices, including keyboard, mice, and remote controls.</span></span> <span data-ttu-id="8c4aa-115">In alcuni casi, il comportamento nell'applicazione host dipende dall'input che, in caso contrario, verrebbe usato da PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="8c4aa-115">Sometimes, behavior in the host application is dependent on input that would otherwise be consumed by PresentationHost.exe.</span></span> <span data-ttu-id="8c4aa-116">Ad esempio, la visualizzazione di specifici elementi dell'interfaccia utente da parte di un'applicazione host può dipendere dalla ricezione di determinati messaggi di input.</span><span class="sxs-lookup"><span data-stu-id="8c4aa-116">For example, a host application may depend on receiving certain input messages to determine whether or not to display specific user interface elements.</span></span>  
  
 <span data-ttu-id="8c4aa-117">Per consentire all'applicazione host ricevere i messaggi di input necessari per questi comportamenti, PresentationHost.exe inoltra i messaggi di input non elaborati adatti all'applicazione ospitata chiamando [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span><span class="sxs-lookup"><span data-stu-id="8c4aa-117">To allow the host application to receive the necessary input messages to provide these behaviors, PresentationHost.exe forwards appropriate raw input messages to the hosted application by calling [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span></span>  
  
 <span data-ttu-id="8c4aa-118">L'applicazione ospitata riceve i messaggi di input non elaborati tramite la registrazione con il set di dispositivi inpui non elaborato (Human Interface Devices) restituito da [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span><span class="sxs-lookup"><span data-stu-id="8c4aa-118">The hosted application receives raw input messages by registering with the set of raw input devices (Human Interface Devices) returned by [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c4aa-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c4aa-119">See also</span></span>
- [<span data-ttu-id="8c4aa-120">Notifica WM_INPUT</span><span class="sxs-lookup"><span data-stu-id="8c4aa-120">WM_INPUT Notification</span></span>](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
