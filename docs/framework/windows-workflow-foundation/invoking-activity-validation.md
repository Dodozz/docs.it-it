---
title: Richiamo della convalida di attività
ms.date: 03/30/2017
ms.assetid: 22bef766-c505-4fd4-ac0f-7b363b238969
ms.openlocfilehash: 19c2d4773cf15245ba20ff8523ebd7e67d5b9c1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791079"
---
# <a name="invoking-activity-validation"></a>Richiamo della convalida di attività
La convalida delle attività offre un metodo per identificare e segnalare errori nella configurazione di qualsiasi attività prima della relativa esecuzione. Viene eseguita quando un flusso di lavoro viene modificato nell'utilità di progettazione del flusso di lavoro e gli eventuali errori o avvisi di convalida vengono visualizzati in tale utilità. La convalida avviene anche in fase di esecuzione quando un flusso di lavoro viene richiamato e, se si verificano errori di convalida, viene generata un'eccezione <xref:System.Activities.InvalidWorkflowException> dalla logica di convalida predefinita. Windows Workflow Foundation (WF) fornisce il <xref:System.Activities.Validation.ActivityValidationServices> classe che può essere utilizzata dagli sviluppatori di strumenti e applicazioni del flusso di lavoro per convalidare in modo esplicito un'attività. In questo argomento viene descritto come usare l'oggetto <xref:System.Activities.Validation.ActivityValidationServices> per eseguire la convalida delle attività.  
  
## <a name="using-activityvalidationservices"></a>Uso di ActivityValidationServices  
 L'oggetto <xref:System.Activities.Validation.ActivityValidationServices> dispone di due overload <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> usati per richiamare la logica di convalida di un'attività. Il primo overload accetta l'attività radice da convalidare e restituisce una raccolta di errori e di avvisi di convalida. Nell'esempio seguente viene usata un'attività `Add` personalizzata con due argomenti obbligatori.  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 L'attività `Add` viene usata all'interno di un oggetto <xref:System.Activities.Statements.Sequence>, ma i due relativi argomenti obbligatori non sono associati, come illustrato nell'esempio seguente.  
  
```csharp  
Variable<int> Operand1 = new Variable<int>{ Default = 10 };  
Variable<int> Operand2 = new Variable<int>{ Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =   
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 Questo flusso di lavoro può essere convalidato chiamando <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> restituisce una raccolta di tutti gli avvisi e gli errori di convalida contenuti nell'attività e negli elementi figlio, come mostrato nell'esempio riportato di seguito.  
  
```csharp  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 Quando il metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> viene chiamato in questo flusso di lavoro di esempio, vengono restituiti due errori di convalida.  
  
 **Errore: Non è stato fornito alcun valore per un argomento obbligatorio attività 'Operand2'.**  
**Errore: Non è stato fornito alcun valore per un argomento obbligatorio attività 'Operand1'.**  Se questo flusso di lavoro viene richiamato, viene generata un'eccezione <xref:System.Activities.InvalidWorkflowException>, come illustrato nell'esempio seguente.  
  
