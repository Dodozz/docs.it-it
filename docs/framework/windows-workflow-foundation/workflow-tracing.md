---
title: Traccia del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: 8dba5706ee37f243c15befb483ab4f9f2a8e3b9c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655715"
---
# <a name="workflow-tracing"></a>Traccia del flusso di lavoro
La traccia del flusso di lavoro consente di acquisire informazioni diagnostiche usando i listener di traccia di .NET Framework. La traccia può essere abilitata in seguito al rilevamento di un problema con l'applicazione, quindi nuovamente disabilitata quando il problema viene risolto. Sono disponibili due modi per abilitare la traccia di debug per i flussi di lavoro: è possibile configurarla usando il visualizzatore di Traccia eventi oppure usare l'oggetto <xref:System.Diagnostics> per inviare eventi di traccia a un file.  
  
## <a name="enabling-debug-tracing-in-etw"></a>Abilitazione della traccia di debug in ETW  
 Per abilitare la traccia tramite ETW, abilitare il canale Debug in Visualizzatore eventi:  
  
1. Passare al nodo dei registri analitici e di debug in Visualizzatore eventi.  
  
2. Nella visualizzazione albero in Visualizzatore eventi passare a **Visualizzatore eventi -> applicazioni e servizi -> Microsoft -> Windows -> Server applicazioni-applicazioni**. Fare doppio clic su **Server applicazioni-applicazioni** e selezionare **Visualizza -> Visualizza registri analitici e Debug**. Fare doppio clic su **Debug** e selezionare **Attiva registro**.  
  
3. Quando un flusso di lavoro esegue il debug e le tracce vengono create nel canale di debug ETW, queste ultime possono essere visualizzate in Visualizzatore eventi. Passare a **Visualizzatore eventi -> applicazioni e servizi -> Microsoft -> Windows -> Server applicazioni-applicazioni**. Fare doppio clic su **Debug** e selezionare **aggiornare**.  
  
4. La dimensione del buffer di traccia analitica predefinita è solo 4 kilobyte (KB). Si consiglia di aumentare la dimensione a 32 KB. A tale scopo, eseguire i passaggi seguenti.  
  
    1. Eseguire il comando seguente nella directory del framework corrente (ad esempio, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2. Modifica il \<bufferSize > valore nel file ApplicationServer a 32.  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3. Eseguire il comando seguente nella directory del framework corrente (ad esempio, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
>  Se si usa .NET Framework 4 Client Profile, è innanzitutto necessario registrare il manifesto ETW eseguendo il comando seguente dalla directory di .NET Framework 4: `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a>Abilitazione della traccia di debug tramite l'oggetto System.Diagnostics  
 Questi listener possono essere configurati nel file App.config dell'applicazione flusso di lavoro o nel file Web.config per un servizio flusso di lavoro. In questo esempio, un [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424) configurata per salvare le informazioni di traccia nel file Mytracelog nella directory corrente.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Monitoraggio dell'infrastruttura di App di Windows Server](https://go.microsoft.com/fwlink/?LinkId=201273)
- [Monitoraggio delle applicazioni con App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
