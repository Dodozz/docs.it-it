---
title: -baseaddress (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: aa76e3d1d30e394f28b5112e45fc72229e9a78fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295783"
---
# <a name="-baseaddress-c-compiler-options"></a>-baseaddress (opzioni del compilatore C#)
L'opzione **-baseaddress** consente di specificare l'indirizzo di base preferito in cui caricare una DLL. Per altre informazioni su quando e perché usare questa opzione, vedere il [blog di Larry Osterman](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Argomenti  
 `address`  
 Indirizzo di base per la DLL. Questo indirizzo può essere specificato come numero decimale, esadecimale o ottale.  
  
## <a name="remarks"></a>Osservazioni  
 L'indirizzo di base predefinito per una DLL viene impostato dal Common Language Runtime di .NET Framework.  
  
 Tenere presente che la parola di ordine inferiore in questo indirizzo verrà arrotondata. Ad esempio, se si specifica 0x11110001, il valore verrà arrotondato a 0x11110000.  
  
 Per completare il processo di firma di una DLL, usare SN.EXE con l'opzione -R.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagine **Proprietà** del progetto.  
  
2. Fare clic sulla pagina della proprietà **Compilazione**.  
  
3. Fare clic su **Avanzate** .  
  
4. Modificare la proprietà **Indirizzo di base DLL**.  
  
     Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>
- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
