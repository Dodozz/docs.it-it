---
title: 'Procedura: usare più token di sicurezza dello stesso tipo'
ms.date: 03/30/2017
ms.assetid: cf179f48-4ed4-4caa-86a5-ef8eecc231cd
ms.openlocfilehash: b8daf8a2cecfc6a7b17911bb50ad292d481188c7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184263"
---
# <a name="how-to-use-multiple-security-tokens-of-the-same-type"></a>Procedura: usare più token di sicurezza dello stesso tipo
-   In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0 un messaggio del client contiene solo un token di un determinato tipo. Nella nuova versione, i messaggi del client possono contenere più token di uno stesso tipo. In questo argomento viene illustrato come includere più token dello stesso tipo in un messaggio del client.  
  
-   Si noti che non è possibile configurare un servizio in questo modo, in quanto un servizio può contenere un solo token di supporto.  
  
### <a name="to-use-multiple-security-tokens-of-the-same-type"></a>Per usare più token di sicurezza dello stesso tipo  
  
1.  Creare una raccolta di elementi di associazione vuota in cui inserire i dati.  
  
     [!code-csharp[C_CustomBinding#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#9)]  
  
2.  Creare una classe <xref:System.ServiceModel.Channels.SecurityBindingElement> chiamando <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>.  
  
     [!code-csharp[C_CustomBinding#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#10)]  
  
3.  Creare una raccolta <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters>.  
  
     [!code-csharp[C_CustomBinding#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#11)]  
  
4.  Aggiungere i token SAML alla raccolta.  
  
     [!code-csharp[C_CustomBinding#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#12)]  
  
5.  Aggiungere la raccolta alla classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
     [!code-csharp[C_CustomBinding#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#13)]  
  
6.  Aggiungere gli elementi di associazione alla relativa raccolta.  
  
     [!code-csharp[C_CustomBinding#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#14)]  
  
7.  Restituire una nuova associazione personalizzata creata a partire dalla raccolta di elementi di associazione.  
  
     [!code-csharp[C_CustomBinding#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#15)]  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato l'intero metodo descritto nella procedura precedente.  
  
 [!code-csharp[C_CustomBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#7)]  
  
## <a name="see-also"></a>Vedere anche  
 [Architettura di sicurezza](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
