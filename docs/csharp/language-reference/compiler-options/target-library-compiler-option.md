---
title: -target:library (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: 2e0935965e9225ab524290429803fe4c9ccc80c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313645"
---
# <a name="-targetlibrary-c-compiler-options"></a>-target:library (opzioni del compilatore C#)
L'opzione **-target:library** consente la creazione da parte del compilatore di una libreria di collegamento dinamico (DLL), anziché di un file eseguibile (EXE).  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a>Osservazioni  
 La libreria creata avrà estensione DLL.  
  
 Se non diversamente specificato tramite l'opzione [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del primo file di input.  
  
 Quando specificato alla riga di comando, tutti i file fino alla successiva opzione **-out** o **-target:module** vengono usati per creare il file con estensione dll.  
  
 Quando si compila un file con estensione dll, non è richiesto alcun metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagine **Proprietà** del progetto.  
  
2. Fare clic sulla pagina delle proprietà **Applicazione**.  
  
3. Modificare la proprietà **Tipo di output**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare in `in.cs` creando in `in.dll`:  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [-target (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
