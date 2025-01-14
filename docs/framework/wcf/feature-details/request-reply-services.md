---
title: Servizi request/reply
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
ms.openlocfilehash: 1ff11b1cae4ec8f6fe886a55cb0add27831048d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991120"
---
# <a name="request-reply-services"></a>Servizi request/reply
Servizi request / reply sono il tipo predefinito di contratto dell'operazione in Windows Communication Foundation (WCF). I client effettuano chiamate alle operazioni del servizio e attendono una risposta dal servizio. È possibile effettuare chiamate a un'operazione del servizio in modo sincrono o asincrono. Nel primo caso, il client si blocca finché non riceve una risposta dal servizio o la chiamata scade, mentre nel secondo caso il client esegue una chiamata all'operazione del servizio, continua a funzionare e riceve la risposta dal servizio su un altro thread.  
  
 Per creare un contratto di servizio request/reply, definirlo e applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni operazione, come illustrato nel codice di esempio seguente.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 Non è necessario impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `false` perché questo è il comportamento predefinito.  
  
## <a name="see-also"></a>Vedere anche

- [Servizi unidirezionali](../../../../docs/framework/wcf/feature-details/one-way-services.md)
- [Servizi duplex](../../../../docs/framework/wcf/feature-details/duplex-services.md)
