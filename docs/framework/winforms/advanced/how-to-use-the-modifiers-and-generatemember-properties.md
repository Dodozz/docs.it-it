---
title: 'Procedura: Usare i modificatori e proprietà GenerateMember'
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
ms.openlocfilehash: 277d2bdebc1d3b85efb70510b8acd34ed3a91087
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710797"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="25fb7-102">Procedura: Usare i modificatori e proprietà GenerateMember</span><span class="sxs-lookup"><span data-stu-id="25fb7-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="25fb7-103">Quando si posiziona un componente in un Windows Form, dall'ambiente di progettazione vengono fornite due proprietà: `GenerateMember` e `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="25fb7-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="25fb7-104">Il `GenerateMember` proprietà consente di specificare quando la finestra di progettazione Windows Form genera una variabile membro per un componente.</span><span class="sxs-lookup"><span data-stu-id="25fb7-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="25fb7-105">Il `Modifiers` proprietà è il modificatore di accesso assegnato alla variabile membro.</span><span class="sxs-lookup"><span data-stu-id="25fb7-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="25fb7-106">Se il valore della `GenerateMember` proprietà è `false`, il valore della `Modifiers` proprietà non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="25fb7-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25fb7-107">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="25fb7-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="25fb7-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="25fb7-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="25fb7-109">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="25fb7-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="25fb7-110">Per specificare se un componente è un membro del form</span><span class="sxs-lookup"><span data-stu-id="25fb7-110">To specify whether a component is a member of the form</span></span>  
  
1.  <span data-ttu-id="25fb7-111">Nella finestra di progettazione Windows Form, aprire il form.</span><span class="sxs-lookup"><span data-stu-id="25fb7-111">In the Windows Forms Designer, open your form.</span></span>  
  
2.  <span data-ttu-id="25fb7-112">Aprire il **casella degli strumenti**e nel form, inserire tre <xref:System.Windows.Forms.Button> controlli.</span><span class="sxs-lookup"><span data-stu-id="25fb7-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3.  <span data-ttu-id="25fb7-113">Impostare il `GenerateMember` e `Modifiers` delle proprietà per ogni <xref:System.Windows.Forms.Button> controllo in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="25fb7-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="25fb7-114">Nome del pulsante</span><span class="sxs-lookup"><span data-stu-id="25fb7-114">Button name</span></span>|<span data-ttu-id="25fb7-115">Valore GenerateMember</span><span class="sxs-lookup"><span data-stu-id="25fb7-115">GenerateMember value</span></span>|<span data-ttu-id="25fb7-116">Valore di modificatori</span><span class="sxs-lookup"><span data-stu-id="25fb7-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="25fb7-117">Nessuna modifica</span><span class="sxs-lookup"><span data-stu-id="25fb7-117">No change</span></span>|  
  
4.  <span data-ttu-id="25fb7-118">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="25fb7-118">Build the solution.</span></span>  
  
5.  <span data-ttu-id="25fb7-119">In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6.  <span data-ttu-id="25fb7-120">Aprire il **Form1** nodo e nel **Editor di codice**, aprire il **Form1** o **Form1.Designer.cs** file.</span><span class="sxs-lookup"><span data-stu-id="25fb7-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="25fb7-121">Questo file contiene il codice generato da Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="25fb7-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7.  <span data-ttu-id="25fb7-122">Trova le dichiarazioni dei tre pulsanti.</span><span class="sxs-lookup"><span data-stu-id="25fb7-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="25fb7-123">Esempio di codice seguente illustra le differenze specificate dal `GenerateMember` e `Modifiers` proprietà.</span><span class="sxs-lookup"><span data-stu-id="25fb7-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="25fb7-124">Per impostazione predefinita, la finestra di progettazione Windows Form assegna il `private` (`Friend` in Visual Basic) modifica ai controlli contenitore, ad esempio <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="25fb7-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="25fb7-125">Se la base <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> dispone di un controllo contenitore, non accetterà nuovi elementi figlio nei form e controlli ereditati.</span><span class="sxs-lookup"><span data-stu-id="25fb7-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="25fb7-126">La soluzione consiste nel modificare il modificatore del controllo contenitore di base `protected` o `public`.</span><span class="sxs-lookup"><span data-stu-id="25fb7-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25fb7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25fb7-127">See also</span></span>
- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="25fb7-128">Ereditarietà visiva di Windows Form</span><span class="sxs-lookup"><span data-stu-id="25fb7-128">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="25fb7-129">Procedura dettagliata: Dimostrazione dell'ereditarietà visiva</span><span class="sxs-lookup"><span data-stu-id="25fb7-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="25fb7-130">Procedura: Ereditare Windows Form</span><span class="sxs-lookup"><span data-stu-id="25fb7-130">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
