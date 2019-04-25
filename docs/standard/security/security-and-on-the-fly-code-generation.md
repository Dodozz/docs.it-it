---
title: Sicurezza e generazione di codice immediata
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- code security, on-the-fly code generation
- on-the-fly code generation
- security [.NET Framework], on-the-fly code generation
- secure coding, on-the-fly code generation
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ffb1081c80c31353ad38080ae16ef9f8a74b5481
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61860542"
---
# <a name="security-and-on-the-fly-code-generation"></a><span data-ttu-id="5526d-102">Sicurezza e generazione di codice immediata</span><span class="sxs-lookup"><span data-stu-id="5526d-102">Security and On-the-Fly Code Generation</span></span>
<span data-ttu-id="5526d-103">Alcune librerie funzionano tramite la generazione e l'esecuzione di codice per eseguire alcune operazioni per il chiamante.</span><span class="sxs-lookup"><span data-stu-id="5526d-103">Some libraries operate by generating code and running it to perform some operation for the caller.</span></span> <span data-ttu-id="5526d-104">Il problema di fondo è costituito dalla generazione di codice per conto di codice meno attendibile e dalla relativa esecuzione con attendibilità superiore</span><span class="sxs-lookup"><span data-stu-id="5526d-104">The basic problem is generating code on behalf of lesser-trust code and running it at a higher trust.</span></span> <span data-ttu-id="5526d-105">e diventa più grave quando il chiamante è in grado di influenzare la generazione di codice, per cui è necessario che venga generato solo codice sicuro.</span><span class="sxs-lookup"><span data-stu-id="5526d-105">The problem worsens when the caller can influence code generation, so you must ensure that only code you consider safe is generated.</span></span>  
  
 <span data-ttu-id="5526d-106">È preferibile sapere esattamente quale tipo di codice si genera in ogni momento;</span><span class="sxs-lookup"><span data-stu-id="5526d-106">You need to know exactly what code you are generating at all times.</span></span> <span data-ttu-id="5526d-107">in altre parole, è necessario avere un controllo totale sui valori ottenuti da un utente, che si tratti di stringhe racchiuse tra virgolette, che devono essere sottoposte a escape per evitare che includano elementi di codice non previsti, identificatori, di cui è necessario verificare la validità, o altri elementi.</span><span class="sxs-lookup"><span data-stu-id="5526d-107">This means that you must have strict controls on any values that you get from a user, be they quote-enclosed strings (which should be escaped so they cannot include unexpected code elements), identifiers (which should be checked to verify that they are valid identifiers), or anything else.</span></span> <span data-ttu-id="5526d-108">Gli identificatori possono rappresentare un pericolo in quanto la modifica di un assembly compilato può determinare la comparsa di caratteri insoliti negli identificatori, che ne possono provocare il blocco; questa condizione, tuttavia, costituisce raramente una vulnerabilità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5526d-108">Identifiers can be dangerous because a compiled assembly can be modified so that its identifiers contain strange characters, which will probably break it (although this is rarely a security vulnerability).</span></span>  
  
 <span data-ttu-id="5526d-109">È preferibile generare codice tramite la reflection emit, che spesso consente di evitare gran parte di questi problemi.</span><span class="sxs-lookup"><span data-stu-id="5526d-109">It is recommended that you generate code with reflection emit, which often helps you avoid many of these problems.</span></span>  
  
 <span data-ttu-id="5526d-110">Durante la compilazione del codice, stabilire se un programma dannoso è in grado di modificarlo.</span><span class="sxs-lookup"><span data-stu-id="5526d-110">When you compile the code, consider whether there is some way a malicious program could modify it.</span></span> <span data-ttu-id="5526d-111">In un lasso di tempo molto breve, il codice dannoso può modificare il codice sorgente sul disco prima che il compilatore sia in grado di leggerlo o prima che sia possibile caricare nel codice il file DLL.</span><span class="sxs-lookup"><span data-stu-id="5526d-111">Is there a small window of time during which malicious code can change source code on disk before the compiler reads it or before your code loads the .dll file?</span></span> <span data-ttu-id="5526d-112">In questo caso è necessario proteggere la directory che contiene file di questo tipo tramite un elenco di controllo di accesso (ACL), se necessario.</span><span class="sxs-lookup"><span data-stu-id="5526d-112">If so, you must protect the directory containing these files, using an Access Control List in the file system, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5526d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5526d-113">See also</span></span>

- [<span data-ttu-id="5526d-114">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="5526d-114">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
