---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 1c3c70b24de5163ca004b41a21017205a19d9730
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583368"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Indica al compilatore di non riferimento automaticamente alle librerie standard.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>Note  
 Il `-nostdlib` opzione rimuove il riferimento automatico all'assembly System. dll e impedisce al compilatore di leggere il file Vbc. rsp. Il file Vbc. rsp, che si trova nella stessa directory del file Vbc.exe, fa riferimento all'assembly di .NET Framework comunemente utilizzati e Importa il `System` e `Microsoft.VisualBasic` gli spazi dei nomi.  
  
> [!NOTE]
>  Gli assembly mscorlib. dll e VisualBasic vengono sempre fatto riferimento.  
  
> [!NOTE]
>  Il `-nostdlib` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` senza fare riferimento alle librerie standard. È necessario impostare il `_MYTYPE` costante di compilazione condizionale per la stringa "Empty" per rimuovere il `My` oggetto.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
