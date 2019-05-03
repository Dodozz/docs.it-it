---
title: Utilizzo dei contenitori di grafica
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766155"
---
# <a name="using-graphics-containers"></a>Utilizzo dei contenitori di grafica
Oggetto <xref:System.Drawing.Graphics> oggetto fornisce metodi quali <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, e <xref:System.Drawing.Graphics.DrawString%2A> per la visualizzazione di testo, immagini raster e immagini vettoriali. Oggetto <xref:System.Drawing.Graphics> oggetto inoltre dispone di diverse proprietà che determinano la qualità e l'orientamento degli elementi da cui vengono disegnati. Ad esempio, la proprietà modalità di arrotondamento determina se l'anti-aliasing viene applicato a linee e curve, e la proprietà di trasformazione world influenza la posizione e la rotazione degli elementi da cui vengono disegnati.  
  
 Oggetto <xref:System.Drawing.Graphics> oggetto è associato un dispositivo di visualizzazione particolare. Quando si usa una <xref:System.Drawing.Graphics> oggetto su cui disegnare in una finestra di <xref:System.Drawing.Graphics> oggetto è anche associato a quel particolare finestra.  
  
 Oggetto <xref:System.Drawing.Graphics> oggetto può essere considerato un contenitore poiché contiene un set di proprietà che influenza il disegno e collegarla a informazioni specifiche del dispositivo. È possibile creare un contenitore secondario all'interno di un oggetto esistente <xref:System.Drawing.Graphics> chiamando il <xref:System.Drawing.Graphics.BeginContainer%2A> di tale metodo <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Gestione dello stato di un oggetto Graphics](managing-the-state-of-a-graphics-object.md)  
 Viene descritto come gestire le impostazioni di qualità, l'area di ritaglio e trasformazioni di un <xref:System.Drawing.Graphics> oggetto.  
  
 [Uso di contenitori di grafica annidati](using-nested-graphics-containers.md)  
 Viene illustrato come usare i contenitori per controllare lo stato del <xref:System.Drawing.Graphics> oggetto.
