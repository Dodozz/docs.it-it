---
title: Estensione di metadati mediante attributi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- metadata, extending
- attributes [.NET Framework], metadata
- elements [.NET Framework], attributes
- common language runtime, attributes
- annotating programming elements
- keyword-like descriptive declarations
- runtime, attributes
- extending metadata
ms.assetid: 30386922-1e00-4602-9ebf-526b271a8b87
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a31082604048e71ebc7581b36857a8bfbd333c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969793"
---
# <a name="extending-metadata-using-attributes"></a>Estensione di metadati mediante attributi
Common Language Runtime consente di aggiungere dichiarazioni descrittive simili a parole chiave, dette attributi, per annotare gli elementi di programmazione quali tipi, campi, metodi e proprietà. Quando si compila il codice per il runtime, viene convertito in Microsoft Intermediate Language (MSIL) e inserito in un file eseguibile portabile (PE) insieme ai metadati generati dal compilatore. Gli attributi consentono di inserire informazioni descrittive aggiuntive nei metadati che possono essere estratte mediante i servizi di reflection di runtime. Il compilatore crea attributi quando si dichiarano istanze di classi speciali che derivano da <xref:System.Attribute?displayProperty=nameWithType>.  
  
 .NET Framework usa gli attributi per diversi motivi e per risolvere una vasta gamma di problemi. Gli attributi descrivono come serializzare i dati, specificare le caratteristiche che consentono di applicare la protezione e limitare le ottimizzazioni effettuate dal compilatore just-in-time (JIT) per facilitare il debug del codice. Gli attributi possono anche registrare il nome di un file o l'autore di codice o controllare la visibilità dei controlli e membri durante lo sviluppo di moduli.  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Description|  
|-----------|-----------------|  
|[Applicazione di attributi](../../../docs/standard/attributes/applying-attributes.md)|Descrive come applicare un attributo a un elemento di codice.|  
|[Scrittura di attributi personalizzati](../../../docs/standard/attributes/writing-custom-attributes.md)|Descrive come progettare le classi di attributi personalizzati.|  
|[Recupero di informazioni memorizzate negli attributi](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)|Descrive come recuperare attributi personalizzati per codice che viene caricato nel contesto di esecuzione.|  
|[Metadati e componenti auto-descrittivi](../../../docs/standard/metadata-and-self-describing-components.md)|Fornisce una panoramica dei metadati e descrive come vengono implementati in un file eseguibile (PE) di .NET Framework.|  
|[Procedura: Caricare assembly nel contesto Reflection-Only](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)|Illustra come recuperare informazioni sugli attributi personalizzati nel contesto reflection-only.|  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Attribute?displayProperty=nameWithType>
