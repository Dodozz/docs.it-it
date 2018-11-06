---
title: Autenticazione di base e del digest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
ms.openlocfilehash: db39bdcaf2c3a4457028e30f9458a5626aa7e795
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2018
ms.locfileid: "50190671"
---
# <a name="basic-and-digest-authentication"></a><span data-ttu-id="0055b-102">Autenticazione di base e del digest</span><span class="sxs-lookup"><span data-stu-id="0055b-102">Basic and Digest Authentication</span></span>
<span data-ttu-id="0055b-103">L'implementazione <xref:System.Net> dell'autenticazione di base e digest è conforme alla specifica RFC2617 - HTTP Authentication: Basic and Digest Authentication, disponibile nel sito Web del [World Wide Web Consortium](https://www.w3.org).</span><span class="sxs-lookup"><span data-stu-id="0055b-103">The <xref:System.Net> implementation of basic and digest authentication complies with RFC2617 – HTTP Authentication: Basic and Digest Authentication (available on the [World Wide Web Consortium's](https://www.w3.org) website).</span></span>  
  
 <span data-ttu-id="0055b-104">Per poter usare l'autenticazione di base e digest in un'applicazione, è necessario che vengano specificati un nome utente e una password nella proprietà <xref:System.Net.WebRequest.Credentials%2A> dell'oggetto <xref:System.Net.WebRequest> usato per richiedere dati da Internet, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0055b-104">To use basic and digest authentication, an application must provide a user name and password in the <xref:System.Net.WebRequest.Credentials%2A> property of the <xref:System.Net.WebRequest> object that it uses to request data from the Internet, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
>  <span data-ttu-id="0055b-105">I dati inviati con l'autenticazione di base o digest non sono crittografati, pertanto possono essere visti da un antagonista.</span><span class="sxs-lookup"><span data-stu-id="0055b-105">Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary.</span></span> <span data-ttu-id="0055b-106">Le credenziali di autenticazione di base (nome utente e password) vengono inoltre inviate in testo non crittografato e possono essere intercettate.</span><span class="sxs-lookup"><span data-stu-id="0055b-106">Additionally, Basic Authentication credentials (user name and password) are sent in the clear and can be intercepted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0055b-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0055b-107">See Also</span></span>  
 [<span data-ttu-id="0055b-108">Autenticazione NTLM e Kerberos</span><span class="sxs-lookup"><span data-stu-id="0055b-108">NTLM and Kerberos Authentication</span></span>](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)  
 [<span data-ttu-id="0055b-109">Autenticazione Internet</span><span class="sxs-lookup"><span data-stu-id="0055b-109">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
