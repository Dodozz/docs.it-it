---
title: Comando dotnet msbuild - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 76165590478b0e76d19d546c87e012da4716b6db
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583718"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="a870f-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="a870f-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a870f-104">nome</span><span class="sxs-lookup"><span data-stu-id="a870f-104">Name</span></span>

<span data-ttu-id="a870f-105">`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="a870f-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a870f-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a870f-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="a870f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a870f-107">Description</span></span>

<span data-ttu-id="a870f-108">Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a870f-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="a870f-109">Il comando ha le stesse funzionalità del client della riga di comando di MSBuild esistente.</span><span class="sxs-lookup"><span data-stu-id="a870f-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="a870f-110">Le opzioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="a870f-110">The options are all the same.</span></span> <span data-ttu-id="a870f-111">Per altre informazioni sulle opzioni disponibili, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="a870f-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="examples"></a><span data-ttu-id="a870f-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="a870f-112">Examples</span></span>

<span data-ttu-id="a870f-113">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="a870f-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="a870f-114">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="a870f-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild -p:Configuration=Release`

<span data-ttu-id="a870f-115">Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="a870f-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="a870f-116">Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:</span><span class="sxs-lookup"><span data-stu-id="a870f-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild -pp`
