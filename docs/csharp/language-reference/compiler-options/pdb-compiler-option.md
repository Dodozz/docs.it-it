---
title: -pdb (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: b0a566931ac76a3adb191f423a497bc446e280c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575502"
---
# <a name="-pdb-c-compiler-options"></a>-pdb (opzioni del compilatore C#)
L'opzione del compilatore **-pdb** consente di specificare il nome e il percorso del file dei simboli di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Nome e percorso del file di simboli di debug.  
  
## <a name="remarks"></a>Note  
 Quando si specifica [-debug (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), il compilatore crea nella stessa directory in cui verrà creato il file di output (con estensione exe o dll) un file con estensione pdb il cui nome è identico a quello del file di output.  
  
 **-pdb** consente di specificare un nome e un percorso non predefiniti per il file con estensione pdb.  
  
 Questa opzione del compilatore non può essere impostata nell'ambiente di sviluppo di Visual Studio, né modificata a livello di codice.  
  
## <a name="example"></a>Esempio  
 Compilare `t.cs` e creare un file con estensione pdb denominato tt.pdb:  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
