---
title: LINQ e stringhe (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
ms.openlocfilehash: 7e0ebe64494182191dafa033ecbc38bad17180be
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818956"
---
# <a name="linq-and-strings-visual-basic"></a>LINQ e stringhe (Visual Basic)
È possibile usare LINQ per eseguire query e trasformare stringhe e raccolte di stringhe. LINQ può essere particolarmente utile con i dati semistrutturati nei file di testo. Le query LINQ possono essere usate in associazione a funzioni per valori stringa tradizionali ed espressioni regolari. Ad esempio, è possibile usare il metodo <xref:System.String.Split%2A> o <xref:System.Text.RegularExpressions.Regex.Split%2A> per creare una matrice di stringhe in cui sarà possibile eseguire query o apportare modifiche usando LINQ. È possibile usare il metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> nella clausola `where` di una query LINQ. È anche possibile usare LINQ per eseguire query o modificare i risultati <xref:System.Text.RegularExpressions.MatchCollection> restituiti da un'espressione regolare.  
  
 È anche possibile usare le tecniche descritte in questa sezione per trasformare dati di testo semistrutturati in XML. Per altre informazioni, vedere [Procedura: Generare XML da file CSV](how-to-generate-xml-from-csv-files.md).  
  
 Gli esempi di questa sezione sono suddivisi in due categorie:  
  
## <a name="querying-a-block-of-text"></a>Esecuzione di query in un blocco di testo  
 È possibile eseguire query, analizzare e modificare blocchi di testo suddividendoli in una matrice di stringhe più piccole sottoponibile a query usando il metodo <xref:System.String.Split%2A> o <xref:System.Text.RegularExpressions.Regex.Split%2A>. È possibile suddividere il testo di origine in parole, frasi, paragrafi, pagine o altri criteri e quindi eseguire altre suddivisioni se richieste nella query.  
  
 [Procedura: Conteggio delle occorrenze di una parola in una stringa (LINQ) (Visual Basic)](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Descrive come usare LINQ per eseguire query semplici nel testo.  
  
 [Procedura: Eseguire una query per trovare frasi che contengono un Set specificato di parole (LINQ) (Visual Basic)](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 Descrive come suddividere file di testo su limiti arbitrari e come eseguire query in ogni parte.  
  
 [Procedura: Query per trovare caratteri in una stringa (LINQ) (Visual Basic)](how-to-query-for-characters-in-a-string-linq.md)  
 Dimostra che una stringa è un tipo sottoponibile a query.  
  
 [Procedura: Combinare query LINQ con espressioni regolari (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md)  
 Descrive come usare le espressioni regolari nelle query LINQ per un modello complesso corrispondente ai risultati della query filtrati.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Esecuzione di query in dati semistrutturati in formato testo  
 Numerosi tipi di file di testo sono costituiti da una serie di righe, spesso con formattazione simile, ad esempio file delimitati da tabulazione o virgola o righe a lunghezza fissa. Dopo la lettura del file di testo in memoria, è possibile usare LINQ per eseguire query e/o modificare le righe. Le query LINQ semplificano anche la combinazione di dati di più origini.  
  
 [Procedura: Trovare la differenza dei Set tra due elenchi (LINQ) (Visual Basic)](how-to-find-the-set-difference-between-two-lists-linq.md)  
 Descrive come trovare tutte le stringhe presenti in un elenco ma non in un altro elenco.  
  
 [Procedura: Ordinare o filtrare i dati di testo per qualsiasi parola o campo (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Descrive come ordinare le righe di testo in base a una parola o un campo.  
  
 [Procedura: Riordinare i campi di un File delimitato (LINQ) (Visual Basic)](how-to-reorder-the-fields-of-a-delimited-file.md)  
 Descrive come riordinare i campi in una riga in un file con estensione csv.  
  
 [Procedura: Combinare e confrontare raccolte di stringhe (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)  
 Descrive come combinare elenchi di stringhe in diversi modi.  
  
 [Procedura: Popolare le raccolte di oggetti da più origini (LINQ) (Visual Basic)](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Descrive come creare raccolte di oggetti usando più file di testo come origini dati.  
  
 [Procedura: Unire contenuto da file non analoghi (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md)  
 Descrive come combinare le stringhe in due elenchi in un'unica stringa usando una chiave corrispondente.  
  
 [Procedura: Suddividere un File in molti file usando i gruppi (LINQ) (Visual Basic)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Descrive come creare file nuovi usando un singolo file come origine dati.  
  
 [Procedura: Calcolare i valori di colonna in un File di testo CSV (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Descrive come eseguire calcoli matematici in dati di testo in file con estensione csv.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query) (Visual Basic)](index.md)
- [Procedura: Generare XML da file CSV](how-to-generate-xml-from-csv-files.md)
