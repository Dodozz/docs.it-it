---
title: -optimize (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: 25a9ee1b27836dfb00dcbc72712ed068639fa2fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320032"
---
# <a name="-optimize-c-compiler-options"></a>-optimize (opzioni del compilatore C#)
L'opzione **-optimize** abilita o disabilita le ottimizzazioni eseguite dal compilatore per ridurre le dimensioni del file di output e aumentarne la velocità e l'efficienza.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a>Osservazioni  
 **-optimize** comunica poi a Common Language Runtime di ottimizzare il codice in fase di esecuzione.  
  
 Per impostazione predefinita, le ottimizzazioni sono disabilitate. Per abilitarle, specificare **-optimize+**.  
  
 Durante la compilazione di un modulo per l'uso da parte di un assembly, specificare per **-optimize** le stesse impostazioni usate per l'assembly.  
  
 **-o** è la versione abbreviata di **-optimize**.  
  
 Le opzioni **-optimize** e [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) possono essere usate in modo combinato.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagine **Proprietà** del progetto.  
  
2. Fare clic sulla pagina della proprietà **Compilazione**.  
  
3. Modificare la proprietà **Ottimizza codice**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `t2.cs` e abilitare le ottimizzazioni del compilatore:  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
