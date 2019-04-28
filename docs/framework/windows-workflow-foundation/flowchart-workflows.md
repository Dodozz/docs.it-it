---
title: Flussi di lavoro del diagramma di flusso
ms.date: 03/30/2017
ms.assetid: b0a3475c-d22f-49eb-8912-973c960aebf5
ms.openlocfilehash: 1840f677929509e4902498c5aa8920f49cb13496
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773594"
---
# <a name="flowchart-workflows"></a><span data-ttu-id="d887d-102">Flussi di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="d887d-102">Flowchart Workflows</span></span>

<span data-ttu-id="d887d-103">Un diagramma di flusso è un paradigma noto per la progettazione di programmi.</span><span class="sxs-lookup"><span data-stu-id="d887d-103">A flowchart is a well-known paradigm for designing programs.</span></span> <span data-ttu-id="d887d-104">L'attività Flowchart viene generalmente usata per implementare i flussi di lavoro non sequenziali, tuttavia può essere sfruttata anche per i flussi di lavoro sequenziali se non viene usato alcun nodo `FlowDecision`.</span><span class="sxs-lookup"><span data-stu-id="d887d-104">The Flowchart activity is typically used to implement non-sequential workflows, but can be used for sequential workflows if no `FlowDecision` nodes are used.</span></span>

## <a name="flowchart-workflow-structure"></a><span data-ttu-id="d887d-105">Struttura del flusso di lavoro del diagramma di flusso</span><span class="sxs-lookup"><span data-stu-id="d887d-105">Flowchart workflow structure</span></span>

 <span data-ttu-id="d887d-106">Un'attività diagramma di flusso contiene una raccolta di attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d887d-106">A Flowchart activity is an activity that contains a collection of activities to be executed.</span></span>  <span data-ttu-id="d887d-107">I diagrammi di flusso contengono gli elementi di controllo del flusso, come <xref:System.Activities.Statements.FlowDecision> e <xref:System.Activities.Statements.FlowSwitch%601>, che dirigono l'esecuzione tra le attività contenute in base ai valori delle variabili.</span><span class="sxs-lookup"><span data-stu-id="d887d-107">Flowcharts also contain flow control elements such as <xref:System.Activities.Statements.FlowDecision> and <xref:System.Activities.Statements.FlowSwitch%601> that direct execution between contained activities based on the values of variables.</span></span>

## <a name="types-of-flow-nodes"></a><span data-ttu-id="d887d-108">Tipi di nodi del flusso</span><span class="sxs-lookup"><span data-stu-id="d887d-108">Types of flow nodes</span></span>

 <span data-ttu-id="d887d-109">Vengono usati tipi diversi di elementi a seconda del tipo di controllo del flusso richiesto quando l'elemento viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="d887d-109">Different types of elements are used depending on the type of flow control required when the element executes.</span></span> <span data-ttu-id="d887d-110">I tipi di elementi del diagramma di flusso includono:</span><span class="sxs-lookup"><span data-stu-id="d887d-110">Types of flowchart elements include:</span></span>

- <span data-ttu-id="d887d-111">`FlowStep`: modella un passaggio di esecuzione nel diagramma di flusso.</span><span class="sxs-lookup"><span data-stu-id="d887d-111">`FlowStep` - Models one step of execution in the flowchart.</span></span>

- <span data-ttu-id="d887d-112">`FlowDecision`: crea un ramo dell'esecuzione in base a una condizione Boolean, simile all'oggetto <xref:System.Activities.Statements.If>.</span><span class="sxs-lookup"><span data-stu-id="d887d-112">`FlowDecision` - Branches execution based on a Boolean condition, similar to <xref:System.Activities.Statements.If>.</span></span>

