---
title: -codepage (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 7cbd3ec1b2d134106c6c9429341f5603444dac27
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693980"
---
# <a name="-codepage-c-compiler-options"></a>-codepage (opzioni del compilatore C#)
Questa opzione specifica la tabella codici da usare durante la compilazione, se la pagina richiesta non è la tabella codici predefinita corrente per il sistema.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Argomenti  
 `id`  
 ID della tabella codici da usare per tutti i file di codice sorgente nella compilazione.  
  
## <a name="remarks"></a>Note  
 Se si compilano uno o più file di codice sorgente che non sono stati creati per usare la tabella codici predefinita nel computer in uso, è possibile usare l'opzione **-codepage** per specificare la tabella codici da usare. **-codepage** si applica a tutti i file di codice sorgente nella compilazione.  
  
 Se i file di codice sorgente sono stati creati con la stessa tabella codici attiva nel computer in uso o se i file di codice sorgente sono stati creati con UNICODE o UTF-8, non sarà necessario usare **-codepage**.  
  
 Per informazioni su come individuare le tabelle codici supportate nel sistema, vedere [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
