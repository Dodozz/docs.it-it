---
title: Istruzione Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: bf3eb6476dc1485faeddab475f29e508175d3378
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638194"
---
# <a name="erase-statement-visual-basic"></a>Istruzione Erase (Visual Basic)
Utilizzato per rilasciare le variabili di matrice e deallocare la memoria usata per i relativi elementi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>Parti  
 `arraylist`  
 Obbligatorio. Elenco di variabili di matrice da cancellare. Nel caso di più variabili, è possibile separarle mediante virgole.  
  
## <a name="remarks"></a>Note  
 Il `Erase` istruzione può essere specificata solo a livello di routine. Ciò significa che è possibile rilasciare le matrici all'interno di una routine, ma non a livello di classe o modulo.  
  
 Il `Erase` istruzione equivale all'assegnazione `Nothing` a ogni variabile di matrice.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Erase` istruzione per due matrici di cancellare e liberare la memoria (1000 e 100 elementi, rispettivamente). Il `ReDim` istruzione quindi assegna una nuova istanza della matrice nella matrice tridimensionale.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
