---
title: "Procedura: Controllare l'istanza del servizio"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
ms.openlocfilehash: e8efbc5a3dec5f60dbefc8f6dc377d97b29b7653
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699617"
---
# <a name="how-to-control-service-instancing"></a><span data-ttu-id="d92b0-102">Procedura: Controllare l'istanza del servizio</span><span class="sxs-lookup"><span data-stu-id="d92b0-102">How to: Control Service Instancing</span></span>
<span data-ttu-id="d92b0-103">L'impostazione della modalità di istanza di un servizio consente di specificare quando vengono creati una classe <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> e il relativo oggetto servizio definito dall'utente associato.</span><span class="sxs-lookup"><span data-stu-id="d92b0-103">Setting the instance mode of a service enables you to specify when a <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> (and its associated user-defined service object) is created.</span></span> <span data-ttu-id="d92b0-104">Per un elenco delle modalità possibili, vedere l'enumerazione <xref:System.ServiceModel.InstanceContextMode>.</span><span class="sxs-lookup"><span data-stu-id="d92b0-104">See the <xref:System.ServiceModel.InstanceContextMode> enumeration for the possible modes.</span></span> <span data-ttu-id="d92b0-105">Per altre informazioni sui comportamenti, vedere [configurazione ed estensione del Runtime dei comportamenti](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="d92b0-105">For more information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span> <span data-ttu-id="d92b0-106">Per alcuni esempi funzionanti, vedere [comportamenti](../../../../docs/framework/wcf/samples/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="d92b0-106">For working examples, see [Behaviors](../../../../docs/framework/wcf/samples/behaviors.md).</span></span>  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a><span data-ttu-id="d92b0-107">Per controllare la durata dell'istanza del servizio tramite codice</span><span class="sxs-lookup"><span data-stu-id="d92b0-107">To control the service instance lifetime using code</span></span>  
  
1. <span data-ttu-id="d92b0-108">Applicare la classe <xref:System.ServiceModel.ServiceBehaviorAttribute> alla classe di servizi.</span><span class="sxs-lookup"><span data-stu-id="d92b0-108">Apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> to the service class.</span></span>  
  
2. <span data-ttu-id="d92b0-109">Impostare la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> su uno dei valori seguenti: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> o <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="d92b0-109">Set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property to one of the following values: <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession>, or <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span>  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="d92b0-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="d92b0-110">Example</span></span>  
 <span data-ttu-id="d92b0-111">Nell'esempio di codice seguente, la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> dell'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> viene impostata su <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span><span class="sxs-lookup"><span data-stu-id="d92b0-111">The following code example sets the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property of the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to <xref:System.ServiceModel.InstanceContextMode.PerCall>.</span></span>  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d92b0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d92b0-112">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
- <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>
- <xref:System.ServiceModel.InstanceContextMode>
- [<span data-ttu-id="d92b0-113">Servizio: Esempi di comportamenti</span><span class="sxs-lookup"><span data-stu-id="d92b0-113">Service: Behaviors Samples</span></span>](../samples/behaviors.md)