- <span data-ttu-id="d887d-113">`FlowSwitch`: crea un ramo dell'esecuzione in base a un'opzione esclusiva, simile all'oggetto <xref:System.Activities.Statements.Switch%601>.</span><span class="sxs-lookup"><span data-stu-id="d887d-113">`FlowSwitch` – Branches execution based on an exclusive switch, similar to <xref:System.Activities.Statements.Switch%601>.</span></span>

<span data-ttu-id="d887d-114">Ogni collegamento dispone di una proprietà `Action` che definisce un oggetto <xref:System.Activities.ActivityAction> che può essere usato per eseguire le attività figlio e una o più proprietà `Next` che definiscono quali elementi eseguire al termine dell'esecuzione dell'elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="d887d-114">Each link has an `Action` property that defines a <xref:System.Activities.ActivityAction> that can be used to execute child activities, and one or more `Next` properties that define which element or elements to execute when the current element finishes execution.</span></span>

### <a name="creating-a-basic-activity-sequence-with-a-flowstep-node"></a><span data-ttu-id="d887d-115">Creazione di una sequenza di attività di base con un nodo FlowStep</span><span class="sxs-lookup"><span data-stu-id="d887d-115">Creating a basic activity sequence with a FlowStep node</span></span>

<span data-ttu-id="d887d-116">Per modellare una sequenza di base in cui vengono eseguite a loro volta due attività, viene usato l'elemento `FlowStep`.</span><span class="sxs-lookup"><span data-stu-id="d887d-116">To model a basic sequence in which two activities execute in turn, the `FlowStep` element is used.</span></span> <span data-ttu-id="d887d-117">Nell'esempio seguente vengono usati due elementi `FlowStep` per eseguire due attività in sequenza.</span><span class="sxs-lookup"><span data-stu-id="d887d-117">In the following example, two `FlowStep` elements are used to execute two activities in sequence.</span></span>

```xml
<Flowchart>
  <FlowStep>
    <Assign DisplayName="Get Name">
      <Assign.To>
        <OutArgument x:TypeArguments="x:String">[result]</OutArgument>
      </Assign.To>
      <Assign.Value>
        <InArgument x:TypeArguments="x:String">["User"]</InArgument>
      </Assign.Value>
    </Assign>
    <FlowStep.Next>
      <FlowStep>
        <WriteLine Text="["Hello, " & result]"/>
      </FlowStep>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-a-conditional-flowchart-with-a-flowdecision-node"></a><span data-ttu-id="d887d-118">Creazione di un diagramma di flusso condizionale con un nodo FlowDecision</span><span class="sxs-lookup"><span data-stu-id="d887d-118">Creating a conditional flowchart with a FlowDecision node</span></span>

<span data-ttu-id="d887d-119">Per modellare un nodo del flusso condizionale in un flusso di lavoro del diagramma di flusso (ovvero per creare un collegamento che funziona come simbolo di decisione di un diagramma di flusso tradizionale), viene usato un nodo <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="d887d-119">To model a conditional flow node in a flowchart workflow (that is, to create a link that functions as a traditional flowchart's decision symbol), a <xref:System.Activities.Statements.FlowDecision> node is used.</span></span> <span data-ttu-id="d887d-120">La proprietà <xref:System.Activities.Statements.FlowDecision.Condition%2A> del nodo è impostata su un'espressione che definisce la condizione e le proprietà <xref:System.Activities.Statements.FlowDecision.True%2A> e <xref:System.Activities.Statements.FlowDecision.False%2A> sono impostate sulle istanze di <xref:System.Activities.Statements.FlowNode> da eseguire se l'espressione restituisce `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="d887d-120">The <xref:System.Activities.Statements.FlowDecision.Condition%2A> property of the node is set to an expression that defines the condition, and the <xref:System.Activities.Statements.FlowDecision.True%2A> and <xref:System.Activities.Statements.FlowDecision.False%2A> properties are set to <xref:System.Activities.Statements.FlowNode> instances to be executed if the expression evaluates to `true` or `false`.</span></span> <span data-ttu-id="d887d-121">Nell'esempio seguente viene illustrato come definire un flusso di lavoro che usa un nodo <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="d887d-121">The following example shows how to define a workflow that uses a <xref:System.Activities.Statements.FlowDecision> node.</span></span>

