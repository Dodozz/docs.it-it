---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: ff4b1729f1b9fb1d698b4b5b1e3711ce3d27b4db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655556"
---
# <a name="-rootnamespace"></a>-rootnamespace
Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`namespace`|Il nome dello spazio dei nomi in cui racchiudere tutte le dichiarazioni di tipo per il progetto corrente.|  
  
## <a name="remarks"></a>Note  
 Se si usa il file eseguibile (Devenv.exe) di Visual Studio per compilare un progetto creato nell'ambiente di sviluppo integrato di Visual Studio, usare `-rootnamespace` per specificare il valore della <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> proprietà. Visualizzare [opzioni della riga di comando Devenv](/visualstudio/ide/reference/devenv-command-line-switches) per altre informazioni.  
  
 Usare common language runtime MSIL Disassembler (`Ildasm.exe`) per visualizzare i nomi dello spazio dei nomi nel file di output.  
  
|Per impostare-. rootnamespace nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Applicazione** .<br />3.  Modificare il valore di **radice Namespace** casella.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` racchiude tutte le dichiarazioni di tipo nello spazio dei nomi `mynamespace`.  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Ildasm.exe (Disassembler IL)](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
