---
title: "Procedura: Eseguire l'override del metodo Panel OnRender"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: c4539847368c1a5789e99ec92106d17077ed5943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770838"
---
# <a name="how-to-override-the-panel-onrender-method"></a>Procedura: Eseguire l'override del metodo Panel OnRender
Questo esempio illustra come eseguire l'override di <xref:System.Windows.Controls.Panel.OnRender%2A> metodo <xref:System.Windows.Controls.Panel> per aggiungere effetti grafici personalizzati a un elemento di layout.  
  
## <a name="example"></a>Esempio  
 Usare il <xref:System.Windows.Controls.Panel.OnRender%2A> metodo per aggiungere effetti grafici a un elemento panel sottoposto a rendering. Ad esempio, è possibile usare questo metodo per aggiungere personalizzata del bordo o sfondo effetti. Oggetto <xref:System.Windows.Media.DrawingContext> oggetto viene passato come argomento, che fornisce i metodi per disegnare forme, testo, immagini o video. Di conseguenza, questo metodo è utile per la personalizzazione di un oggetto panel.  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Panel>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Esempio di pannello radiale personalizzato](https://go.microsoft.com/fwlink/?LinkID=159982)
- [Procedure relative alle proprietà](panel-how-to-topics.md)
