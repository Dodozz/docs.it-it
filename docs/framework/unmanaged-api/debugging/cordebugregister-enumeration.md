---
title: Enumerazione CorDebugRegister
ms.date: 03/30/2017
api_name:
- CorDebugRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugRegister
helpviewer_keywords:
- CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fab5225225d4e4a4e07961b0f967cff2c1b07321
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599318"
---
# <a name="cordebugregister-enumeration"></a><span data-ttu-id="e784d-102">Enumerazione CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="e784d-102">CorDebugRegister Enumeration</span></span>
<span data-ttu-id="e784d-103">Specifica i registri associati a un'architettura di processore specifica.</span><span class="sxs-lookup"><span data-stu-id="e784d-103">Specifies the registers associated with a given processor architecture.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e784d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e784d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRegister {  
  
    REGISTER_INSTRUCTION_POINTER = 0,  
    REGISTER_STACK_POINTER,  
    REGISTER_FRAME_POINTER,  
  
    REGISTER_X86_EIP = 0,  
    REGISTER_X86_ESP,  
    REGISTER_X86_EBP,  
  
    REGISTER_X86_EAX,  
    REGISTER_X86_ECX,  
    REGISTER_X86_EDX,  
    REGISTER_X86_EBX,  
  
    REGISTER_X86_ESI,  
    REGISTER_X86_EDI,  
  
    REGISTER_X86_FPSTACK_0,  
    REGISTER_X86_FPSTACK_1,  
    REGISTER_X86_FPSTACK_2,  
    REGISTER_X86_FPSTACK_3,  
    REGISTER_X86_FPSTACK_4,  
    REGISTER_X86_FPSTACK_5,  
    REGISTER_X86_FPSTACK_6,  
    REGISTER_X86_FPSTACK_7,  
  
    REGISTER_AMD64_RIP = 0,  
    REGISTER_AMD64_RSP,  
    REGISTER_AMD64_RBP,  
    REGISTER_AMD64_RAX,  
    REGISTER_AMD64_RCX,  
    REGISTER_AMD64_RDX,  
    REGISTER_AMD64_RBX,  
    REGISTER_AMD64_RSI,  
    REGISTER_AMD64_RDI,  
    REGISTER_AMD64_R8,  
    REGISTER_AMD64_R9,  
    REGISTER_AMD64_R10,  
    REGISTER_AMD64_R11,  
    REGISTER_AMD64_R12,  
    REGISTER_AMD64_R13,  
    REGISTER_AMD64_R14,  
    REGISTER_AMD64_R15,  
  
    REGISTER_AMD64_XMM0,  
    REGISTER_AMD64_XMM1,  
    REGISTER_AMD64_XMM2,  
    REGISTER_AMD64_XMM3,  
    REGISTER_AMD64_XMM4,  
    REGISTER_AMD64_XMM5,  
    REGISTER_AMD64_XMM6,  
    REGISTER_AMD64_XMM7,  
    REGISTER_AMD64_XMM8,  
    REGISTER_AMD64_XMM9,  
    REGISTER_AMD64_XMM10,  
    REGISTER_AMD64_XMM11,  
    REGISTER_AMD64_XMM12,  
    REGISTER_AMD64_XMM13,  
    REGISTER_AMD64_XMM14,  
    REGISTER_AMD64_XMM15,  
  
    REGISTER_IA64_BSP = REGISTER_FRAME_POINTER,  
    REGISTER_IA64_R0  = REGISTER_IA64_BSP + 1,  
    REGISTER_IA64_F0  = REGISTER_IA64_R0  + 128,  
    REGISTER_ARM_PC = 0,  
    REGISTER_ARM_SP,  
    REGISTER_ARM_R0,  
    REGISTER_ARM_R1,  
    REGISTER_ARM_R2,  
    REGISTER_ARM_R3,  
    REGISTER_ARM_R4,  
    REGISTER_ARM_R5,  
    REGISTER_ARM_R6,  
    REGISTER_ARM_R7,  
    REGISTER_ARM_R8,  
    REGISTER_ARM_R9,  
    REGISTER_ARM_R10,  
    REGISTER_ARM_R11,  
    REGISTER_ARM_R12,  
    REGISTER_ARM_LR,  
  
} CorDebugRegister;  
```  
  
## <a name="members"></a><span data-ttu-id="e784d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e784d-105">Members</span></span>  
  
|<span data-ttu-id="e784d-106">Member</span><span class="sxs-lookup"><span data-stu-id="e784d-106">Member</span></span>|<span data-ttu-id="e784d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e784d-107">Description</span></span>|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|<span data-ttu-id="e784d-108">Un registro dei puntatori alle istruzioni in qualsiasi processore.</span><span class="sxs-lookup"><span data-stu-id="e784d-108">An instruction pointer register on any processor.</span></span>|  
|`REGISTER_STACK_POINTER`|<span data-ttu-id="e784d-109">Un registro dei puntatori agli stack in qualsiasi processore.</span><span class="sxs-lookup"><span data-stu-id="e784d-109">A stack pointer register on any processor.</span></span>|  
|`REGISTER_FRAME_POINTER`|<span data-ttu-id="e784d-110">Registro dei puntatori ai frame in qualsiasi processore.</span><span class="sxs-lookup"><span data-stu-id="e784d-110">A frame pointer register on any processor.</span></span>|  
|`REGISTER_X86_EIP`|<span data-ttu-id="e784d-111">Registro dei puntatori alle istruzioni nel processore x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-111">The instruction pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESP`|<span data-ttu-id="e784d-112">Registro dei puntatori agli stack nel processore x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-112">The stack pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBP`|<span data-ttu-id="e784d-113">Registro dei puntatori di base nel processore x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-113">The base pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EAX`|<span data-ttu-id="e784d-114">Registro dei dati A nel processore x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-114">The A data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ECX`|<span data-ttu-id="e784d-115">Registro dei dati C nel processore x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-115">The C data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDX`|<span data-ttu-id="e784d-116">Registro dei dati D nel processore x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-116">The D data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBX`|<span data-ttu-id="e784d-117">Registro dei dati B nel processore x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-117">The B data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESI`|<span data-ttu-id="e784d-118">Registro dell'indice di origine nel processore x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-118">The source index register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDI`|<span data-ttu-id="e784d-119">Registro dell'indice di destinazione nel processore x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-119">The destination index register on the x86 processor.</span></span>|  
|`REGISTER_X86_FPSTACK_0`|<span data-ttu-id="e784d-120">Registro dello stack 0 nel processore a virgola mobile x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-120">The stack register 0 on the x86 floating-point (FP) processor.</span></span>|  
|`REGISTER_X86_FPSTACK_1`|<span data-ttu-id="e784d-121">Registro dello stack 1 nel processore a virgola mobile x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-121">The #1 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_2`|<span data-ttu-id="e784d-122">Registro dello stack 2 nel processore a virgola mobile x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-122">The #2 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_3`|<span data-ttu-id="e784d-123">Registro dello stack 3 nel processore a virgola mobile x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-123">The #3 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_4`|<span data-ttu-id="e784d-124">Registro dello stack 4 nel processore a virgola mobile x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-124">The #4 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_5`|<span data-ttu-id="e784d-125">Registro dello stack 5 nel processore a virgola mobile x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-125">The #5 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_6`|<span data-ttu-id="e784d-126">Registro dello stack 6 nel processore a virgola mobile x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-126">The #6 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_7`|<span data-ttu-id="e784d-127">Registro dello stack 7 nel processore a virgola mobile x86.</span><span class="sxs-lookup"><span data-stu-id="e784d-127">The #7 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_AMD64_RIP`|<span data-ttu-id="e784d-128">Registro dei puntatori alle istruzioni nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-128">The instruction pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSP`|<span data-ttu-id="e784d-129">Registro dei puntatori agli stack nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-129">The stack pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBP`|<span data-ttu-id="e784d-130">Registro dei puntatori di base nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-130">The base pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RAX`|<span data-ttu-id="e784d-131">Registro dei dati A nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-131">The A data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RCX`|<span data-ttu-id="e784d-132">Registro dei dati C nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-132">The C data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDX`|<span data-ttu-id="e784d-133">Registro dei dati D nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-133">The D data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBX`|<span data-ttu-id="e784d-134">Registro dei dati B nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-134">The B data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSI`|<span data-ttu-id="e784d-135">Registro dell'indice di origine nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-135">The source index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDI`|<span data-ttu-id="e784d-136">Registro dell'indice di destinazione nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-136">The destination index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R8`|<span data-ttu-id="e784d-137">Registro dei dati 8 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-137">The #8 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R9`|<span data-ttu-id="e784d-138">Registro dei dati 9 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-138">The #9 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R10`|<span data-ttu-id="e784d-139">Registro dei dati 10 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-139">The #10 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R11`|<span data-ttu-id="e784d-140">Registro dei dati 11 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-140">The #11 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R12`|<span data-ttu-id="e784d-141">Registro dei dati 12 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-141">The #12 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R13`|<span data-ttu-id="e784d-142">Registro dei dati 13 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-142">The #13 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R14`|<span data-ttu-id="e784d-143">Registro dei dati 14 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-143">The #14 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R15`|<span data-ttu-id="e784d-144">Registro dei dati 15 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-144">The #15 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM0`|<span data-ttu-id="e784d-145">Registro dei dati multimediali 0 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-145">The #0 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM1`|<span data-ttu-id="e784d-146">Registro dei dati multimediali 1 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-146">The #1 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM2`|<span data-ttu-id="e784d-147">Registro dei dati multimediali 2 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-147">The #2 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM3`|<span data-ttu-id="e784d-148">Registro dei dati multimediali 3 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-148">The #3 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM4`|<span data-ttu-id="e784d-149">Registro dei dati multimediali 4 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-149">The #4 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM5`|<span data-ttu-id="e784d-150">Registro dei dati multimediali 5 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-150">The #5 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM6`|<span data-ttu-id="e784d-151">Registro dei dati multimediali 6 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-151">The #6 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM7`|<span data-ttu-id="e784d-152">Registro dei dati multimediali 7 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-152">The #7 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM8`|<span data-ttu-id="e784d-153">Registro dei dati multimediali 8 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-153">The #8 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM9`|<span data-ttu-id="e784d-154">Registro dei dati multimediali 9 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-154">The #9 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM10`|<span data-ttu-id="e784d-155">Registro dei dati multimediali 10 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-155">The #10 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM11`|<span data-ttu-id="e784d-156">Registro dei dati multimediali 11 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-156">The #11 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM12`|<span data-ttu-id="e784d-157">Registro dei dati multimediali 12 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-157">The #12 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM13`|<span data-ttu-id="e784d-158">Registro dei dati multimediali 13 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-158">The #13 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM14`|<span data-ttu-id="e784d-159">Registro dei dati multimediali 14 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-159">The #14 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM15`|<span data-ttu-id="e784d-160">Registro dei dati multimediali 15 nel processore AMD64.</span><span class="sxs-lookup"><span data-stu-id="e784d-160">The #15 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_IA64_BSP`|<span data-ttu-id="e784d-161">Registro dei puntatori agli stack nel processore IA-64.</span><span class="sxs-lookup"><span data-stu-id="e784d-161">The stack pointer register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_R0`|<span data-ttu-id="e784d-162">Registro dei dati 0 nel processore IA-64.</span><span class="sxs-lookup"><span data-stu-id="e784d-162">The #0 data register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_F0`|<span data-ttu-id="e784d-163">Registro dei dati a virgola mobile 0 nel processore IA-64.</span><span class="sxs-lookup"><span data-stu-id="e784d-163">The #0 FP data register on the IA-64 processor.</span></span>|  
|`REGISTER_ARM_PC`|<span data-ttu-id="e784d-164">Registro dei contatori di programma (R15) nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-164">The program counter register (R15) on the ARM processor.</span></span>|  
|`REGISTER_ARM_SP`|<span data-ttu-id="e784d-165">Registro dei puntatori agli stack (R13) nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-165">The stack pointer register (R13) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R0`|<span data-ttu-id="e784d-166">Registro dei dati R0 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-166">Data register R0 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R1`|<span data-ttu-id="e784d-167">Registro dei dati R1 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-167">Data register R1 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R2`|<span data-ttu-id="e784d-168">Registro dei dati R2 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-168">Data register R2 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R3`|<span data-ttu-id="e784d-169">Registro dei dati R3 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-169">Data register R3 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R4`|<span data-ttu-id="e784d-170">Registro R4 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-170">Register R4 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R5`|<span data-ttu-id="e784d-171">Registro R5 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-171">Register R5 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R6`|<span data-ttu-id="e784d-172">Registro R6 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-172">Register R6 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R7`|<span data-ttu-id="e784d-173">Registro R7 (puntatore ai frame THUMB) nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-173">Register R7 (the THUMB frame pointer) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R8`|<span data-ttu-id="e784d-174">Registro R8 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-174">Register R8 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R9`|<span data-ttu-id="e784d-175">Registro R9 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-175">Register R9 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R10`|<span data-ttu-id="e784d-176">Registro R10 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-176">Register R10 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R11`|<span data-ttu-id="e784d-177">Puntatore ai frame nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-177">The frame pointer on the ARM processor.</span></span>|  
|`REGISTER_ARM_R12`|<span data-ttu-id="e784d-178">Registro R12 nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-178">Register R12 on the ARM processor.</span></span>|  
|`REGISTER_ARM_LR`|<span data-ttu-id="e784d-179">Registro dei collegamenti (R14) nel processore ARM.</span><span class="sxs-lookup"><span data-stu-id="e784d-179">The link register (R14) on the ARM processor.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e784d-180">Note</span><span class="sxs-lookup"><span data-stu-id="e784d-180">Remarks</span></span>  
 <span data-ttu-id="e784d-181">Esistono 128 registri dei dati per l'utilizzo generico e 128 registri dei dati a virgola mobile nel processore IA-64, ma vengono forniti solo i valori `REGISTER_IA64_R0` e `REGISTER_IA64_F0`.</span><span class="sxs-lookup"><span data-stu-id="e784d-181">There are 128 general-purpose data registers and 128 floating-point data registers on the IA-64 processor, but only values `REGISTER_IA64_R0` and `REGISTER_IA64_F0` are provided.</span></span> <span data-ttu-id="e784d-182">Gli altri valori possono essere determinati come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="e784d-182">The other values can be determined as follows:</span></span>  
  