```csharp  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 **System.Activities.InvalidWorkflowException:**  
**Durante l'elaborazione dell'albero del flusso di lavoro sono stati rilevati gli errori seguenti:**   
**'Aggiungi': Non è stato fornito alcun valore per un argomento obbligatorio attività 'Operand2'.**   
**'Aggiungi': Non è stato fornito alcun valore per un argomento obbligatorio attività 'Operand1'.**  Affinché questo flusso di lavoro di esempio sia valido, è necessario associare i due argomenti obbligatori dell'attività `Add`. Nell'esempio seguente i due argomenti obbligatori vengono associati alle variabili del flusso di lavoro insieme al valore di risultato. In questo esempio l'argomento <xref:System.Activities.Activity%601.Result%2A> viene associato insieme ai due argomenti obbligatori. L'argomento <xref:System.Activities.Activity%601.Result%2A> non deve essere associato e tale condizione non genera un errore di convalida. È compito dell'autore del flusso di lavoro associare la proprietà <xref:System.Activities.Activity%601.Result%2A> qualora il relativo valore venisse usato in altri punti all'interno del flusso di lavoro.  
  
```csharp  
new Add  
{  
    Operand1 = Operand1,  
    Operand2 = Operand2,  
    Result = Result  
}  
```  
  
### <a name="validating-required-arguments-on-the-root-activity"></a>Convalida di argomenti obbligatori nell'attività radice  
 Se l'attività radice di un flusso di lavoro dispone di argomenti, questi vengono associati solo quando il flusso di lavoro viene richiamato e i parametri vengono passati al flusso di lavoro. Il seguente flusso di lavoro supera la convalida, ma viene generata un'eccezione se il flusso di lavoro viene richiamato senza passare gli argomenti obbligatori, come illustrato nell'esempio seguente.  
  
```csharp  
Activity wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, but when the workflow  
// is invoked, an InvalidWorkflowException is thrown.  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 **System.ArgumentException: Impostazioni degli argomenti dell'attività radice non sono corrette.**  
**Correggere la definizione del flusso di lavoro o fornire i valori di input per risolvere questi errori:**   
**'Aggiungi': Non è stato fornito alcun valore per un argomento obbligatorio attività 'Operand2'.**   
**'Aggiungi': Non è stato fornito alcun valore per un argomento obbligatorio attività 'Operand1'.**  Una volta passati gli argomenti appropriati, il flusso di lavoro viene completato correttamente, come illustrato nell'esempio seguente.  
  
