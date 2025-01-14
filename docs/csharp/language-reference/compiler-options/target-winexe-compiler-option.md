---
title: -target:winexe (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 3c16bf8aed0d281b2b5a3f9c6ae06f343b1eff7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307313"
---
# <a name="-targetwinexe-c-compiler-options"></a>-target:winexe (opzioni del compilatore C#)
Con l'opzione **-target:winexe** il compilatore crea un file eseguibile (EXE), ovvero un programma di Windows.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a>Osservazioni  
 Il file eseguibile verrà creato con estensione .exe. È un programma di Windows che genera un'interfaccia utente dalla libreria di .NET Framework o con le API Windows.  
  
 Usare [-target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) per creare un'applicazione console.  
  
 Se non diversamente specificato con l'opzione [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del file di input contenente il metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Se specificato alla riga di comando, tutti i file fino alla successiva opzione **-out** o [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) vengono usati per creare il programma Windows.  
  
 Un solo metodo **Main** è necessario nei file del codice sorgente che vengono compilati in un file con estensione exe. L'opzione [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) consente di specificare la classe che contiene il metodo **Main**, nei casi in cui il codice ha più di una classe con un metodo **Main**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio  
  
1. Aprire la pagine **Proprietà** del progetto.  
  
2. Fare clic sulla pagina delle proprietà **Applicazione**.  
  
3. Modificare la proprietà **Tipo di output**.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare `in.cs` in un programma di Windows:  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [-target (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
