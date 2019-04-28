---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: c0c9848d073c799e1f97dd79b375848dfab71e99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763906"
---
# <a name="metadata"></a><span data-ttu-id="ff7b1-101">\<metadata></span><span class="sxs-lookup"><span data-stu-id="ff7b1-101">\<metadata></span></span>
<span data-ttu-id="ff7b1-102">Specifica la modalità di elaborazione dei metadati di servizio.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-102">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="ff7b1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ff7b1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ff7b1-104">\<client></span><span class="sxs-lookup"><span data-stu-id="ff7b1-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff7b1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff7b1-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff7b1-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ff7b1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ff7b1-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff7b1-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="ff7b1-108">Attributes</span></span>  
 <span data-ttu-id="ff7b1-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ff7b1-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ff7b1-110">Child Elements</span></span>  
  
|<span data-ttu-id="ff7b1-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff7b1-111">Element</span></span>|<span data-ttu-id="ff7b1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff7b1-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff7b1-113">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="ff7b1-113">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="ff7b1-114">Specifica tutte le unità di importazione dei criteri che controllano l'importazione di asserzioni di criteri personalizzati sulle associazioni.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="ff7b1-115">Un'unità di importazione dei criteri viene usata per la ricerca di asserzioni di criteri personalizzati sulle funzionalità delle associazioni e per allegare un elemento di associazione personalizzato che implementa le funzionalità richieste dall'asserzione.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-115">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="ff7b1-116">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="ff7b1-116">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="ff7b1-117">Specifica tutte le unità di importazione WSDL che importano metadati Web Services Description Language (WSDL) 1.1 con allegati WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-117">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="ff7b1-118">Un'unità di importazione WSDL viene usata per importare metadati e per convertire tali informazioni in diverse classi che rappresentano informazioni di contratto e di endpoint.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-118">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="ff7b1-119">Può importare selettivamente informazioni di contratto e di endpoint e proprietà che espongono qualsiasi errore di importazione e accettano informazioni sul tipo relative al processo di importazione e di conversione.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-119">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="ff7b1-120">Supporta inoltre l'importazione di informazioni dell'associazione e proprietà che forniscono accesso a qualsiasi documento di criteri, documento WSDL, estensione WSDL e documento di XML Schema.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-120">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff7b1-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ff7b1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ff7b1-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff7b1-122">Element</span></span>|<span data-ttu-id="ff7b1-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff7b1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff7b1-124">\<client></span><span class="sxs-lookup"><span data-stu-id="ff7b1-124">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="ff7b1-125">La sezione client definisce un elenco di endpoint ai quali un client può connettersi.</span><span class="sxs-lookup"><span data-stu-id="ff7b1-125">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff7b1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff7b1-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="ff7b1-127">Configurazione del client WCF</span><span class="sxs-lookup"><span data-stu-id="ff7b1-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="ff7b1-128">Client</span><span class="sxs-lookup"><span data-stu-id="ff7b1-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
