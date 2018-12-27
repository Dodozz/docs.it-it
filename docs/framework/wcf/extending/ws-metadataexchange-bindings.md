---
title: Associazioni WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2018
ms.locfileid: "53767348"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="47ee0-102">Associazioni WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="47ee0-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="47ee0-103">In questo argomento vengono illustrate le modalità di costruzione delle associazioni predefinite per lo scambio di metadati per i vari trasporti.</span><span class="sxs-lookup"><span data-stu-id="47ee0-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="47ee0-104">Associazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="47ee0-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="47ee0-105">Nome associazione predefinita</span><span class="sxs-lookup"><span data-stu-id="47ee0-105">Default Binding Name</span></span>|<span data-ttu-id="47ee0-106">Modalità di costruzione dell'associazione</span><span class="sxs-lookup"><span data-stu-id="47ee0-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="47ee0-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="47ee0-107">mexHttpBinding</span></span>|<span data-ttu-id="47ee0-108">Una classe <xref:System.ServiceModel.WSHttpBinding> con protezione a livello di trasporto attivata.</span><span class="sxs-lookup"><span data-stu-id="47ee0-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="47ee0-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="47ee0-109">mexHttpsBinding</span></span>|<span data-ttu-id="47ee0-110">Una classe <xref:System.ServiceModel.WSHttpBinding> che supporta la protezione a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="47ee0-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="47ee0-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="47ee0-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="47ee0-112">Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> che utilizza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="47ee0-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="47ee0-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="47ee0-113">mexTcpBinding</span></span>|<span data-ttu-id="47ee0-114">Una classe <xref:System.ServiceModel.Channels.CustomBinding> con un elemento <xref:System.ServiceModel.Channels.TcpTransportBindingElement> che utilizza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="47ee0-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
