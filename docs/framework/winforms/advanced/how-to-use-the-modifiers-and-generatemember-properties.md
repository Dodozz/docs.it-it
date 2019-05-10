---
title: 'Procedura: Usare modificatori e proprietà GenerateMember'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211287"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>Procedura: Usare modificatori e proprietà GenerateMember

Quando si posiziona un componente in un Windows Form, dall'ambiente di progettazione vengono fornite due proprietà: `GenerateMember` e `Modifiers`. Il `GenerateMember` proprietà consente di specificare quando la finestra di progettazione Windows Form genera una variabile membro per un componente. Il `Modifiers` proprietà è il modificatore di accesso assegnato alla variabile membro. Se il valore della `GenerateMember` proprietà è `false`, il valore della `Modifiers` proprietà non ha alcun effetto.

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a>Specificare se un componente è un membro del form

1. In Visual Studio, nella finestra di progettazione Windows Form, aprire il form.

2. Aprire il **casella degli strumenti**e nel form, inserire tre <xref:System.Windows.Forms.Button> controlli.

3. Impostare il `GenerateMember` e `Modifiers` delle proprietà per ogni <xref:System.Windows.Forms.Button> controllo in base alla tabella riportata di seguito.

    |Nome del pulsante|Valore GenerateMember|Valore di modificatori|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|Nessuna modifica|

4. Compilare la soluzione.

5. In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.

6. Aprire il **Form1** nodo e nel **Editor di codice**, aprire il **Form1** o **Form1.Designer.cs** file. Questo file contiene il codice generato da Progettazione Windows Form.

7. Trova le dichiarazioni dei tre pulsanti. Esempio di codice seguente illustra le differenze specificate dal `GenerateMember` e `Modifiers` proprietà.

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> Per impostazione predefinita, la finestra di progettazione Windows Form assegna il `private` (`Friend` in Visual Basic) modifica ai controlli contenitore, ad esempio <xref:System.Windows.Forms.Panel>. Se la base <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> dispone di un controllo contenitore, non accetterà nuovi elementi figlio nei form e controlli ereditati. La soluzione consiste nel modificare il modificatore del controllo contenitore di base `protected` o `public`.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Button>
- [Ereditarietà visiva di Windows Form](windows-forms-visual-inheritance.md)
- [Procedura dettagliata: Dimostrazione dell'ereditarietà visiva](walkthrough-demonstrating-visual-inheritance.md)
- [Procedura: Ereditare Windows Form](how-to-inherit-windows-forms.md)
