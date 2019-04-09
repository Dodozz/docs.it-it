---
title: Pubblicazione di metadati
ms.date: 03/30/2017
helpviewer_keywords:
- meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
ms.openlocfilehash: 97836cef12cd1f220e97d2c38d2dca1b878d7484
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183081"
---
# <a name="publishing-metadata"></a>Pubblicazione di metadati
Servizi Windows Communication Foundation (WCF) pubblicano metadati tramite la pubblicazione di uno o più endpoint di metadati. La pubblicazione di metadati del servizio rende disponibili i metadati utilizzando protocolli standard, ad esempio le richieste WS-MetadataExchange (MEX) e HTTP/GET. Gli endpoint dei metadati sono simili ad altri endpoint del servizio per indirizzo, associazione e contratto e possono essere aggiunti a un host del servizio tramite configurazione o codice imperativo.  
  
## <a name="publishing-metadata-endpoints"></a>Pubblicazione di endpoint dei metadati  
 Per pubblicare endpoint dei metadati per un servizio WCF, è innanzitutto necessario aggiungere il <xref:System.ServiceModel.Description.ServiceMetadataBehavior> comportamento al servizio del servizio. L'aggiunta di un'istanza <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> consente al servizio di esporre gli endpoint dei metadati. Quando viene aggiunto il comportamento del servizio <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, è possibile esporre gli endpoint dei metadati che supportano il protocollo MEX o che rispondono alle richieste HTTP/GET.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> utilizza un oggetto <xref:System.ServiceModel.Description.WsdlExporter> per esportare i metadati per tutti gli endpoint nel servizio. Per altre informazioni sull'esportazione di metadati da un servizio, vedere [esportazione e importazione di metadati](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> aggiunge un'istanza <xref:System.ServiceModel.Description.ServiceMetadataExtension> come estensione all'host del servizio. <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> fornisce l'implementazione per i metadati che pubblicano protocolli. È inoltre possibile utilizzare <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> per ottenere i metadati del servizio in fase di esecuzione accedendo alla proprietà <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>.  
  
### <a name="mex-metadata-endpoints"></a>Endpoint dei metadati MEX  
 Per aggiungere endpoint dei metadati che utilizzano il protocollo MEX, aggiungere gli endpoint del servizio all'host del servizio che utilizza il contratto di servizio `IMetadataExchange`. WCF include un <xref:System.ServiceModel.Description.IMetadataExchange> interfacciarsi con questo nome di contratto di servizio che è possibile usare come parte del modello di programmazione WCF. Gli endpoint di WS-MetadataExchange o MEX, possono usare una delle quattro associazioni predefinite che i metodi factory statici espongono nel <xref:System.ServiceModel.Description.MetadataExchangeBindings> classe in modo che corrispondano associazioni predefinite utilizzate dagli strumenti di WCF, ad esempio Svcutil.exe. È inoltre possibile configurare gli endpoint dei metadati MEX utilizzando un'associazione personalizzata.  
  
### <a name="http-get-metadata-endpoints"></a>Endpoint dei metadati HTTP GET  
 Per aggiungere un endpoint dei metadati al servizio che risponda alle richieste HTTP/GET, impostare la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> in <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> su `true`. È inoltre possibile configurare un endpoint dei metadati che utilizza HTTPS impostando la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> in <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> su `true`.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Pubblicare metadati per un servizio usando un file di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Viene illustrato come configurare un servizio WCF per pubblicare metadati in modo che i client possono recuperare i metadati utilizzando un WS-MetadataExchange o una richiesta HTTP/GET tramite la `?wsdl` stringa di query.  
  
 [Procedura: Pubblicare metadati per un servizio usando codice](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Viene illustrato come abilitare la pubblicazione dei metadati per un servizio WCF nel codice in modo che i client possono recuperare i metadati utilizzando un WS-MetadataExchange o una richiesta HTTP/GET tramite la `?wsdl` stringa di query.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>Vedere anche

- [Esportazione e importazione di metadati](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
