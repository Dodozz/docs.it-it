---
title: 'Procedura: Determinare se un File è un Assembly (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: 47ac7f29509af86819006a4394ca661140b95ab0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316063"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>Procedura: Determinare se un File è un Assembly (Visual Basic)
Un file è un assembly unicamente nei casi in cui è gestito e include nei metadati una voce assembly. Per altre informazioni sugli assembly e sui metadati, vedere l'argomento [Manifesto dell'assembly](../../../../framework/app-domains/assembly-manifest.md).  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Procedura: Determinare se un file è un assembly in modo manuale  
  
1. Avviare il [Disassembler IL (Ildasm.exe)](../../../../framework/tools/ildasm-exe-il-disassembler.md).  
  
2. Caricare il file che si intende verificare.  
  
3. Se **ILDASM** segnala che il file non è un file eseguibile portabile (PE, portable executable), tale file non è un assembly. Per altre informazioni, vedere l'argomento [Procedura: Visualizzare il contenuto degli assembly](../../../../framework/app-domains/how-to-view-assembly-contents.md).  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Procedura: Determinare se un file è un assembly a livello di codice  
  
1. Chiamare il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>, passando il percorso file completo e il nome del file sottoposto a test.  
  
2. Se viene generata un'eccezione <xref:System.BadImageFormatException>, il file non è un assembly.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene testata una DLL per verificare se è un assembly.  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 Il metodo <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> carica il file di test e lo rilascia dopo aver letto le informazioni.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.AssemblyName>
- [Concetti di programmazione](../../../../visual-basic/programming-guide/concepts/index.md)
- [Assembly e Global Assembly Cache (Visual Basic)](index.md)
