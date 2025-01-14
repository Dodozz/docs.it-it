---
title: 'Mitigazione: Autenticazione del certificato e servizi WCF'
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f94cabb482a237395854fcdc91df476c567069c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599501"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a>Mitigazione: Autenticazione del certificato e servizi WCF
.NET Framework 4.6 aggiunge TLS 1.1 e TLS 1.2 all'elenco predefinito dei controlli SSL WCF. Quando .NET Framework 4.6 o versione successiva è installato sia nei computer client che nei server, per la negoziazione viene usato TLS 1.2.  
  
## <a name="impact"></a>Impatto  
 TLS 1.2 non supporta l'autenticazione dei certificati MD5. Di conseguenza, se un cliente usa un certificato SSL che a sua volta usa MD5 per l'algoritmo hash, il client di WCF non riesce a connettersi al servizio WCF. Per altre informazioni, vedere [Mitigazione: Autenticazione del certificato e servizi WCF](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).  
  
## <a name="mitigation"></a>Mitigazione  
 È possibile risolvere questo problema in modo che un client WCF possa connettersi a un server WCF effettuando una delle operazioni seguenti:  
  
- Aggiornare il certificato in modo che non usi l'algoritmo MD5. Si tratta della soluzione consigliata.  
  
- Se l'associazione non è configurata in modo dinamico nel codice sorgente, aggiornare il file di configurazione dell'applicazione in modo che usi TLS 1.1 o una versione precedente del protocollo. In questo modo è possibile continuare a usare un certificato con l'algoritmo hash MD5.  
  
    > [!CAUTION]
    >  Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.  
  
     Il file di configurazione seguente permette di effettuare queste operazioni:  
  
    ```xml  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding>  
                        <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                            <transport clientCredentialType="None|Windows|Certificate"  
                                                protectionLevel="None|Sign|EncryptAndSign"  
                                                sslProtocols="Ssl3|Tls1|Tls11">  
                            </transport>  
                        </security>  
                    </binding>  
                </netTcpBinding>  
            </bindings>  
        </system.ServiceModel>  
    </configuration>  
    ```  
  
- Se l'associazione è configurata in modo dinamico nel codice sorgente, aggiornare la proprietà <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> in modo che usi TLS 1.1(<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) o una versione precedente del protocollo nel codice sorgente.  
  
    > [!CAUTION]
    >  Questa soluzione non è consigliata, poiché un certificato con l'algoritmo hash MD5 viene considerato non protetto.  
  
## <a name="see-also"></a>Vedere anche

- [Modifiche al runtime](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
