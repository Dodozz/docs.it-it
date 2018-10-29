---
title: Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d9bbb14320b84a6d417c5c28026b169092de219
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49120986"
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM
Quando si carica il documento, è possibile impostare l'opzione che consente di conservare gli spazi e creare nodi **XmlWhitespace** nell'albero del documento. Per creare nodi con spazi, impostare la proprietà **PreserveWhitespace** su true. Se la proprietà è impostata su **false**, che rappresenta il valore predefinito, i nodi con spazi non vengono creati. I nodi con spazi significativi vengono sempre mantenuti e i nodi **XmlSignificantWhitespace** vengono sempre creati in memoria per rappresentare tali dati, indipendentemente dall'impostazione del flag **PreserveWhitespace**.  
  
 Se il documento viene caricato da un lettore, l'impostazione della proprietà del flag **PreserveWhitespace** nella classe **XmlDocument** incide sulla creazione dei nodi **XmlWhitespace** solo se la proprietà **WhitespaceHandling** di **XmlTextReader** non è impostata su **WhitespaceHandling.None**. Il valore della proprietà **WhitespaceHandling** nel lettore che ha la precedenza sull'impostazione del flag nella classe **XmlDocument**. Per altre informazioni su **XmlSignificantWhitespace**, vedere <xref:System.Xml.XmlSignificantWhitespace>.  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
