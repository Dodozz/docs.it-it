---
title: '&lt;deselezionare&gt; (elemento) per &lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bc52e3149c213925ea64a8421ee65befeea4161e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184218"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="9e56f-102">\<Cancella > (elemento) per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="9e56f-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="9e56f-103">Cancella le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9e56f-103">Clears custom application settings.</span></span>

<span data-ttu-id="9e56f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="9e56f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="9e56f-105">&nbsp;&nbsp;[**\<appSettings >**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="9e56f-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="9e56f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear >**</span><span class="sxs-lookup"><span data-stu-id="9e56f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9e56f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e56f-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="9e56f-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="9e56f-108">Attributes</span></span>

<span data-ttu-id="9e56f-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="9e56f-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="9e56f-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="9e56f-110">Parent element</span></span>

|     | <span data-ttu-id="9e56f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e56f-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9e56f-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="9e56f-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="9e56f-113">Contiene le impostazioni dell'applicazione personalizzata, ad esempio i percorsi dei file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9e56f-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9e56f-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9e56f-114">Child elements</span></span>

<span data-ttu-id="9e56f-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="9e56f-115">None</span></span>

## <a name="example"></a><span data-ttu-id="9e56f-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e56f-116">Example</span></span>

<span data-ttu-id="9e56f-117">Nell'esempio seguente illustra come cancellare le impostazioni di configurazione personalizzato:</span><span class="sxs-lookup"><span data-stu-id="9e56f-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="9e56f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e56f-118">See also</span></span>

- [<span data-ttu-id="9e56f-119">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9e56f-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
