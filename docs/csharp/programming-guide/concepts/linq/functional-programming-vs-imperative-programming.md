---
title: Differenze tra programmazione funzionale e programmazione imperativa (C#)
ms.date: 07/20/2015
ms.assetid: 5e35c5a0-c949-422a-873b-fca6b2254f57
ms.openlocfilehash: 2b6a53943ea2363869530ae773c19a52b5578b56
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596710"
---
# <a name="functional-programming-vs-imperative-programming-c"></a>Differenze tra programmazione funzionale e programmazione imperativa (C#)
In questo argomento vengono presentate le differenze tra la programmazione funzionale e la più tradizionale programmazione imperativa (procedurale).  
  
## <a name="functional-programming-vs-imperative-programming"></a>Differenze tra programmazione funzionale e programmazione imperativa  
 Il paradigma della *programmazione funzionale* è stato creato espressamente per supportare un approccio funzionale puro alla risoluzione di problemi. La programmazione funzionale è un tipo di *programmazione dichiarativa*. Al contrario, la maggior parte dei linguaggi più diffusi, compresi i linguaggi di programmazione orientata a oggetti (OOP), quali C#, Visual Basic, C++ e Java, è progettata principalmente per supportare la programmazione (procedurale) *imperativa*.  
  
 Con un approccio imperativo lo sviluppatore scrive codice in cui vengono descritti in dettaglio i passaggi esatti che devono essere eseguiti dal computer per raggiungere l'obiettivo. Questo tipo di programmazione viene a volte definito *algoritmica*. Al contrario, un approccio funzionale implica la composizione del problema come set di funzioni da eseguire. È necessario definire con attenzione l'input e l'output di ogni funzione. Nella tabella seguente sono descritte alcune delle differenze generali tra questi due approcci.  
  
|Caratteristica|Approccio imperativo|Approccio funzionale|  
|--------------------|-------------------------|-------------------------|  
|Obiettivo del programmatore|Come eseguire attività (algoritmi) e come tenere traccia delle modifiche di stato.|Quali informazioni si desiderano e quali trasformazioni sono richieste.|  
|Modifiche di stato|Importante.|Non esistente.|  
|Ordine di esecuzione|Importante.|Importanza limitata.|  
|Controllo del flusso primario|Cicli, condizionali e chiamate di funzioni (metodi).|Chiamate di funzioni, inclusa la ricorsione.|  
|Unità di modifica primaria|Istanze di strutture o classi.|Funzioni come oggetti e raccolte dati di prima classe.|  
  
 Anche se la maggior parte dei linguaggi è progettata per supportare un paradigma di programmazione specifico, i linguaggi generici sono in genere sufficientemente flessibili da supportare più paradigmi. Ad esempio, è possibile usare la maggior parte dei linguaggi che contengono puntatori a funzioni per supportare efficacemente la programmazione funzionale. C# comprende anche estensioni di linguaggio esplicite per supportare la programmazione funzionale, tra cui espressioni lambda e inferenza del tipo. La tecnologia LINQ è un tipo di programmazione funzionale e dichiarativa.  
  
## <a name="functional-programming-using-xslt"></a>Programmazione funzionale tramite XSLT  
 Gli sviluppatori XSLT hanno in genere una certa familiarità con l'approccio funzionale. Il modo più efficace per sviluppare un foglio di stile XSLT consiste nel considerare ogni modello come una trasformazione isolata e componibile. All'ordine di esecuzione non viene data alcuna importanza. XSLT non consente effetti collaterali, con l'eccezione che i meccanismi di escape per l'esecuzione di codice procedurale può introdurre effetti collaterali che pregiudicano la purezza funzionale. Tuttavia, pur essendo uno strumento efficace, alcune caratteristiche di XSLT non sono ottimali. Ad esempio, l'espressione di costrutti di programmazione in XML rende il codice relativamente dettagliato e pertanto difficile da mantenere. Inoltre, l'affidamento eccessivo alla ricorsione per il controllo del flusso può generare codice difficile da leggere. Per altre informazioni su XSLT, vedere [Trasformazioni XSLT](../../../../standard/data/xml/xslt-transformations.md).  
  
 Tuttavia, XSLT ha dimostrato il vantaggio dell'utilizzo di un approccio funzionale puro per trasformare XML da una forma a un'altra. La programmazione funzionale con LINQ to XML è simile a XSLT per molti aspetti. I costrutti di programmazione introdotti da LINQ to XML e C# consentono tuttavia di scrivere trasformazioni funzionali pure che risultano più facili da leggere e di facile manutenzione rispetto a XSLT.  
  
## <a name="advantages-of-pure-functions"></a>Vantaggi delle funzioni pure  
 Il motivo principale per implementare le trasformazioni funzionali come funzioni pure è che le funzioni pure sono componibili, ossia sono autonome e senza stato. Queste caratteristiche offrono numerosi vantaggi, tra cui quelli riportati di seguito:  
  
- Maggiore facilità di lettura e manutenibilità, in quanto ogni funzione è progettata per realizzare un'attività specifica con gli argomenti assegnati. La funzione non si basa su alcuno stato esterno.  
  
- Sviluppo iterativo più semplice, in quanto è più agevole eseguire il refactoring del codice ed è più facile implementare le modifiche di progettazione. Si supponga ad esempio di scrivere una trasformazione complicata e poi di realizzare che una parte di codice viene ripetuta diverse volte al suo interno. Se si esegue il refactoring tramite un metodo puro, è possibile chiamare il metodo puro quando è necessario senza preoccuparsi degli effetti collaterali.  
  
- Procedure più semplici di test e debug, in quanto le funzioni pure possono essere più facilmente testate in isolamento ed è possibile scrivere codice di test che chiama la funzione pura con valori tipici, casi limite validi e casi limite non validi.  
  
## <a name="transitioning-for-oop-developers"></a>Transizione per gli sviluppatori OOP  
 Nella tradizionale programmazione orientata a oggetti (OOP, Object-Oriented Programming), gli sviluppatori sono in genere abituati a programmare nello stile imperativo/procedurale. Per passare allo sviluppo in uno stile funzionale puro, devono modificare il loro modo di ragionare e l'approccio adottato per lo sviluppo.  
  
 Per risolvere i problemi, gli sviluppatori progettano gerarchie di classi, si dedicano al corretto incapsulamento e ragionano in termini di contratti tra classi. Il comportamento e lo stato dei tipi di oggetto sono di fondamentale importanza e per rispondere a tale esigenza vengono fornite funzionalità del linguaggio quali classi, interfacce, ereditarietà e polimorfismo.  
  
 Al contrario, l'approccio della programmazione funzionale ai problemi si traduce nella valutazione di trasformazioni funzionali pure di raccolte dati. Nella programmazione funzionale vengono evitati i dati di stato e modificabili e viene data invece una maggiore enfasi all'applicazione di funzioni.  
  
 Fortunatamente, in C# non è necessario passare completamente alla programmazione funzionale, perché sono supportati sia l'approccio imperativo che quello funzionale. Gli sviluppatori possono scegliere l'approccio più appropriato per un determinato scenario. In effetti, nei programmi vengono spesso combinati entrambi gli approcci.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle trasformazioni funzionali pure (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Trasformazioni XSLT](../../../../standard/data/xml/xslt-transformations.md)
- [Refactoring in funzioni pure (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