```csharp  
Add wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, and the workflow completes  
// successfully because the required arguments were passed.  
try  
{  
    Dictionary<string, object> wfparams = new Dictionary<string, object>  
    {  
        { "Operand1", 10 },  
        { "Operand2", 15 }  
    };  
  
    int result = WorkflowInvoker.Invoke(wf, wfparams);  
    Console.WriteLine("Result: {0}", result);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
> [!NOTE]
> In questo esempio l'attività radice è stata dichiarata come `Add` anziché `Activity` come nell'esempio precedente. In questo modo il metodo `WorkflowInvoker.Invoke` può restituire un solo Integer che rappresenta i risultati dell'attività `Add` anziché un dizionario di argomenti `out`. Anche la variabile `wf` può essere stata dichiarata come `Activity<int>`.  
  
 In caso di convalida di argomenti radice, è compito dell'applicazione host assicurare che vengano passati tutti gli argomenti obbligatori quando viene richiamato il flusso di lavoro.  
  
### <a name="invoking-imperative-code-based-validation"></a>Chiamata della convalida basata su codice imperativo

La convalida basata su codice imperativo fornisce un modo semplice per la convalida automatica di un'attività ed è disponibile per le attività che derivano dagli oggetti <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> e <xref:System.Activities.NativeActivity>. Il codice di convalida che determina qualsiasi errore o avviso di convalida viene aggiunto all'attività. Quando la convalida viene richiamata sull'attività, questi avvisi o errori sono contenuti nella raccolta restituita dalla chiamata a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. Nell'esempio seguente viene definita un'attività `CreateProduct` . Se `Cost` è maggiore di `Price`, viene aggiunto un errore di convalida ai metadati nell'override di <xref:System.Activities.CodeActivity.CacheMetadata%2A>.  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error   
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 In questo esempio, un flusso di lavoro viene configurato usando l'attività `CreateProduct`. In questo flusso di lavoro, `Cost` è maggiore di `Price` e l'argomento obbligatorio `Description` non è impostato. Quando viene richiamata la convalida, vengono restituiti gli errori seguenti.  
  
```csharp  
Activity wf = new Sequence  
{  
    Activities =   
    {  
        new CreateProduct  
        {  
            Cost = 75.00,  
            Price = 55.00  
            // Cost > Price and required Description argument not set.  
        },  
        new WriteLine  
        {  
            Text = "Product added."  
        }  
    }  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 **Errore: Il costo deve essere minore o uguale al prezzo.**  
**Errore: Non è stato fornito alcun valore per un argomento di attività richiesta 'Description'.**    
> [!NOTE]
>  Gli autori di attività personalizzate possono fornire la logica di convalida nell'override di un'attività <xref:System.Activities.CodeActivity.CacheMetadata%2A>. Qualsiasi eccezione generata dal metodo <xref:System.Activities.CodeActivity.CacheMetadata%2A> non viene considerata come errore di convalida. Queste eccezioni saranno escluse dalla chiamata all'oggetto <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> e devono essere gestite dal chiamante.  
  
## <a name="using-validationsettings"></a>Utilizzo dell'oggetto ValidationSettings  
 Per impostazione predefinita, tutte le attività nell'albero delle attività vengono valutate quando la convalida viene richiamata da <xref:System.Activities.Validation.ActivityValidationServices>. <xref:System.Activities.Validation.ValidationSettings> consente di personalizzare la convalida in vari modi attraverso la configurazione delle relative tre proprietà. <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> specifica se il validator deve analizzare l'intero albero delle attività o applicare semplicemente la logica di convalida all'attività fornita. L'impostazione predefinita per questo valore è `false`. <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> specifica il mapping di vincoli aggiuntivi da un tipo a un elenco di vincoli. Per il tipo base di ogni attività nell'albero delle attività convalidata è disponibile una ricerca nella proprietà <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>. Se viene individuato un elenco di vincoli corrispondente, tutti i vincoli nell'elenco vengono valutati per l'attività. <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> specifica se tutti i vincoli o solo quelli specificati in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> devono essere valutati dal validator. Il valore predefinito è `false`. Gli autori di host del flusso di lavoro usano <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> e <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> per aggiungere un'ulteriore convalida ai flussi di lavoro, quali i vincoli di criteri per strumenti come FxCop. Per altre informazioni sui vincoli, vedere [vincoli dichiarativi](declarative-constraints.md).  
  
 Per usare l'oggetto <xref:System.Activities.Validation.ValidationSettings>, configurare le proprietà desiderate, quindi passarlo nella chiamata al metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>. In questo esempio viene convalidato un flusso di lavoro che è costituito da un oggetto <xref:System.Activities.Statements.Sequence> con un'attività `Add` personalizzata. L'attività `Add` dispone di due argomenti obbligatori.  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 L'attività `Add` seguente viene usata in un oggetto <xref:System.Activities.Statements.Sequence>, ma i due argomenti obbligatori non sono associati.  
  
```csharp  
Variable<int> Operand1 = new Variable<int> { Default = 10 };  
Variable<int> Operand2 = new Variable<int> { Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =   
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 Per l'esempio seguente, la convalida viene eseguita con la proprietà <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> impostata su `true`, pertanto solo l'attività <xref:System.Activities.Statements.Sequence> radice viene convalidata.  
  
```csharp  
ValidationSettings settings = new ValidationSettings  
{  
    SingleLevel = true  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 Di seguito viene visualizzato l'output del codice:  
  
 **Nessun avviso o errore** anche se il `Add` attività dispone di argomenti obbligatori che non sono associati, la convalida ha esito positivo perché viene valutata solo l'attività radice. Questo tipo di convalida è utile per convalidare solo elementi specifici in un albero delle attività, ad esempio la convalida di una modifica a una proprietà di una singola attività in una finestra di progettazione. Si noti che se questo flusso di lavoro viene richiamato, viene valutata l'intera convalida configurata nel flusso di lavoro ed eventualmente viene generata un'eccezione <xref:System.Activities.InvalidWorkflowException>. <xref:System.Activities.Validation.ActivityValidationServices> e <xref:System.Activities.Validation.ValidationSettings> configurano solo la convalida richiamata in modo esplicito dall'host e non la convalida che viene eseguita quando un flusso di lavoro viene richiamato.
