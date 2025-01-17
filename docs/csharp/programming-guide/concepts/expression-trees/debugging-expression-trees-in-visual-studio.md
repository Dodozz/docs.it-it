---
title: Debug degli alberi delle espressioni in Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 93b1b660181cd81c31055f5d30d43e535171bb55
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2019
ms.locfileid: "66195980"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a>Debug degli alberi delle espressioni in Visual Studio (C#)
È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni. Per una rapida panoramica della struttura dell'albero delle espressioni, è possibile usare la proprietà `DebugView`, che rappresenta gli alberi delle espressioni [usando una sintassi speciale](debugview-syntax.md). Si noti che `DebugView` è disponibile solo in modalità di debug.  

![DebugView di un albero delle espressioni all'interno del debugger di Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview.png)

Dato che `DebugView` è una stringa, è possibile usare il [Visualizzatore testo incorporato](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) per visualizzarla su più righe, selezionando **Visualizzatore testo** dall'icona della lente di ingrandimento accanto all'etichetta `DebugView`.

 ![Visualizzatore testo applicato ai risultati di "DebugView"](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

In alternativa, è possibile installare e usare [un visualizzatore personalizzato](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) per gli alberi delle espressioni, ad esempio:

* [Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licenza MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponibile in [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)) esegue il rendering dell'albero delle espressioni come codice C#:

  ![Visualizzatore Readable Expressions](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licenza MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) offre una visualizzazione grafica dell'albero delle espressioni, delle relative proprietà e degli oggetti correlati:

  ![Visualizzatore ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Per aprire un visualizzatore per un albero delle espressioni  
  
1. Fare clic sull'icona della lente di ingrandimento visualizzata accanto all'albero delle espressioni in **Suggerimenti dati**, in una finestra **Espressione di controllo**, nella finestra **Automatico** o nella finestra **Variabili locali**.  
  
     Viene visualizzato un elenco dei visualizzatori disponibili: 

      ![Apertura di visualizzatori da Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. Fare clic sul visualizzatore da usare.  
  
## <a name="see-also"></a>Vedere anche

- [Alberi delle espressioni (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [Debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Creazione di visualizzatori personalizzati](/visualstudio/debugger/create-custom-visualizers-of-data)
- Sintassi di [`DebugView`](debugview-syntax.md)