```xml
<Flowchart>
  <FlowStep>
    <Read Result="[s]"/>
    <FlowStep.Next>
      <FlowDecision>
        <IsEmpty Input="[s]" />
        <FlowDecision.True>
          <FlowStep>
            <Write Text="Empty"/>
          </FlowStep>
        </FlowDecision.True>
        <FlowDecision.False>
          <FlowStep>
            <Write Text="Non-Empty"/>
          </FlowStep>
        </FlowDecision.False>
      </FlowDecision>
    </FlowStep.Next>
  </FlowStep>
</Flowchart>
```

### <a name="creating-an-exclusive-switch-with-a-flowswitch-node"></a><span data-ttu-id="d887d-122">Creazione di un'opzione esclusiva con un nodo FlowSwitch</span><span class="sxs-lookup"><span data-stu-id="d887d-122">Creating an exclusive switch with a FlowSwitch node</span></span>

<span data-ttu-id="d887d-123">Per modellare un diagramma di flusso in cui un percorso esclusivo viene selezionato in base a un valore corrispondente viene usato il nodo <xref:System.Activities.Statements.FlowSwitch%601>.</span><span class="sxs-lookup"><span data-stu-id="d887d-123">To model a flowchart in which one exclusive path is selected based on a matching value, the <xref:System.Activities.Statements.FlowSwitch%601> node is used.</span></span> <span data-ttu-id="d887d-124">La proprietà <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> è impostata su <xref:System.Activities.Activity%601> con un parametro di tipo di <xref:System.Object> che definisce il valore con cui confrontare le scelte.</span><span class="sxs-lookup"><span data-stu-id="d887d-124">The <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> property is set to a <xref:System.Activities.Activity%601> with a type parameter of <xref:System.Object> that defines the value to match choices against.</span></span> <span data-ttu-id="d887d-125">La proprietà <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> definisce un dizionario di chiavi e oggetti <xref:System.Activities.Statements.FlowNode> da confrontare con l'espressione condizionale e un set di oggetti <xref:System.Activities.Statements.FlowNode> che definiscono come l'esecuzione deve proseguire se il dato caso corrisponde all'espressione condizionale.</span><span class="sxs-lookup"><span data-stu-id="d887d-125">The <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> property defines a dictionary of keys and <xref:System.Activities.Statements.FlowNode> objects to match against the conditional expression, and a set of <xref:System.Activities.Statements.FlowNode> objects that define how execution should flow if the given case matches the conditional expression.</span></span> <span data-ttu-id="d887d-126">L'oggetto <xref:System.Activities.Statements.FlowSwitch%601> definisce anche una proprietà <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> che definisce il flusso dell'esecuzione se nessun caso corrisponde all'espressione della condizione.</span><span class="sxs-lookup"><span data-stu-id="d887d-126">The <xref:System.Activities.Statements.FlowSwitch%601> also defines a <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> property that defines how execution should flow if no cases match the condition expression.</span></span> <span data-ttu-id="d887d-127">Nell'esempio seguente viene illustrato come definire un flusso di lavoro che usa un elemento <xref:System.Activities.Statements.FlowSwitch%601>.</span><span class="sxs-lookup"><span data-stu-id="d887d-127">The following example demonstrates how to define a workflow that uses a <xref:System.Activities.Statements.FlowSwitch%601> element.</span></span>

```xml
<Flowchart>
  <FlowSwitch>
    <FlowStep x:Key="Red">
      <WriteRed/>
    </FlowStep>
    <FlowStep x:Key="Blue">
      <WriteBlue/>
    </FlowStep>
    <FlowStep x:Key="Green">
      <WriteGreen/>
    </FlowStep>
  </FlowSwitch>
</Flowchart>
```
