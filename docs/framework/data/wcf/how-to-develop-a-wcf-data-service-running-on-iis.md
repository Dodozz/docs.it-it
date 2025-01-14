---
title: 'Procedura: Sviluppare un servizio dati WCF in esecuzione in IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: 74c31c748dd3483aa87afb2c9a7d926965c9f1ed
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64755603"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>Procedura: Sviluppare un servizio dati WCF in esecuzione in IIS

Questo argomento illustra come usare WCF Data Services per creare un servizio dati che si basa sul database di esempio Northwind ospitato da un'applicazione Web ASP.NET che è in esecuzione in Internet Information Services (IIS). Per un esempio di come creare lo stesso servizio dati Northwind come applicazione Web ASP.NET in esecuzione sul Server di sviluppo ASP.NET, vedere la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).

> [!NOTE]
> Per creare il servizio dati Northwind, è necessario installare il database di esempio Northwind nel computer locale. Per scaricare questo database di esempio, vedere la pagina di download dei [database di esempio per SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).

In questo argomento viene illustrato come creare un servizio dati tramite il provider di Entity Framework. Sono disponibili altri provider di servizi dati. Per altre informazioni, vedere [provider di servizi dati](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).

Dopo aver creato il servizio, è necessario fornire in modo esplicito l'accesso alle risorse del servizio dati. Per altre informazioni, vedere [Procedura: Abilitare l'accesso al servizio dati](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a>Creare l'applicazione web ASP.NET che viene eseguita in IIS

1. In Visual Studio sul **File** dal menu **New** > **progetto**.

2. Nel **nuovo progetto** finestra di dialogo, seleziona la **installati** > [**Visual C#**  o **Visual Basic**] > **Web**  categoria.

3. Selezionare il **applicazione Web ASP.NET** modello.

4. Immettere `NorthwindService` come il nome del progetto.

5. Fare clic su **OK**.

6. Nel **Project** dal menu **proprietà NorthwindService**.

7. Selezionare il **Web** scheda e quindi selezionare **Usa Server Web IIS locale**.

8. Fare clic su **crea Directory virtuale** e quindi fare clic su **OK**.

9. Dal prompt dei comandi aperto con privilegi di amministratore, eseguire uno dei comandi seguenti (a seconda del sistema operativo):

    - sistemi a 32 bit:

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - sistemi a 64 bit:

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     In questo modo viene effettuata la registrazione di Windows Communication Foundation (WCF) nel computer.

10. Dal prompt dei comandi aperto con privilegi di amministratore, eseguire uno dei comandi seguenti (a seconda del sistema operativo):

    - sistemi a 32 bit:

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - sistemi a 64 bit:

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     In questo modo viene verificato che l'esecuzione di IIS dopo che WCF è stato installato nel computer sia corretta. Può essere necessario inoltre riavviare IIS.

11. Quando l'applicazione ASP.NET è in esecuzione in IIS7, è necessario eseguire inoltre i passaggi seguenti:

    1. Aprire Gestione IIS e passare all'applicazione PhotoService sottoposta **sito Web predefinito**.

    2. Nelle **visualizzazione funzionalità**, fare doppio clic su **autenticazione**.

    3. Nel **Authentication** pagina, selezionare **autenticazione anonima**.

    4. Nel **azioni** riquadro, fare clic su **modificare** per impostare la sicurezza dell'entità in cui gli utenti anonimi si connetterà al sito.

    5. Nel **Modifica credenziali di autenticazione anonima** finestra di dialogo **identità pool di applicazioni**.

    > [!IMPORTANT]
    > Quando si usa l'account Servizio di rete, agli utenti anonimi viene concesso l'accesso completo alla rete interna associato a tale account.

12. Tramite SQL Server Management Studio, l'utilità sqlcmd.exe o l'Editor Transact-SQL eseguire il comando Transact-SQL seguente sull'istanza di SQL Server cui è collegato il database Northwind:

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    In questo modo nell'istanza di SQL Server viene creato un account di accesso per l'account di Windows usato per eseguire IIS. Ciò rende possibile la connessione di IIS all'istanza di SQL Server.

13. Con il database Northwind collegato eseguire i comandi Transact-SQL seguenti:

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    Vengono concessi i diritti al nuovo account di accesso per consentire a IIS la lettura e la scrittura dei dati nel database Northwind.

## <a name="define-the-data-model"></a>Definizione del modello di dati

1. Nelle **Esplora soluzioni**, fare doppio clic il nome del progetto ASP.NET e quindi fare clic su **Add** > **nuovo elemento**.

2. Nel **Aggiungi nuovo elemento** finestra di dialogo **ADO.NET Entity Data Model**.

3. Per il nome del modello di dati, digitare `Northwind.edmx`.

4. Nella procedura guidata Entity Data Model, selezionare **genera da Database**, quindi fare clic su **successivo**.

5. Connettere il modello di dati al database effettuando una delle operazioni seguenti e quindi fare clic su **successivo**:

    - Se non hai una connessione al database già configurata, fare clic su **nuova connessione** e creare una nuova connessione. Per altre informazioni, vedere [Procedura: Creare connessioni a database di SQL Server](https://go.microsoft.com/fwlink/?LinkId=123631). A questa istanza di SQL Server deve essere collegato il database Northwind di esempio.

         \- oppure -

    - Se si dispone di una connessione al database già configurata per connettersi al database Northwind, selezionarla dall'elenco delle connessioni.

6. Nella pagina finale della procedura guidata, selezionare le caselle di controllo relative a tutte le tabelle nel database e deselezionare le caselle di controllo relative a visualizzazioni e stored procedure.

7. Fare clic su **fine** per chiudere la procedura guidata.

## <a name="create-the-data-service"></a>Creazione del servizio dati

1. Nelle **Esplora soluzioni**, fare doppio clic il nome del progetto ASP.NET e quindi fare clic su **Add** > **nuovo elemento**.

2. Nel **Aggiungi nuovo elemento** finestra di dialogo **WCF Data Services**.

   ![Modello di elemento di WCF Data Services in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Il **di WCF Data Services** modello è disponibile in Visual Studio 2015, ma non in Visual Studio 2017.

3. Immettere il nome del servizio, `Northwind`.

     In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice. Nelle **Esplora soluzioni**, il servizio ha il nome, Northwind e l'estensione. svc.cs o. svc.

4. Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindEntities`. La definizione di classe dovrà essere analoga alla seguente:

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a>Vedere anche

- [Esposizione dei dati come un servizio](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
