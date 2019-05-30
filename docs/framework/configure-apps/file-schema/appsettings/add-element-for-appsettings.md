---
title: Elemento <add> per <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: f8b426dc0e1e180afbfccce50d3b45774991a572
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301346"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="f1e5d-102">\<aggiungere > (elemento) per \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="f1e5d-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="f1e5d-103">Aggiunge un'impostazione personalizzata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f1e5d-103">Adds a custom application setting.</span></span>

<span data-ttu-id="f1e5d-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f1e5d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="f1e5d-105">&nbsp;&nbsp;[ **\<appSettings >** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f1e5d-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="f1e5d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="f1e5d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f1e5d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1e5d-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="f1e5d-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="f1e5d-108">Attributes</span></span>

|           | <span data-ttu-id="f1e5d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1e5d-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f1e5d-110">**key**</span><span class="sxs-lookup"><span data-stu-id="f1e5d-110">**key**</span></span>   | <span data-ttu-id="f1e5d-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f1e5d-111">Required attribute.</span></span><br><br><span data-ttu-id="f1e5d-112">Specifica il nome della chiave da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="f1e5d-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="f1e5d-113">**value**</span><span class="sxs-lookup"><span data-stu-id="f1e5d-113">**value**</span></span> | <span data-ttu-id="f1e5d-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f1e5d-114">Required attribute.</span></span><br><br><span data-ttu-id="f1e5d-115">Specifica il valore della chiave da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="f1e5d-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f1e5d-116">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="f1e5d-116">Parent element</span></span>

|     | <span data-ttu-id="f1e5d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1e5d-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f1e5d-118"> *\*\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="f1e5d-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="f1e5d-119">Contiene le impostazioni dell'applicazione personalizzate, ad esempio i percorsi di file, gli URL del servizio Web XML o qualsiasi altra informazione di configurazione personalizzata per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f1e5d-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f1e5d-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f1e5d-120">Child elements</span></span>

<span data-ttu-id="f1e5d-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="f1e5d-121">None</span></span>

## <a name="example"></a><span data-ttu-id="f1e5d-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1e5d-122">Example</span></span>

<span data-ttu-id="f1e5d-123">Nell'esempio seguente viene illustrato come aggiungere un'impostazione di configurazione personalizzati per il nome dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="f1e5d-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="f1e5d-124">L'esempio seguente usa il `<add>` elemento per definire due impostazioni di compatibilità in un'applicazione ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="f1e5d-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="f1e5d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1e5d-125">See also</span></span>

- [<span data-ttu-id="f1e5d-126">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f1e5d-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
