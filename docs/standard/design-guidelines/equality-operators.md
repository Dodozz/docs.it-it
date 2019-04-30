---
title: Operatori di uguaglianza
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: KrzysztofCwalina
ms.openlocfilehash: ef1a0aff1ac59434d9d9a6f0371bf236f637050e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61960331"
---
# <a name="equality-operators"></a>Operatori di uguaglianza
In questa sezione illustra l'overload degli operatori di uguaglianza e si intende `operator==` e `operator!=` come operatori di uguaglianza.  
  
 **X DO NOT** overload degli operatori di uguaglianza e non in altro.  
  
 **✓ DO** assicurarsi che <xref:System.Object.Equals%2A?displayProperty=nameWithType> e gli operatori di uguaglianza hanno esattamente la stessa semantica e caratteristiche di prestazioni simili.  
  
 Ciò significa che spesso `Object.Equals` deve essere sottoposto a override quando sono sottoposti a overload gli operatori di uguaglianza.  
  
 **X AVOID** generazione di eccezioni da operatori di uguaglianza.  
  
 Ad esempio, restituisce false se uno degli argomenti è null anziché generare `NullReferenceException`.  
  
## <a name="equality-operators-on-value-types"></a>Operatori di uguaglianza sui tipi di valore  
 **✓ DO** eseguire l'overload degli operatori di uguaglianza sui tipi di valore, se l'uguaglianza è significativo.  
  
 La maggior parte dei linguaggi di programmazione, vi è Nessuna implementazione predefinita di `operator==` per i tipi di valore.  
  
## <a name="equality-operators-on-reference-types"></a>Operatori di uguaglianza sui tipi di riferimento  
 **X AVOID** overload degli operatori di uguaglianza sui tipi di riferimento modificabile.  
  
 Molte lingue hanno operatori di uguaglianza predefinito per i tipi di riferimento. Gli operatori incorporati in genere implementano l'uguaglianza di riferimenti e molti sviluppatori sono sorpresi quando viene modificato il comportamento predefinito per l'uguaglianza di valore.  
  
 Questo problema è stata risolta per i tipi di riferimento non modificabile, poiché non modificabilità rende molto più difficile da osservare la differenza tra uguaglianza di riferimento e uguaglianza di valori.  
  
 **X AVOID** overload degli operatori di uguaglianza sui tipi di riferimento se l'implementazione sarebbe notevolmente più lento rispetto a quello di uguaglianza di riferimento.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
- [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
