---
title: Cenni preliminari su LINQ to XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
ms.openlocfilehash: a8695e94797c297154db9597c6e9938ed9aecfef
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063014"
---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a>Cenni preliminari su LINQ to XML in Visual Basic
Visual Basic fornisce il supporto per [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tramite valori letterali XML e proprietà axis XML. In questo modo è possibile usare una sintassi familiare e conveniente per l'utilizzo di XML nel codice Visual Basic. *Valori letterali XML* consentono di includere dati XML direttamente nel codice. *Proprietà axis XML* consentono di accedere a nodi figlio, i nodi discendente e gli attributi di un valore letterale XML. Per altre informazioni, vedere [Cenni preliminari sui valori letterali XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) e [l'accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è progettato specificamente per sfruttare i vantaggi dell'API di programmazione XML in memoria [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Sebbene sia possibile chiamare il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] direttamente le API, solo Visual Basic consente di dichiarare i valori letterali XML e accedere direttamente a proprietà axis XML.  
  
> [!NOTE]
>  Valori letterali XML e proprietà axis XML non sono supportate nel codice dichiarativo in una pagina ASP.NET. Per usare le funzionalità XML di Visual Basic, inserire il codice in una pagina code-behind nell'applicazione ASP.NET.  
  
 [Pulsante Riproduci](./media/overview-of-linq-to-xml/play-video-icon-example.gif) per dimostrazioni video correlate, vedere [How Do prendetevi con LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-get-started-with-linq-to-xml) e [come posso creare fogli di calcolo Excel mediante LINQ to XML?](/aspnet/web-forms/videos/data-access/linq-videos-from-the-vb-team/how-do-i-create-excel-spreadsheets-using-linq-to-xml).   
  
## <a name="creating-xml"></a>Creazione di XML  
 Esistono due modi per creare alberi XML in Visual Basic. È possibile dichiarare valori letterali direttamente nel codice XML oppure è possibile usare il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] API per creare l'albero. Entrambi i processi consentono al codice in modo da riflettere la struttura finale dell'albero XML. Ad esempio, il codice seguente crea un elemento XML:  
  
 [!code-vb[VbXmlSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Per altre informazioni, vedere [creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## <a name="accessing-and-navigating-xml"></a>Accesso e l'esplorazione XML  
 Visual Basic fornisce le proprietà axis XML per l'accesso e l'esplorazione di strutture XML. Queste proprietà consentono di accedere a elementi e attributi XML specificando i nomi degli elementi figlio XML. In alternativa, è possibile chiamare in modo esplicito il [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] metodi per la navigazione e individuazione di elementi e attributi. Ad esempio, il codice seguente usa le proprietà axis XML per fare riferimento agli attributi e gli elementi figlio di un elemento XML. Nell'esempio di codice viene usato un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query per recuperare elementi figlio e restituirli come elementi XML, in modo efficace eseguendo una trasformazione.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Per altre informazioni, vedere [l'accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Visual Basic consente di specificare un alias per uno spazio dei nomi XML globale utilizzando il `Imports` istruzione. Nell'esempio seguente viene illustrato come utilizzare il `Imports` per importare uno spazio dei nomi XML:  
  
 [!code-vb[VbXMLSamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#1)]  
  
 Quando si accede alle proprietà axis XML e dichiarano i valori letterali XML per elementi e documenti XML, è possibile usare un alias dello spazio dei nomi XML.  
  
 È possibile recuperare un <xref:System.Xml.Linq.XNamespace> oggetto per un prefisso dello spazio dei nomi specifico usando il [operatore GetXmlNamespace](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Per altre informazioni, vedere [istruzione Imports (Namespace XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### <a name="using-xml-namespaces-in-xml-literals"></a>Utilizzo di spazi dei nomi XML in valori letterali XML  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Xml.Linq.XElement> oggetto che usa lo spazio dei nomi globale `ns`:  
  
 [!code-vb[VbXMLSamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#2)]  
  
 Il compilatore Visual Basic si traduce i valori letterali XML che contengono gli alias dello spazio dei nomi XML in codice equivalente che usa la notazione di XML per l'uso di spazi dei nomi XML, con la `xmlns` attributo. Quando viene compilato, il codice di esempio della sezione precedente produce essenzialmente lo stesso codice eseguibile come illustrato nell'esempio seguente:  
  
 [!code-vb[VbXMLSamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#3)]  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a>Utilizzo di spazi dei nomi XML in proprietà Axis XML  
 Spazi dei nomi XML dichiarati in valori letterali XML non sono disponibili per l'uso in proprietà axis XML. Tuttavia, gli spazi dei nomi globale è utilizzabile con le proprietà axis XML. I due punti per separare il prefisso dello spazio dei nomi XML da utilizzare il nome dell'elemento locale. Di seguito è riportato un esempio:  
  
 [!code-vb[VbXMLSamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Accesso a XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
