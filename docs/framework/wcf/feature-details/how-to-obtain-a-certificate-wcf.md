---
title: 'Procedura: Ottenere un certificato (WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 1a2731c535bd403046ca3bc01364d0933f127a7f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643676"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Procedura: Ottenere un certificato (WCF)
Per usare uno qualsiasi di Windows Communication Foundation (WCF) funzionalità di che utilizzano i certificati X.509, è necessario prima ottenere i certificati.  
  
### <a name="to-obtain-an-x509-certificate"></a>Per ottenere un certificato X.509  
  
1. Effettuare una delle seguenti operazioni:  
  
    - Acquistare un certificato da un'autorità di certificazione, ad esempio VeriSign, Inc.  
  
    - Configurare il proprio servizio certificati e fare in modo che un'autorità di certificazione firmi i certificati. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows 2000 Server, Windows 2000 Datacenter Server e Windows 2000 Datacenter Server includono tutti servizi certificati che supportano l'infrastruttura a chiave pubblica (PKI). In Windows Server 2008, utilizzare il [Servizi certificati Active Directory](https://go.microsoft.com/fwlink/?LinkID=153483) ruolo per gestire un'autorità di certificazione.  
  
    - Configurare un proprio servizio certificati e non far firmare i certificati.  
  
    > [!NOTE]
    >  Indipendentemente dall'approccio adottato, il destinatario della richiesta SOAP che contiene il certificato X.509 deve considerare attendibile il certificato X.509. Questo significa che il certificato X.509 o un'autorità emittente nella catena di certificati si trova nell'archivio certificati Persone attendibili e che il certificato X.509 non si trova nell'archivio Certificati non disponibili nell'elenco locale.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Procedura: Creare certificati temporanei da usare durante lo sviluppo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
