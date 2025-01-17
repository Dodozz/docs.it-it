---
title: Richieste di collegamento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ba3172b1a82c0a9f624a49eb63a193dd29faac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750734"
---
# <a name="link-demands"></a>Richieste di collegamento
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Una richiesta di collegamento determina l'esecuzione di un controllo di sicurezza in fase di compilazione JIT, durante il quale viene esaminato solo l'assembly chiamante immediato del codice. Il collegamento si verifica quando il codice è associato a un riferimento a un tipo, quale un riferimento a un puntatore a funzione o una chiamata al metodo. Se l'assembly chiamante non dispone delle autorizzazioni sufficienti per collegarsi al codice, il collegamento non viene autorizzato e in fase di caricamento ed esecuzione del codice viene generata un'eccezione di runtime. Le richieste di collegamento possono essere sottoposte a override nelle classi che ereditano dal codice.  
  
 Mediante questo tipo di richiesta non viene eseguita un'analisi completa dello stack e permane il rischio che il codice sia soggetto ad attacchi subdoli. Ad esempio, se un metodo nell'assembly A è protetto da una richiesta di collegamento, un chiamante diretto nell'assembly B viene valutato in base alle autorizzazioni dell'Assembly B.  Tuttavia, la richiesta di collegamento non restituirà un metodo nell'assembly C se il metodo chiamato indirettamente nell'assembly usando il metodo nell'assembly B. La richiesta di collegamento specifica che solo le autorizzazioni di indirizzare i chiamanti nell'assembly chiamante immediato devono avere il collegamento al codice. Non vengono specificate le autorizzazioni necessarie a tutti i chiamanti per l'esecuzione del codice.  
  
 I modificatori di percorso chiamate nello stack <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> e <xref:System.Security.CodeAccessPermission.PermitOnly%2A> non influiscono sulla valutazione delle richieste di collegamento.  poiché queste non eseguono una verifica del percorso chiamate nello stack.  
  
 Se un metodo protetto da una richiesta di collegamento si accede attraverso [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md), quindi una richiesta di collegamento viene controllato il chiamante immediato del codice tramite reflection. Tale comportamento si verifica sia per l'individuazione che per la chiamata di metodi realizzate mediante reflection. Si supponga ad esempio di codice Usa la reflection per restituire un <xref:System.Reflection.MethodInfo> dell'oggetto che rappresenta un metodo protetto da una richiesta di collegamento e quindi passa tale **MethodInfo** oggetto ad altro codice che utilizza l'oggetto per richiamare il metodo originale. In questo caso il controllo della richiesta di collegamento viene eseguito due volte: una volta per il codice che restituisce il **MethodInfo** oggetto e una volta per il codice che lo richiama.  
  
> [!NOTE]
>  Una richiesta di collegamento effettuata su un costruttore di classe statico non consente di proteggere il costruttore, poiché i costruttori statici vengono chiamati dal sistema, all'esterno del percorso di esecuzione del codice dell'applicazione. Quando una richiesta di collegamento viene applicata a un'intera classe, tale richiesta non consente quindi di proteggere l'accesso a un costruttore statico, anche se consente di proteggere il resto della classe.  
  
 Il frammento di codice seguente specifica in modo dichiarativo che a ogni codice collegato al metodo `ReadData` deve essere assegnata l'autorizzazione `CustomPermission`. Questa autorizzazione è un'autorizzazione personalizzata ipotetica e non esiste in .NET Framework. La richiesta viene effettuata mediante il passaggio di un **SecurityAction. LinkDemand** flag per il `CustomPermissionAttribute`.  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function    
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Attributi](../../../docs/standard/attributes/index.md)
- [Sicurezza dall'accesso di codice](../../../docs/framework/misc/code-access-security.md)
