---
title: 'Procedura: Usare lo spazio dei nomi My - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: 00f9083fb9d0ef6c96e19e085a6cff0e0e36f2b0
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236713"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Procedura: Usare lo spazio dei nomi My (Guida per programmatori C#)
Lo spazio dei nomi <xref:Microsoft.VisualBasic.MyServices> (`My` in Visual Basic) consente di accedere in modo semplice e intuitivo a numerose classi .NET Framework, permettendo di scrivere codice che interagisce con il computer, l'applicazione, le impostazioni, le risorse e così via. Anche se originariamente progettato per l'uso con Visual Basic, lo spazio dei nomi `MyServices` può essere usato nelle applicazioni C#.  
  
 Per altre informazioni sull'uso dello spazio dei nomi `MyServices` da Visual Basic, vedere [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md) (Sviluppo con My).  
  
## <a name="adding-a-reference"></a>Aggiunta di un riferimento  
 Prima di poter usare le classi `MyServices` nella soluzione, è necessario aggiungere un riferimento alla libreria di Visual Basic.  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a>Per aggiungere un riferimento alla libreria di Visual Basic  
  
1.  In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** e scegliere **Aggiungi riferimento**.  
  
2.  Nella finestra di dialogo **Riferimenti** visualizzata scorrere l'elenco e selezionare Microsoft.VisualBasic.dll.  
  
     È anche possibile includere la riga seguente nella sezione `using` all'inizio del programma.  
  
     [!code-csharp[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]  
  
## <a name="example"></a>Esempio  
 Questo esempio chiama diversi metodi statici contenuti nello spazio dei nomi `MyServices`. Per compilare questo codice, è necessario aggiungere al progetto un riferimento a Microsoft.VisualBasic.DLL.  
  
 [!code-csharp[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]  
  
 Non tutte le classi incluse nello spazio dei nomi `MyServices` possono essere chiamate da un'applicazione C#. La classe <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>, ad esempio, non è compatibile. In questo caso specifico è possibile usare i metodi statici inclusi in <xref:Microsoft.VisualBasic.FileIO.FileSystem> e contenuti anche nel file VisualBasic.dll. Ecco ad esempio come usare uno di questi metodi per duplicare una directory:  
  
 [!code-csharp[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md)  
- [Uso degli spazi dei nomi](../../../csharp/programming-guide/namespaces/using-namespaces.md)
