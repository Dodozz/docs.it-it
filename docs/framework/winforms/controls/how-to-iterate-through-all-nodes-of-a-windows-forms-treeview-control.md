---
title: 'Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
ms.openlocfilehash: 4b287cecddd63ec6535feb70118c3466c8960531
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941089"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a>Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Forms
È talvolta utile esaminare tutti i nodi in un form Windows <xref:System.Windows.Forms.TreeView> controllo per eseguire calcoli sui valori del nodo. Questa operazione può essere eseguita usando una routine ricorsiva (metodo ricorsivo in C# e C++) che esegue l'iterazione in ogni nodo in ogni raccolta dell'albero.  
  
 Ciascuna <xref:System.Windows.Forms.TreeNode> oggetto in una visualizzazione albero include proprietà che è possibile usare per spostarsi nella visualizzazione albero: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, e <xref:System.Windows.Forms.TreeNode.Parent%2A>. Il valore della <xref:System.Windows.Forms.TreeNode.Parent%2A> proprietà è il nodo padre del nodo corrente. I nodi figlio del nodo corrente, se sono presenti, vengono elencati nel relativo <xref:System.Windows.Forms.TreeNode.Nodes%2A> proprietà. Il <xref:System.Windows.Forms.TreeView> stesso controllo dispone di <xref:System.Windows.Forms.TreeView.TopNode%2A> proprietà, ovvero il nodo radice dell'intera visualizzazione albero.  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a>Per eseguire l'iterazione in tutti i nodi di un controllo TreeView  
  
1. Creare una routine ricorsiva (metodo ricorsivo in C# e C++) che verifica ogni nodo.  
  
2. Chiamare la routine.  
  
     Nell'esempio seguente viene illustrato come stampare ogni <xref:System.Windows.Forms.TreeNode> dell'oggetto <xref:System.Windows.Forms.TreeNode.Text%2A> proprietà:  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)
- [Routine ricorsive](~/docs/visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)
