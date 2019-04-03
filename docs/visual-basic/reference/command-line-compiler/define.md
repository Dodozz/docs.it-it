---
title: -define (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: d0a483e7a3c9e9863db39e89d655cf172c1e8c81
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834309"
---
# <a name="-define-visual-basic"></a>-define (Visual Basic)
Definisce le costanti del compilatore condizionali.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`symbol`|Obbligatorio. Il simbolo da definire.|  
|`value`|Facoltativo. Il valore da assegnare a `symbol`. Se `value` è una stringa, deve essere racchiuso tra sequenze di barre rovesciate/virgolette (\\") anziché le virgolette. Se non è specificato un valore, è considerato True.|  
  
## <a name="remarks"></a>Note  
 Il `-define` opzione ha un effetto simile all'uso di un `#Const` direttiva per il preprocessore nel file di origine, ad eccezione che le costanti definite con `-define` sono pubblici e si applicano a tutti i file nel progetto.  
  
 È possibile usare i simboli creati mediante questa opzione con la direttiva `#If`...`Then`...`#Else` per eseguire la compilazione condizionale dei file di origine.  
  
 `-d` è la versione abbreviata di `-define`.  
  
 È possibile definire più simboli con `-define`, separando le definizioni dei simboli con una virgola.  
  
|Per impostare /define nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Compila**.<br />3.  Scegliere **Avanzate**.<br />4.  Modificare il valore di **stanti personalizzate** casella.|  
  
## <a name="example"></a>Esempio  
 Nel codice seguente sono definite e usate due costanti di compilazione condizionale.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
