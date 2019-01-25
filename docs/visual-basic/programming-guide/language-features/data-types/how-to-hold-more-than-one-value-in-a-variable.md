---
title: 'Procedura: Inserire più valori in una variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: c6cd9c61c332fc98e99334143b50e395f4eabf47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671499"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>Procedura: Inserire più valori in una variabile (Visual Basic)
Una variabile contiene più di un valore se si dichiara che questo sia di un *tipo di dati composito*.  
  
 [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) includono matrici, strutture e classi. Una variabile di un tipo di dati composito può contenere una combinazione di tipi di dati elementari e altri tipi composti. Classi e strutture possono contenere codice, nonché i dati.  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a>Per inserire più valori in una variabile  
  
1.  Determinare a quale tipo di dati composito da usare per la variabile.  
  
2.  Se non è già stato definito il tipo di dati compositi, definirlo in modo che la variabile può usarlo.  
  
    -   Definire una struttura con un [istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md).  
  
    -   Definire una matrice con un [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
    -   Definire una classe con un [istruzione Class](../../../../visual-basic/language-reference/statements/class-statement.md).  
  
3.  Dichiarare la variabile con un `Dim` istruzione.  
  
4.  Seguire il nome della variabile con un `As` clausola.  
  
5.  Seguire il `As` parola chiave con il nome del tipo di dati compositi appropriato.  
  
## <a name="see-also"></a>Vedere anche
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [Caratteri tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
