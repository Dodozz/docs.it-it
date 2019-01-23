---
title: Recupero dei metadati
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], retrieving
ms.assetid: 18d8ba4c-af0f-4827-a50b-4202d767bacc
ms.openlocfilehash: 72a9b8445a83af3cbda15c5f4580a1c1df859339
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533234"
---
# <a name="retrieving-metadata"></a>Recupero dei metadati
Il recupero dei metadati è il processo di richiesta e di recupero dei metadati da un endpoint di metadati, ad esempio un endpoint di metadati WS-MetadataExchange (MEX) o un endpoint di metadati HTTP/GET.  
  
## <a name="retrieving-metadata-from-the-command-line-using-svcutilexe"></a>Recupero dei metadati dalla riga di comando utilizzando Svcutil.exe  
 È possibile recuperare metadati del servizio utilizzando richieste WS-MetadataExchange o HTTP/GET mediante il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) dello strumento e passando il `/target:metadata` switch e un indirizzo. Svcutil.exe scarica i metadati all'indirizzo specificato e salva il file su disco. Lo strumento utilizza internamente un'istanza <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> e carica dalla configurazione la configurazione dell'endpoint <xref:System.ServiceModel.Description.IMetadataExchange> il cui nome corrisponde allo schema dell'indirizzo passato a Svcutil.exe come input.  
  
## <a name="retrieving-metadata-programmatically-using-the-metadataexchangeclient"></a>Recupero dei metadati a livello di codice utilizzando MetadataExchangeClient  
 Windows Communication Foundation (WCF) è possibile recuperare i metadati del servizio utilizzando protocolli standard, ad esempio WS-MetadataExchange e richieste HTTP/GET. Entrambi questi protocolli sono supportati dal tipo <xref:System.ServiceModel.Description.MetadataExchangeClient>. Per recuperare i metadati del servizio, utilizzare il tipo <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> fornendo un indirizzo per l'endpoint dei metadati e un'associazione facoltativa. L'associazione utilizzata da un'istanza <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> può essere una delle associazioni predefinite dalla classe statica <xref:System.ServiceModel.Description.MetadataExchangeBindings>, un'associazione fornita dall'utente o un'associazione caricata dalla configurazione dell'endpoint per il contratto `IMetadataExchange`. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> può inoltre risolvere i riferimenti dell'URL HTTP ai metadati utilizzando il tipo <xref:System.Net.HttpWebRequest>.  
  
 Per impostazione predefinita, un'istanza di <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> è collegata a una sola istanza di <xref:System.ServiceModel.ChannelFactory>. È possibile modificare o sostituire l'istanza di <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> utilizzata da <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> eseguendo l'override del metodo virtuale <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>. Analogamente, è possibile modificare o sostituire l'istanza di <xref:System.Net.HttpWebRequest> utilizzata da <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> per le richieste HTTP/GET eseguendo l'override del metodo virtuale <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Usare Svcutil.exe per scaricare documenti di metadati](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)  
 Viene illustrato come utilizzare Svcutil.exe per scaricare documenti di metadati  
  
 [Procedura: Usare la classe MetadataResolver per ottenere dinamicamente i metadati di associazione](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)  
 Viene illustrato come utilizzare <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> per ottenere dinamicamente i metadati di associazione a runtime.  
  
 [Procedura: Usare MetadataExchangeClient per recuperare i metadati](../../../../docs/framework/wcf/feature-details/how-to-use-metadataexchangeclient-to-retrieve-metadata.md)  
 Viene illustrato come utilizzare la classe <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> per scaricare file di metadati in un oggetto <xref:System.ServiceModel.Description.MetadataSet?displayProperty=nameWithType> contenente oggetti <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> per la scrittura nei file o per altri utilizzi.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Description.MetadataExchangeClient>
