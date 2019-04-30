---
title: Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione
ms.date: 03/30/2017
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
ms.openlocfilehash: b4578a030300872bf4e0bab30b8daf12544be0cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032773"
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="2a1ed-102">Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="2a1ed-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="2a1ed-103">Per impostazione predefinita, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene generato codice SQL dinamico per implementare le operazioni di inserimento, lettura, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="2a1ed-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="2a1ed-104">In pratica, tuttavia, l'applicazione viene in genere personalizzata per soddisfare specifiche esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="2a1ed-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a1ed-105">Se si usa Visual Studio, è possibile usare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per personalizzare l'inserimento, aggiornamento ed eliminazione di azioni.</span><span class="sxs-lookup"><span data-stu-id="2a1ed-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="2a1ed-106">Negli argomenti di questa sezione vengono descritte le tecniche offerte da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per personalizzare le operazioni di inserimento, lettura, aggiornamento ed eliminazione in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a1ed-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a1ed-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="2a1ed-107">In This Section</span></span>  
 [<span data-ttu-id="2a1ed-108">Personalizzazione di operazioni: panoramica</span><span class="sxs-lookup"><span data-stu-id="2a1ed-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="2a1ed-109">Vengono descritte le diverse tecniche fornite da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per personalizzare le operazioni di inserimento, lettura, aggiornamento ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="2a1ed-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="2a1ed-110">Operazioni di inserimento, aggiornamento ed eliminazione</span><span class="sxs-lookup"><span data-stu-id="2a1ed-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="2a1ed-111">Vengono descritti i processi predefiniti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per la modifica dei dati del database.</span><span class="sxs-lookup"><span data-stu-id="2a1ed-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="2a1ed-112">Responsabilità dello sviluppatore nell'override del comportamento predefinito</span><span class="sxs-lookup"><span data-stu-id="2a1ed-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="2a1ed-113">Viene descritto il ruolo dello sviluppatore nell'implementazione dei requisiti non applicati da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a1ed-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="2a1ed-114">Aggiunta di logica di business mediante metodi parziali</span><span class="sxs-lookup"><span data-stu-id="2a1ed-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="2a1ed-115">Viene descritto come usare metodi parziali per eseguire l'override dei metodi generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2a1ed-115">Describes how to use partial methods to override autogenerated methods.</span></span>
