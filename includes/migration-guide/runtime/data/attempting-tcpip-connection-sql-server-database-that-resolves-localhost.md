---
ms.openlocfilehash: 88d6c166acf9e9ab72c2713b575a8453779f70d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774166"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a `localhost` non riesce

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6 e 4.6.1, il tentativo di connessione TCP/IP a un database di SQL Server corrispondente a <code>localhost</code> ha esito negativo con l'errore &quot;Si è verificato un errore di rete o specifico dell'istanza mentre si cercava di stabilire una connessione con SQL Server. Il server non è stato trovato o non è accessibile. Verificare che il nome dell'istanza sia corretto e che SQL Server sia configurato in modo da consentire connessioni remote. (provider: Interfacce di rete SQL, errore: 26 - Errore nell'individuazione del server/dell'istanza specificati)&quot;|
|Suggerimento|Questo problema è stato risolto ed è stato ripristinato il comportamento precedente in .NET Framework 4.6.2. Per connettersi a un database di SQL Server corrispondente a <code>localhost</code>, eseguire l'aggiornamento a .NET Framework 4.6.2.|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Runtime|
