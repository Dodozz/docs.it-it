---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: c1824e4a086ecdd4b6a776bd6894f6e003d02867
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789006"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
Evita la visualizzazione del banner del copyright e i messaggi informativi durante la compilazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-nologo  
```  
  
## <a name="remarks"></a>Note  
 Se si specifica `-nologo`, il compilatore non viene visualizzato un banner del copyright. Per impostazione predefinita, l'opzione `-nologo` non è attiva.  
  
> [!NOTE]
>  Il `-nologo` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e non viene visualizzato un banner del copyright.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
