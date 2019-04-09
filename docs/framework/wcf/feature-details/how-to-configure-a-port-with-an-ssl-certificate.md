---
title: 'Procedura: Configurare una porta con un certificato SSL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 533c329bed7b1cb9b07805032c839d3f5ff10634
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139815"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Procedura: Configurare una porta con un certificato SSL
Quando si crea un servizio Windows Communication Foundation (WCF) self-hosted con la <xref:System.ServiceModel.WSHttpBinding> che usa la protezione del trasporto di classi, è anche necessario configurare una porta con un certificato X.509. Se non si intende creare un servizio indipendente, è possibile ospitare il servizio in Internet Information Services (IIS). Per altre informazioni, vedere [protezione del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Per configurare una porta, lo strumento da usare dipende dal sistema operativo eseguito nel computer.  
  
 Se viene eseguito [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], usare lo strumento HttpCfg.exe. Con [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], questo strumento è installato. Con [!INCLUDE[wxp](../../../../includes/wxp-md.md)], è possibile scaricare lo strumento [strumenti di supporto di Windows XP Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=88606). Per altre informazioni, vedere [Panoramica di Httpcfg](https://go.microsoft.com/fwlink/?LinkId=88605). Il [documentazione di Windows Support Tools](https://go.microsoft.com/fwlink/?LinkId=94840) viene illustrata la sintassi per lo strumento Httpcfg.exe.  
  
 Se viene eseguito [!INCLUDE[wv](../../../../includes/wv-md.md)], usare lo strumento Netsh.exe già installato.  
  
 In questo argomento viene descritto come eseguire diverse procedure:  
  
-   Determinazione della configurazione corrente delle porte di un computer  
  
-   Acquisizione dell'identificazione personale (necessaria per le due procedure seguenti) di un certificato  
  
-   Binding di un certificato SSL alla configurazione di una porta  
  
-   Binding di un certificato SSL alla configurazione di una porta e supporto di certificati client  
  
-   Eliminazione di un certificato SSL da un numero di porta  
  
 Si noti che la modifica dei certificati archiviati nel computer richiede privilegi di amministrazione.  
  
### <a name="to-determine-how-ports-are-configured"></a>Per determinare la configurazione delle porte  
  
1.  In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oppure [!INCLUDE[wxp](../../../../includes/wxp-md.md)], usare lo strumento HttpCfg.exe per visualizzare la configurazione corrente delle porte, usando la **query** e **ssl** attiva, come illustrato nell'esempio seguente.  
  
    ```  
    httpcfg query ssl  
    ```  
  
2.  In [!INCLUDE[wv](../../../../includes/wv-md.md)] usare lo strumento Netsh.exe per visualizzare la configurazione corrente delle porte, come illustrato nell'esempio seguente.  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a>Per ottenere l'identificazione personale di un certificato  
  
1.  Usare lo snap-in MMC Certificati per individuare un certificato X.509 che abbia come scopo previsto l'autenticazione client. Per altre informazioni, vedere [Procedura: Visualizzare i certificati con lo Snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2.  Accedere all'identificazione personale del certificato. Per altre informazioni, vedere [Procedura: Recuperare l'identificazione personale di un certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3.  Copiare l'identificazione personale del certificato in un editor di testo, ad esempio Blocco note.  
  
4.  Rimuovere tutti gli spazi tra i caratteri esadecimali. Per eseguire questa operazione, è possibile usare la funzionalità Trova e sostituisci dell'editor di testo per sostituire ogni spazio con un carattere null.  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a>Per associare un certificato SSL a un numero di porta  
  
1.  In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)] usare lo strumento HttpCfg.exe in modalità "impostazione" nell'archivio SSL (Secure Sockets Layer) per associare il certificato a un numero di porta. Lo strumento usa l'identificazione personale per identificare il certificato, come illustrato nell'esempio seguente.  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   Il **-i** commutatore presenta la sintassi `IP`:`port` e indica allo strumento di impostare il certificato sulla porta 8012 del computer. I quattro zero che precedono il numero possono essere anche sostituiti dall'indirizzo IP effettivo del computer.  
  
    -   Il **-h** consente di specificare l'identificazione personale del certificato.  
  
2.  In [!INCLUDE[wv](../../../../includes/wv-md.md)] usare lo strumento Netsh.exe come illustrato nell'esempio seguente.  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   Il **certhash** parametro specifica l'identificazione personale del certificato.  
  
    -   Il **ipport** parametro specifica l'indirizzo IP e la porta e funziona come il **-i** dello strumento Httpcfg.exe descritto.  
  
    -   Il **appid** parametro è un GUID che può essere utilizzato per identificare l'applicazione proprietaria.  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>Per associare un certificato SSL a un numero di porta e ai certificati client supportati  
  
1.  In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)] per supportare client che eseguono l'autenticazione con i certificati X.509 a livello di trasporto, eseguire la procedura precedente passando a HttpCfg.exe un parametro aggiuntivo della riga di comando, come illustrato nell'esempio seguente.  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     Il **-f** commutatore ha la sintassi di `n` dove n è un numero compreso tra 1 e 7. Un valore di 2, come mostrato nell'esempio precedente, abilita certificati client a livello di trasporto. Il valore 3 attiva i certificati client e associa tali certificati a un account Windows. Per il comportamento di altri valori, vedere la Guida di HttpCfg.exe.  
  
2.  In [!INCLUDE[wv](../../../../includes/wv-md.md)] per supportare i client che eseguono l'autenticazione con i certificati X.509 a livello di trasporto, eseguire la procedura precedente, ma con un parametro aggiuntivo, come illustrato nell'esempio seguente.  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a>Per eliminare un certificato SSL da un numero di porta  
  
1.  Usare lo strumento HttpCfg.exe o Netsh.exe per visualizzare le porte e le identificazioni personali di tutti i binding nel computer. Per stampare le informazioni su disco, usare il carattere di reindirizzamento ">", come illustrato nell'esempio seguente.  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2.  Nella [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oppure [!INCLUDE[wxp](../../../../includes/wxp-md.md)], utilizzare lo strumento HttpCfg.exe con la **eliminare** e **ssl** parole chiave. Usare la **-i** per specificare le `IP`:`port` numero e il **-h** per specificare l'identificazione personale.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3.  In [!INCLUDE[wv](../../../../includes/wv-md.md)] usare lo strumento Netsh.exe come illustrato nell'esempio seguente.  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene illustrato come creare un servizio indipendente usando la classe <xref:System.ServiceModel.WSHttpBinding> per la protezione del trasporto. Quando si crea un'applicazione, specificare il numero di porta nell'indirizzo.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Protezione del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
