---
title: Pool di connessioni
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: 4cba53993489f51ed39ac52bff4fa252beb9aafd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61880018"
---
# <a name="connection-pooling"></a><span data-ttu-id="da3a1-102">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="da3a1-102">Connection Pooling</span></span>
<span data-ttu-id="da3a1-103">La connessione a un'origine dati può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="da3a1-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="da3a1-104">Per ridurre al minimo il costo dell'apertura delle connessioni, ADO.NET usa una tecnica di ottimizzazione denominata *pool di connessioni*, che consente di ridurre il costo dell'apertura e chiusura delle connessioni ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="da3a1-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="da3a1-105">Per i provider di dati .NET Framework il pool di connessioni viene gestito in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="da3a1-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da3a1-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="da3a1-106">In This Section</span></span>  
 [<span data-ttu-id="da3a1-107">Pool di connessioni SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="da3a1-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="da3a1-108">Fornisce una panoramica dei pool di connessioni e viene descritto l'utilizzo del pool di connessioni in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da3a1-108">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="da3a1-109">Pool di connessioni OLE DB, ODBC e Oracle</span><span class="sxs-lookup"><span data-stu-id="da3a1-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="da3a1-110">Viene descritto l'uso del pool di connessioni con i provider di dati .NET Framework per OLE DB, ODBC e Oracle.</span><span class="sxs-lookup"><span data-stu-id="da3a1-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3a1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da3a1-111">See also</span></span>

- [<span data-ttu-id="da3a1-112">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="da3a1-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="da3a1-113">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="da3a1-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
