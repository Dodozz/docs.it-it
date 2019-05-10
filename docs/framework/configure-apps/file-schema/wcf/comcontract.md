---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 5d6bfb1e4aa1651cd8c3a869f681d71cfb15725c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751880"
---
# <a name="comcontract"></a>\<comContract>
Specifica un contratto del servizio COM+ Integration.  
  
 \<system.ServiceModel>  
\<comContracts>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|contratto|Stringa che contiene il tipo di contratto.|  
|name|Stringa che contiene il nome del contratto.|  
|namespace|Stringa che contiene lo spazio dei nomi del contratto.|  
|requiresSession|Valore booleano che specifica se il contratto può essere usato solo nelle associazioni con sessione. All'avvio del servizio, il runtime di integrazione verifica che questa impostazione sia coerente con il tipo di associazione da usare. Viene generata un'eccezione se una o più delle associazioni per il contratto sono in conflitto tra loro. Se questa proprietà è `false` e viene usato un canale unidirezionale in presenza di parametri [out], viene generata un'eccezione.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|persistableTypes|Tutti i tipi persistenti.|  
|userDefinedTypes|Raccolta di tipi definiti dall'utente che deve essere inclusa nel contratto di servizio.|  
|exposedMethods|Raccolta di metodi COM+ che vengono esposti quando l'interfaccia in un componente COM+ viene esposta come servizio Web.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|comContracts|Contiene una raccolta di elementi `comContract`.|  
  
## <a name="remarks"></a>Note  
 Contratti di servizio COM+ integration sono limitati attualmente al `http://tempuri.org` spazio dei nomi e nome del contratto è derivato dall'interfaccia COM di supporto. È tuttavia possibile specificare alternative usando la sezione `comContracts` e anche l'elemento `comContract` nel file di configurazione. Ad esempio, è possibile usare la configurazione seguente per specificare lo spazio dei nomi, il nome del contratto, i tipi definiti dall'utente da includere e altre impostazioni per un contratto di servizio.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 Quando il servizio viene inizializzato, gli spazi dei nomi specificati e i nomi del contratto vengono applicati alle descrizioni del servizio generate.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [Integrazione con applicazioni COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Procedura: Configurare le impostazioni di servizio COM+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
