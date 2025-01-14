---
title: Autorizzazione dell'accesso alle operazioni del servizio
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: 857e1ebe21dcb37764ddf60570a00ec35b205c8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955007"
---
# <a name="authorizing-access-to-service-operations"></a>Autorizzazione dell'accesso alle operazioni del servizio
In questo esempio illustra come usare il [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per abilitare l'uso del <xref:System.Security.Permissions.PrincipalPermissionAttribute> attributo per autorizzare l'accesso alle operazioni del servizio. In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) esempio. Il servizio e client sono configurati utilizzando il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Il `mode` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) è stato impostato su `Message` e `clientCredentialType` è stata impostata su `Windows`. <xref:System.Security.Permissions.PrincipalPermissionAttribute> viene applicato a ogni metodo del servizio e usato per limitare l'accesso alle operazioni. Il chiamante deve essere un amministratore Windows per accedere a tutte le operazioni.  
  
 In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 File di configurazione del servizio Usa la [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per impostare il `principalPermissionMode` attributo:  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>   
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 L'impostazione della `principalPermissionMode` su `UseWindowsGroups` abilita l'uso di <xref:System.Security.Permissions.PrincipalPermissionAttribute> basato sui nomi dei gruppi di Windows.  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> viene applicato a ogni operazione per richiedere che il chiamante appartenga al gruppo Administrators di Windows, come illustrato nell'esempio di codice seguente.  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,   
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Il client comunica correttamente con ogni operazione se viene eseguito con un account che appartiene al gruppo Administrators. In caso contrario, l'accesso viene negato. Per sperimentare un errore di autorizzazione, eseguire il client con un account che non appartiene al gruppo Administrators. Premere INVIO nella finestra della console per arrestare il client.  
  
 Un servizio può ricevere una notifica di errori di autorizzazione implementando un <xref:System.ServiceModel.Dispatcher.IErrorHandler>. Visualizzare [estensione di controllo sulla gestione degli errori e gestione rapporti](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) per informazioni sull'implementazione `IErrorHandler`.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
