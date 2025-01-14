---
title: Overload dei membri
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: b13f9e1551aec7e53ba1ac2ed0b9049d46b0a756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945545"
---
# <a name="member-overloading"></a>Overload dei membri
Overload dei membri prevede la creazione di due o più membri sullo stesso tipo che si differenziano solo per il numero o il tipo dei parametri, ma hanno lo stesso nome. Ad esempio, in quanto segue, il `WriteLine` è l'overload di metodo:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Poiché solo metodi, costruttori e proprietà indicizzate possono avere parametri, solo i membri possono essere sottoposti a overload.  
  
 L'overload è una delle tecniche più importanti per migliorare l'usabilità, la produttività e migliorare la leggibilità delle librerie riutilizzabili. L'overload per il numero di parametri rende possibile fornire versioni semplificate di costruttori e metodi. L'overload del tipo di parametro rende possibile usare lo stesso nome di membro per i membri identici operazioni su un set selezionato di tipi diversi.  
  
 **✓ DO** tenta di utilizzare nomi di parametro descrittivi per indicare il valore predefinito utilizzato dagli overload più breve.  
  
 **X AVOID** arbitrariamente i nomi dei parametri in overload. Se un parametro in uno degli overload rappresenta lo stesso input di un parametro in un altro overload, tali parametri devono avere lo stesso nome.  
  
 **X AVOID** incoerente nell'ordine dei parametri in membri di overload. I parametri con lo stesso nome verrà visualizzato nella stessa posizione in tutti gli overload.  
  
 **✓ DO** rendere virtuale solo l'overload più lunga (se estendibilità è obbligatoria). Overload più breve deve semplicemente eseguire chiamate a un overload più lungo.  
  
 **X DO NOT** usare `ref` o `out` modificatori per eseguire l'overload di membri.  
  
 Alcuni linguaggi non possono risolvere le chiamate agli overload simile al seguente. Inoltre, tali overload in genere hanno una semantica completamente diversa e probabilmente non deve essere overload, ma due metodi distinti invece.  
  
 **X DO NOT** dispongono di overload con parametri nella stessa posizione e tipi simili ma con una semantica diversa.  
  
 **✓ DO** consentire `null` da passare per gli argomenti facoltativi.  
  
 **✓ DO** utilizzare l'overload dei membri anziché definire membri con argomenti predefiniti.  
  
 Gli argomenti predefiniti non sono conformi a CLS.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