- <span data-ttu-id="e784d-183">Aggiungere il numero del registro a `REGISTER_IA64_R0` per i valori da `REGISTER_IA64_R1` a `REGISTER_IA64_R127`, che corrispondono al registro dei dati dal numero 1 al numero 127 nel processore IA-64.</span><span class="sxs-lookup"><span data-stu-id="e784d-183">Add the register number to `REGISTER_IA64_R0` for values `REGISTER_IA64_R1` through `REGISTER_IA64_R127`, which correspond to the #1 data register through the #127 data register on the IA-64 processor.</span></span>  
  
- <span data-ttu-id="e784d-184">Aggiungere il numero del registro a `REGISTER_IA64_F0` per i valori da `REGISTER_IA64_F1` a `REGISTER_IA64_F127`, che corrispondono al registro dei dati a virgola mobile dal numero 1 al numero 127 nel processore IA-64.</span><span class="sxs-lookup"><span data-stu-id="e784d-184">Add the register number to `REGISTER_IA64_F0` for values `REGISTER_IA64_F1` through `REGISTER_IA64_F127`, which correspond to the #1 FP data register through the #127 FP data register on the IA-64 processor.</span></span>  
  
 <span data-ttu-id="e784d-185">Ad esempio, se occorre specificare il registro dei dati 83 nel processore IA-64, usare `REGISTER_IA64_R0` + 83.</span><span class="sxs-lookup"><span data-stu-id="e784d-185">For example, if you need to specify the #83 data register on the IA-64 processor, use `REGISTER_IA64_R0` + 83.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e784d-186">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e784d-186">Requirements</span></span>  
 <span data-ttu-id="e784d-187">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e784d-187">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e784d-188">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e784d-188">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e784d-189">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e784d-189">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e784d-190">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e784d-190">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e784d-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e784d-191">See also</span></span>

- [<span data-ttu-id="e784d-192">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="e784d-192">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
