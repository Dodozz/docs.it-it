---
title: Implementazione di applicazioni resilienti
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Implementazione di applicazioni resilienti
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: ec79221f0238d61f1ca1b2b7c58b1e16be7f4df4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130794"
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="4e18e-103">Implementazione di applicazioni resilienti</span><span class="sxs-lookup"><span data-stu-id="4e18e-103">Implementing Resilient Applications</span></span>

<span data-ttu-id="4e18e-104">*Le applicazioni basate su microservizi e cloud devono essere in grado di gestire gli errori parziali che sicuramente si verificheranno. È necessario progettare l'applicazione in modo che sia resiliente a questi errori parziali.*</span><span class="sxs-lookup"><span data-stu-id="4e18e-104">*Your microservice and cloud-based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="4e18e-105">La resilienza è la capacità di correggere gli errori e continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="4e18e-105">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="4e18e-106">Non significa evitare gli errori, ma accettare il fatto che si verificheranno e trovare una modalità di gestione degli errori che eviti tempi di inattività o perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="4e18e-106">It is not about avoiding failures but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="4e18e-107">L'obiettivo della resilienza è riportare l'applicazione in uno stato pienamente operativo dopo un errore.</span><span class="sxs-lookup"><span data-stu-id="4e18e-107">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="4e18e-108">È piuttosto difficoltoso progettare e distribuire un'applicazione basata su microservizi.</span><span class="sxs-lookup"><span data-stu-id="4e18e-108">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="4e18e-109">Ma è anche necessario mantenere l'applicazione in esecuzione in un ambiente in cui è certo che si verifichi un determinato tipo di errori.</span><span class="sxs-lookup"><span data-stu-id="4e18e-109">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="4e18e-110">Pertanto, l'applicazione deve essere resiliente.</span><span class="sxs-lookup"><span data-stu-id="4e18e-110">Therefore, your application should be resilient.</span></span> <span data-ttu-id="4e18e-111">Deve essere progettata per gestire errori parziali, ad esempio interruzioni della rete o arresti anomali di nodi o macchine virtuali nel cloud.</span><span class="sxs-lookup"><span data-stu-id="4e18e-111">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="4e18e-112">Anche lo spostamento di microservizi (contenitori) in un nodo diverso all'interno di un cluster può causare brevi errori intermittenti nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4e18e-112">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="4e18e-113">I diversi componenti singoli dell'applicazione devono inoltre incorporare le funzionalità di monitoraggio dell'integrità.</span><span class="sxs-lookup"><span data-stu-id="4e18e-113">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="4e18e-114">Seguendo le indicazioni riportate in questo capitolo, è possibile creare un'applicazione in grado di funzionare senza problemi malgrado tempi di inattività temporanei o le normali interruzioni che si verificano nelle distribuzioni complesse e basate su cloud.</span><span class="sxs-lookup"><span data-stu-id="4e18e-114">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4e18e-115">[Precedente](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[Successivo](handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="4e18e-115">[Previous](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Next](handle-partial-failure.md)</span></span>