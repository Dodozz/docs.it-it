---
title: Supporto dello spazio dei nomi nel DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f0548ead-0fed-41ee-b33e-117ba900d3bc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a468d1a2b15d1f92726d8d429fbc5ddece96e6d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647856"
---
# <a name="namespace-support-in-the-dom"></a>Supporto dello spazio dei nomi nel DOM
Il modello DOM XML supporta pienamente lo spazio dei nomi. Sono supportati solo i documenti XML che supportano lo spazio dei nomi. Il W3C (World Wide Web Consortium) specifica che lo spazio dei nomi può non essere supportato da applicazioni DOM che implementano il Livello 1, ma che è supportato dalle funzionalità di Livello 2 del DOM. Tutte le funzionalità nel DOM XML, tuttavia, supportano lo spazio dei nomi indipendentemente dal fatto che il metodo sia regolato dalla raccomandazione DOM di Livello 1 o di Livello 2.  
  
 Ad esempio, in un'impostazione che supporta lo spazio dei nomi, la chiamata di `setAttribute("A:b", "123")` come specificato dalla raccomandazione DOM di Livello 1, non dà luogo a un attributo con prefisso `A` e nome locale `b`, bensì un attributo con il valore `A:b`.  
  
 In un ambiente che supporta lo spazio dei nomi, la chiamata di `setAttribute("A:b", "123")` del DOM di Livello 2 dà luogo a un attributo con prefisso `A` e nome locale `b`. Il modello DOM di Microsoft .NET Framework funziona in questo modo.  
  
 Quindi i metodi che accettano un nome come parametro accettano anche un prefisso per la qualifica del nome. Un parametro di nome, ad esempio `A:b` nel metodo **setAttribute** del modello DOM di livello 1 viene analizzato nel modo seguente:  
  
- Se non sono presenti caratteri di due punti (:), il nome locale viene impostato sul parametro `name` e il prefisso e NamespaceURI sono stringhe vuote.  
  
- Se viene rilevato un carattere di due punti, il nome viene diviso in due parti, in base alla posizione del primo carattere di due punti. Il prefisso è impostato sulla stringa prima dei due punti e il nome locale è impostato sulla stringa dopo i due punti. Per i metodi che non accettano un valore NamespaceURI, quest'ultimo non è risolto e rimane impostato su una stringa vuota. In caso contrario, il NamespaceURI viene impostato sulla stringa passata al metodo. Se il prefisso non è definito, il metodo **Save** e le proprietà **InnerXml** e **OuterXml** danno origine a un errore.  
  
## <a name="see-also"></a>Vedere anche

- [Modello DOM (Document Object Mode) XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
