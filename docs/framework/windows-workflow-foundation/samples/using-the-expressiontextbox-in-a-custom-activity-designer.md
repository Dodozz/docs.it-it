---
title: Utilizzo di ExpressionTextBox in un ActivityDesigner personalizzato
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: 87f1052b5bf2c7c4e260aa606cb03b978726bb77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587869"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="14965-102">Utilizzo di ExpressionTextBox in un ActivityDesigner personalizzato</span><span class="sxs-lookup"><span data-stu-id="14965-102">Using the ExpressionTextBox in a Custom Activity Designer</span></span>
<span data-ttu-id="14965-103">In questo esempio viene illustrato come usare l'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> in un ActivityDesigner personalizzato.</span><span class="sxs-lookup"><span data-stu-id="14965-103">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="14965-104">L'attività personalizzata, `MultiAssign`, assegna due valori stringa a due variabili di stringa.</span><span class="sxs-lookup"><span data-stu-id="14965-104">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="14965-105">Alcuni controlli <xref:System.Activities.Presentation.View.ExpressionTextBox> vengono associati a oggetti <xref:System.Activities.InArgument> mentre altri a oggetti <xref:System.Activities.OutArgument>.</span><span class="sxs-lookup"><span data-stu-id="14965-105">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>

## <a name="sample-details"></a><span data-ttu-id="14965-106">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="14965-106">Sample details</span></span>
 <span data-ttu-id="14965-107">L'oggetto `ArgumentToExpressionConverter` è il convertitore di tipi usato in caso di associazione di espressioni agli argomenti.</span><span class="sxs-lookup"><span data-stu-id="14965-107">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="14965-108">La proprietà `ConverterParameter` deve essere impostata su `In`, `Out`, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="14965-108">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> <span data-ttu-id="14965-109">`InOut` non è supportato.</span><span class="sxs-lookup"><span data-stu-id="14965-109">`InOut` is not supported.</span></span>

 <span data-ttu-id="14965-110">Il `UseLocationExpression` attributo è usato in `OutArgument`per specificare che l'espressione deve essere un'espressione L-value ("valore a sinistra" o "valore location").</span><span class="sxs-lookup"><span data-stu-id="14965-110">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="14965-111">Nella maggior parte dei casi, un'espressione L-value è un identificatore di Visual Basic valido usato per indicare che l'oggetto `OutArgument` restituito è una variabile o un nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="14965-111">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>

 <span data-ttu-id="14965-112">L'attributo `MaxLines` viene impostato su uno in questo esempio mentre `MinLines` non viene impostato.</span><span class="sxs-lookup"><span data-stu-id="14965-112">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="14965-113">Pertanto, l'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> è una dimensione fissa di una riga, indipendentemente dalla quantità di testo digitato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="14965-113">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="14965-114">Per consentire all'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> di ingrandirsi per adattarsi all'input dell'utente, impostare per `MaxLines` un valore maggiore rispetto a `MinLines`.</span><span class="sxs-lookup"><span data-stu-id="14965-114">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>

 <span data-ttu-id="14965-115">Un oggetto ExpressionTextBox può essere associato solo agli argomenti e non alle proprietà CLR.</span><span class="sxs-lookup"><span data-stu-id="14965-115">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="14965-116">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="14965-116">To use this sample</span></span>

1.  <span data-ttu-id="14965-117">Con Visual Studio 2010, aprire il file Expressiontextboxsample.</span><span class="sxs-lookup"><span data-stu-id="14965-117">Using Visual Studio 2010, open the ExpressionTextBoxSample.sln file.</span></span>

2.  <span data-ttu-id="14965-118">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="14965-118">To build the solution, press CTRL+SHIFT+B.</span></span>

#### <a name="to-run-this-sample"></a><span data-ttu-id="14965-119">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="14965-119">To run this sample</span></span>

1.  <span data-ttu-id="14965-120">Aggiungere una nuova applicazione console flusso di lavoro alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="14965-120">Add a new Workflow Console Application to the solution.</span></span>

2.  <span data-ttu-id="14965-121">Aggiungere un riferimento per la **ExpressionTextBoxSample** progetto dal nuovo progetto applicazione Console flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="14965-121">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>

3.  <span data-ttu-id="14965-122">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="14965-122">Build the solution.</span></span>

4.  <span data-ttu-id="14965-123">Trascinare il **MultiAssign** attività dalla casella degli strumenti e rilasciarla nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="14965-123">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="14965-124">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="14965-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="14965-125">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="14965-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="14965-126">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="14965-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="14965-127">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="14965-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="14965-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14965-128">See also</span></span>
- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [<span data-ttu-id="14965-129">Sviluppo di applicazioni con Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="14965-129">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
