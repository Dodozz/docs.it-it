---
title: Debug degli alberi delle espressioni in Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: fb5905c3c1124dd64371216bddda0a17235abdce
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364723"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="59684-102">Debug degli alberi delle espressioni in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59684-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>

<span data-ttu-id="59684-103">È possibile analizzare la struttura e il contenuto degli alberi delle espressioni durante il debug delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="59684-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="59684-104">Per una breve panoramica della struttura ad albero dell'espressione, è possibile usare la proprietà `DebugView`, disponibile solo nella modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="59684-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="59684-105">Per altre informazioni sul debug, vedere [Debug in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="59684-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>

<span data-ttu-id="59684-106">Per rappresentare meglio il contenuto degli alberi delle espressioni, la proprietà `DebugView` usa i visualizzatori di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="59684-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="59684-107">Per altre informazioni, vedere [Creare visualizzatori personalizzati](/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="59684-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="59684-108">Per aprire un visualizzatore per un albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="59684-108">To open a visualizer for an expression tree</span></span>

1. <span data-ttu-id="59684-109">Fare clic sull'icona a forma di lente di ingrandimento visualizzata accanto alla proprietà `DebugView` di una struttura ad albero dell'espressione in **Suggerimenti dati**, in una finestra **Espressioni di controllo**, nella finestra **Auto** o nella finestra **Variabili locali**.</span><span class="sxs-lookup"><span data-stu-id="59684-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>

    <span data-ttu-id="59684-110">Verrà visualizzato un elenco di visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="59684-110">A list of visualizers is displayed.</span></span>

2. <span data-ttu-id="59684-111">Fare clic sul visualizzatore da usare.</span><span class="sxs-lookup"><span data-stu-id="59684-111">Click the visualizer you want to use.</span></span>

<span data-ttu-id="59684-112">Ogni tipo di espressione viene visualizzato nel visualizzatore come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="59684-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="59684-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="59684-113">ParameterExpressions</span></span>

<span data-ttu-id="59684-114">I nomi delle variabili <xref:System.Linq.Expressions.ParameterExpression> vengono visualizzati con un simbolo "$" all'inizio.</span><span class="sxs-lookup"><span data-stu-id="59684-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="59684-115">Se un parametro non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="59684-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="59684-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="59684-116">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="59684-117">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-117">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="59684-118">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-118">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="59684-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="59684-119">ConstantExpressions</span></span>
 <span data-ttu-id="59684-120">Per gli oggetti <xref:System.Linq.Expressions.ConstantExpression> che rappresentano valori interi, stringhe e `null`, viene visualizzato il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="59684-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="59684-121">Esempi</span><span class="sxs-lookup"><span data-stu-id="59684-121">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="59684-122">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-122">`DebugView` property</span></span>

    <span data-ttu-id="59684-123">10</span><span class="sxs-lookup"><span data-stu-id="59684-123">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="59684-124">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-124">`DebugView` property</span></span>

    <span data-ttu-id="59684-125">10D</span><span class="sxs-lookup"><span data-stu-id="59684-125">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="59684-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="59684-126">BlockExpression</span></span>

<span data-ttu-id="59684-127">Se il tipo di un oggetto <xref:System.Linq.Expressions.BlockExpression> differisce dal tipo dell'ultima espressione nel blocco, il tipo viene visualizzato nella proprietà `DebugInfo` tra parentesi angolari (\< e >).</span><span class="sxs-lookup"><span data-stu-id="59684-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="59684-128">In caso contrario, il tipo dell'oggetto <xref:System.Linq.Expressions.BlockExpression> non viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="59684-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="59684-129">Esempi</span><span class="sxs-lookup"><span data-stu-id="59684-129">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="59684-130">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-130">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="59684-131">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-131">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="59684-132">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="59684-132">LambdaExpression</span></span>

<span data-ttu-id="59684-133">Gli oggetti <xref:System.Linq.Expressions.LambdaExpression> vengono visualizzati insieme ai rispettivi tipi delegato.</span><span class="sxs-lookup"><span data-stu-id="59684-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="59684-134">Se un'espressione lamda non ha un nome, viene assegnato un nome generato automaticamente, ad esempio `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="59684-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="59684-135">Esempi</span><span class="sxs-lookup"><span data-stu-id="59684-135">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="59684-136">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-136">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="59684-137">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-137">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="59684-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="59684-138">LabelExpression</span></span>

<span data-ttu-id="59684-139">Se si specifica un valore predefinito per l'oggetto <xref:System.Linq.Expressions.LabelExpression>, questo valore viene visualizzato prima dell'oggetto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="59684-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="59684-140">Il token `.Label` indica l'inizio dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="59684-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="59684-141">Il token `.LabelTarget` indica la destinazione alla quale passare.</span><span class="sxs-lookup"><span data-stu-id="59684-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="59684-142">Se un'etichetta non presenta un nome, ne viene assegnato uno generato automaticamente, ad esempio `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="59684-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="59684-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="59684-143">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="59684-144">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-144">`DebugView` property</span></span>

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    <span data-ttu-id="59684-145">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-145">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="59684-146">Operatori checked</span><span class="sxs-lookup"><span data-stu-id="59684-146">Checked Operators</span></span>

<span data-ttu-id="59684-147">Gli operatori di questo tipo vengono visualizzati con il simbolo "#" davanti l'operatore.</span><span class="sxs-lookup"><span data-stu-id="59684-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="59684-148">Ad esempio, l'operatore di addizione checked viene visualizzato come `#+`.</span><span class="sxs-lookup"><span data-stu-id="59684-148">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="59684-149">Esempi</span><span class="sxs-lookup"><span data-stu-id="59684-149">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="59684-150">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-150">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="59684-151">Proprietà `DebugView`</span><span class="sxs-lookup"><span data-stu-id="59684-151">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="59684-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59684-152">See also</span></span>

- [<span data-ttu-id="59684-153">Alberi delle espressioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59684-153">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="59684-154">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="59684-154">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="59684-155">Creazione di visualizzatori personalizzati</span><span class="sxs-lookup"><span data-stu-id="59684-155">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
