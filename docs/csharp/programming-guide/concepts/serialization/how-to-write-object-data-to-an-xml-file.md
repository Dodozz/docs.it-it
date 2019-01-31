---
title: 'Procedura: Scrivere dati oggetto in un file XML (C#)'
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: 064d7ed61921f3f700311a1b09ee77e0c9818d71
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554283"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a>Procedura: Scrivere dati oggetto in un file XML (C#)
Questo esempio scrive l'oggetto da una classe in un file XML usando la classe <xref:System.Xml.Serialization.XmlSerializer>.  
  
## <a name="example"></a>Esempio  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;   
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =   
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 La classe deve avere un costruttore public senza parametri.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   La classe da serializzare non ha un costruttore pubblico senza parametri.  
  
-   Il file esiste ed è di sola lettura (<xref:System.IO.IOException>).  
  
-   Percorso del file troppo lungo (<xref:System.IO.PathTooLongException>).  
  
-   Il disco è pieno (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Questo esempio crea un nuovo file, se il file non esiste. Se un'applicazione deve creare un file, deve avere accesso `Create` alla cartella. Se il file esiste già, per l'applicazione è sufficiente l'accesso `Write`, un privilegio di livello inferiore. Se possibile, è più sicuro creare il file durante la distribuzione e concedere l'accesso `Read` a un unico file, anziché l'accesso `Create` a una cartella.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO.StreamWriter>
- [Procedura: Leggere dati oggetto in un file XML (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [Serializzazione (C#)](../../../../csharp/programming-guide/concepts/serialization/index.md)
