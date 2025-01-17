---
title: 'Procedura: Convertire una matrice di byte in una stringa in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 50acfdbfb9b093f719928f68d90a40f09da5ade5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665367"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>Procedura: Convertire una matrice di byte in una stringa in Visual Basic
Questo argomento illustra come convertire i byte da una matrice di byte in una stringa.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la <xref:System.Text.Encoding.GetString%2A> metodo del <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> classe per convertire tutti i byte dalla matrice di byte in una stringa di codifica.  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 È possibile scegliere tra diverse opzioni di codifica per convertire una matrice di byte in una stringa:  
  
- <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Ottiene una codifica per il set di caratteri ASCII (7 bit).  
  
- <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 nell'ordine dei byte big-endian.  
  
- <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Ottiene una codifica per la tabella codici ANSI corrente del sistema.  
  
- <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-16 nell'ordine dei byte little-endian.  
  
- <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-32 mediante l'ordine dei byte little-endian.  
  
- <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-7.  
  
- <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Ottiene una codifica per il formato UTF-8.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [Procedura: Conversione di stringhe in una matrice di byte in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
