---
title: Creazione di listener di log personalizzati (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
ms.openlocfilehash: 50eb1bc1588602bf562efc31b0f4dd01bc29cad0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593324"
---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a>Procedura dettagliata: Creazione di listener di log personalizzati (Visual Basic)
Questa procedura spiega come creare un listener di log personalizzato e configurarlo in modo che resti in ascolto dell'output dell'oggetto `My.Application.Log`.  
  
## <a name="getting-started"></a>Introduzione  
 I listener di log devono ereditare dalla <xref:System.Diagnostics.TraceListener> classe.  
  
#### <a name="to-create-the-listener"></a>Per creare il listener  
  
- Nell'applicazione creare una classe denominata `SimpleListener` che eredita da <xref:System.Diagnostics.TraceListener>.  
  
     [!code-vb[VbVbalrMyApplicationLog#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#16)]  
  
     I metodi <xref:System.Diagnostics.TraceListener.Write%2A> e <xref:System.Diagnostics.TraceListener.WriteLine%2A>, richiesti dalla classe di base, chiamano `MsgBox` per visualizzare l'input.  
  
     L'attributo <xref:System.Security.Permissions.HostProtectionAttribute> viene applicato ai metodi <xref:System.Diagnostics.TraceListener.Write%2A> e <xref:System.Diagnostics.TraceListener.WriteLine%2A> in modo che i relativi attributi corrispondano ai metodi della classe di base. L'attributo <xref:System.Security.Permissions.HostProtectionAttribute> consente all'host che esegue il codice di determinare se il codice espone la sincronizzazione con protezione host.  
  
    > [!NOTE]
    >  L'attributo <xref:System.Security.Permissions.HostProtectionAttribute> ha effetto solo su applicazioni non gestite che ospitano Common Language Runtime e implementano la protezione host, ad esempio SQL Server.  
  
 Per assicurarsi che `My.Application.Log` usi il listener di log, assegnare un nome sicuro all'assembly che contiene il listener di log.  
  
 La procedura seguente prevede alcuni semplici passaggi per la creazione di un assembly di listener di log con nome sicuro. Per altre informazioni, vedere [Creazione e utilizzo degli assembly con nome sicuro](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md).  
  
#### <a name="to-strongly-name-the-log-listener-assembly"></a>Per assegnare un nome sicuro all'assembly di listener di log  
  
1. Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.   
  
2. Fare clic sulla scheda **Firma**.  
  
3. Selezionare la casella **Firma assembly**.  
  
4. Selezionare **\<Nuovo>** dall'elenco a discesa **Scegli un file chiave con nome sicuro**.  
  
     Si aprirà la finestra di dialogo **Crea chiave con nome sicuro** .  
  
5. Specificare un nome per il file di chiave nella casella **Nome file di chiave**.  
  
6. Digitare una password nelle caselle **Immettere la password** e **Conferma password**.  
  
7. Fare clic su **OK**.  
  
8. Ricompilare l'applicazione.  
  
## <a name="adding-the-listener"></a>Aggiungere il listener  
 Ora che l'assembly ha un nome sicuro è necessario determinare il nome sicuro del listener in modo che `My.Application.Log` usi il listener di log.  
  
 Il formato di un tipo con nome sicuro è il seguente.  
  
 \<nome tipo>, \<nome assembly>, \<numero versione>, \<impostazioni cultura>, \<nome sicuro>  
  
#### <a name="to-determine-the-strong-name-of-the-listener"></a>Per determinare il nome sicuro del listener  
  
- Il codice seguente illustra come determinare il nome sicuro del tipo per `SimpleListener`.  
  
     [!code-vb[VbVbalrMyApplicationLog#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#17)]  
  
     Il nome sicuro del tipo dipende dal progetto.  
  
 Con il nome sicuro è possibile aggiungere il listener alla raccolta di listener di log `My.Application.Log`.  
  
#### <a name="to-add-the-listener-to-myapplicationlog"></a>Per aggiungere il listener a My.Application.Log  
  
1. Fare clic con il pulsante destro del mouse su app.config in **Esplora soluzioni** e scegliere **Apri**.  
  
     -oppure-  
  
     Se non è presente un file app.config:  
  
    1. Scegliere **Aggiungi nuovo elemento** dal menu **Progetto**.  
  
    2. Nella finestra di dialogo **Aggiungi nuovo elemento** scegliere **File di configurazione dell'applicazione**.  
  
    3. Fare clic su **Aggiungi**.  
  
2. Individuare la sezione `<listeners>` all'interno della sezione `<source>` con l'attributo `name` "DefaultSource" che si trova nella sezione `<sources>` . La sezione `<sources>` si trova nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .  
  
3. Aggiungere l'elemento seguente alla sezione `<listeners>`:  
  
    ```xml  
    <add name="SimpleLog" />  
    ```  
  
4. Individuare la sezione `<sharedListeners>` nella sezione `<system.diagnostics>` all'interno della sezione di primo livello `<configuration>` .  
  
5. Aggiungere l'elemento seguente alla sezione `<sharedListeners>` :  
  
    ```xml  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     Modificare il valore di `SimpleLogStrongName` in modo che sia il nome sicuro del listener.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Procedura: Registrare eccezioni](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [Procedura: Scrivere messaggi di log](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
