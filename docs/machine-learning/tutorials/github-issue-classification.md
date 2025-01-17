---
title: 'Esercitazione: Categorizzare i problemi di supporto - classificazione multiclasse'
description: Informazioni su come usare ML.NET in uno scenario di classificazione multiclasse per assegnare i problemi di GitHub a un'area specifica.
ms.date: 05/16/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: da4f82c1b2c4ebdc8ccc8f307722c2719909cf56
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2019
ms.locfileid: "66195583"
---
# <a name="tutorial-categorize-support-issues-using-multiclass-classification-with-ml-net"></a>Esercitazione: Categorizzare i problemi di supporto usando la classificazione multiclasse con ML NET

Questa esercitazione di esempio illustra come usare ML.NET per creare un classificatore di problemi di GitHub per eseguire il training di un modello che classifica e stima l'etichetta Area per un problema di GitHub tramite un'applicazione console .NET Core con C# in Visual Studio.

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> * Preparare i dati
> * Trasformare i dati
> * Eseguire il training del modello
> * Valutare il modello
> * Eseguire stime con il modello sottoposto a training
> * Eseguire distribuzione e stime con un modello caricato

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.

* Il [file separato da tabulazioni dei problemi di Github (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).
* Il [file di test separato da tabulazioni dei problemi di Github (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).

## <a name="create-a-console-application"></a>Creare un'applicazione console

### <a name="create-a-project"></a>Creare un progetto

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**. Selezionare quindi il modello di progetto **App console (.NET Core)** . Nella casella di testo **Nome** digitare "GitHubIssueClassification" e quindi selezionare il pulsante **OK**.

2. Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**. Digitare "Data" e premere INVIO.

3. Creare una directory denominata *Models* nel progetto per salvare il modello:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**. Digitare "Models" e premere INVIO.

4. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto **v 1.0.0** nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

### <a name="prepare-your-data"></a>Preparare i dati

1. Scaricare i set di dati [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) e [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) e salvarli nella cartella *Data* creata in precedenza. Il primo set di dati esegue il training del modello di apprendimento automatico e il secondo può essere usato per valutare il livello di accuratezza del modello.

2. In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione tsv e selezionare **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

Creare tre campi globali per i percorsi dei file scaricati di recente e variabili globali per `MLContext`,`DataView` e `PredictionEngine`:

* `_trainDataPath` contiene il percorso del set di dati usato per il training del modello.
* `_testDataPath` contiene il percorso del set di dati usato per valutare il modello.
* `_modelPath` contiene il percorso in cui è salvato il modello sottoposto a training.
* `_mlContext` è l'elemento <xref:Microsoft.ML.MLContext> che specifica il contesto di elaborazione.
* `_trainingDataView` è l'elemento <xref:Microsoft.ML.IDataView> usato per elaborare il set di dati di training.
* `_predEngine` è l'elemento <xref:Microsoft.ML.PredictionEngine%602> usato per le stime singole.

Aggiungere il codice seguente nella riga subito sopra il metodo `Main` per specificare questi percorsi e le altre variabili:

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

Creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il valore del campo **Nome** impostando *GitHubIssueData.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *GitHubIssueData.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio del file *GitHubIssueData.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `GitHubIssue` e `IssuePrediction`, al file *GitHubIssueData.cs*:

[!code-csharp[DeclareGlobalVariables](~/samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

`label` è la colonna da stimare. Gli elementi `Features` identificati sono gli input indicati al modello per stimare l'etichetta.

Usare [LoadColumnAttribute](xref:Microsoft.ML.Data.LoadColumnAttribute) per specificare gli indici delle colonne di origine nel set di dati.

`GitHubIssue` è la classe del set di dati input e ha i seguenti campi <xref:System.String>:

* La prima colonna `ID` (ID problema di GitHub)
* La seconda colonna `Area` (stima per il training)
* La terza colonna `Title` (titolo del problema GitHub) è la prima `feature` usata per la stima di `Area`
* La quarta colonna `Description` è la seconda `feature` usata per la stima di `Area`

`IssuePrediction` è la classe usata per la stima dopo il training del modello. Dispone di un `string` singolo (`Area`) e di un attributo `PredictedLabel` `ColumnName`.  `PredictedLabel` viene usato durante la valutazione e la stima. Per la valutazione vengono usati un input con dati di training, i valori stimati e il modello.

Tutte le operazioni ML.NET iniziano nella classe [MLContext](xref:Microsoft.ML.MLContext). L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in `Entity Framework`.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

Inizializzare la variabile globale `_mlContext` con una nuova istanza di `MLContext` con un valore di inizializzazione casuale (`seed: 0`) per risultati ripetibili/deterministici in più training.  Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a>Caricare i dati

ML.NET usa la [classe IDataView](xref:Microsoft.ML.IDataView) come un modo efficiente e flessibile per descrivere i dati tabulari numerici o di testo. `IDataView` può caricare file testo o in tempo reale (ad esempio, file di database SQL o di log).

Per inizializzare e caricare la variabile globale `_trainingDataView` in modo da riusarla per la pipeline, aggiungere il codice seguente dopo l'inizializzazione di `mlContext`:

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]

[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema dei dati e legge il contenuto del file. Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.

Aggiungere il codice seguente al metodo `Main` come riga successiva:

[!code-csharp[CallProcessData](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

Il metodo `ProcessData` esegue le attività seguenti:

* Estrae e trasforma i dati.
* Restituisce la pipeline di elaborazione.

Creare il metodo `ProcessData` subito dopo il metodo `Main`, usando il codice seguente:

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a>Estrarre le funzionalità e trasformare i dati

Dato che si vuole stimare l'etichetta GitHub Area per un `GitHubIssue`, usare il metodo [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) per trasformare la colonna `Area` in una colonna `Label` di tipo chiave numerica (un formato accettato dagli algoritmi di classificazione) e aggiungerla come nuova colonna del set di dati:

[!code-csharp[MapValueToKey](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

Chiamare quindi `mlContext.Transforms.Text.FeaturizeText` che trasforma le colonne di testo (`Title` e `Description`) in un vettore numerico per ogni `TitleFeaturized` e `DescriptionFeaturized` di cui è stata eseguita la chiamata. Aggiungere l'estrazione delle funzionalità per entrambe le colonne alla pipeline con il codice seguente:

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando il metodo [Concatenate()](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate%2A). Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**. Aggiungere questa trasformazione alla pipeline con il codice seguente:

[!code-csharp[Concatenate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 Aggiungere quindi <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> per memorizzare nella cache la vista dati e ottenere prestazioni migliori quando si esegue più volte l'iterazione dei dati usando la cache, come nel codice seguente:

[!code-csharp[AppendCache](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> Usare AppendCacheCheckpoint per i set di dati di piccole e medie dimensioni per ridurre i tempi di training. NON usarlo (rimuovere. AppendCacheCheckpoint()) durante la gestione di set di dati molto grandi.

Applicare return alla pipeline alla fine del metodo `ProcessData`.

[!code-csharp[ReturnPipeline](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

Questo passaggio gestisce la pre-elaborazione/estrazione delle funzionalità. Usando i componenti aggiuntivi disponibili in ML.NET, è possibile ottenere risultati migliori con il modello.

## <a name="build-and-train-the-model"></a>Compilare ed eseguire il training del modello

Aggiungere la seguente chiamata al metodo `BuildAndTrainModel` come riga successiva nel metodo `Main`:

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

Il metodo `BuildAndTrainModel` esegue le attività seguenti:

* Crea la classe di algoritmo di training.
* Esegue il training del modello.
* Esegue la stima dell'area sulla base dei dati di training.
* Restituisce il modello.

Creare il metodo `BuildAndTrainModel` subito dopo il metodo `Main`, usando il codice seguente:

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

### <a name="about-the-classification-task"></a>Informazioni sull'attività di classificazione

La classificazione è un'attività di apprendimento automatico che usa i dati per **determinare** la categoria, il tipo o la classe di un elemento o una riga di dati ed è spesso di uno dei tipi seguenti:

* Binarie: A o B.
* Multiclasse: più categorie che possono essere stimate tramite un singolo modello.

Per questo tipo di problema, usare un algoritmo di Machine Learning di classificazione multiclasse, poiché la stima della categoria di problemi può essere una tra più categorie (multiclasse) anziché solo due categorie (binarie).

Aggiungere l'algoritmo di apprendimento automatico alle definizioni di trasformazione dei dati aggiungendo il codice seguente come prima riga di codice in `BuildAndTrainModel()`:

[!code-csharp[AddTrainer](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

[SdcaMaximumEntropy](xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer) è l'algoritmo di training di classificazione multiclasse. Viene aggiunto a `pipeline` e accetta gli elementi `Title` e `Description` (`Features`) con estrazione di funzionalità e i parametri di input `Label` per l'apprendimento dai dati cronologici.

### <a name="train-the-model"></a>Eseguire il training del modello

Eseguire il fit del modello ai dati `splitTrainSet` e restituire il modello sottoposto a training aggiungendo il codice seguente come riga successiva nel metodo `BuildAndTrainModel()`:

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

Il metodo `Fit()` esegue il training del modello trasformando il set di dati e applicando il training.

[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di servizio che consente di passare e quindi eseguire una stima su una singola istanza di dati. Aggiungere il codice seguente come riga successiva nel metodo `BuildAndTrainModel()`:

[!code-csharp[CreatePredictionEngine1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a>Eseguire stime con il modello sottoposto a training

Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:

[!code-csharp[CreateTestIssue1](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

Usare la funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) per eseguire una stima su una singola colonna di dati:

[!code-csharp[Predict](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a>Uso del modello: risultati della stima

Visualizzare `GitHubIssue` e la stima dell'etichetta `Area` corrispondente per condividere i risultati e agire su di essi di conseguenza.  Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a>Restituire il modello di cui è stato eseguito il training da usare per la valutazione

Restituire il modello alla fine del metodo `BuildAndTrainModel`.

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a>Valutare il modello

Ora che è stato creato ed eseguito il training del modello, è necessario valutarlo con un set di dati diverso per il controllo di qualità e la convalida. Nel metodo `Evaluate` viene passato il modello creato in `BuildAndTrainModel` per la valutazione. Creare il metodo `Evaluate` subito dopo `BuildAndTrainModel`, come nel codice seguente:

```csharp
public static void Evaluate(DataViewSchema trainingDataViewSchema)
{

}
```

Il metodo `Evaluate` esegue le attività seguenti:

* Carica il set di dati di test.
* Crea l'analizzatore multiclasse.
* Valuta il modello e crea le metriche.
* Visualizza le metriche.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `BuildAndTrainModel`, usando il codice seguente:

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

Come in precedenza con il training set, caricare il set di dati di test aggiungendo il codice seguente al metodo `Evaluate`:

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

Il metodo [Evaluate()](xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A) calcola le metriche di qualità per il modello usando il set di dati specificato. Restituisce un oggetto <xref:Microsoft.ML.Data.MulticlassClassificationMetrics> che contiene le metriche complessive calcolate dagli analizzatori della classificazione multiclasse.
Per visualizzare la metrica per determinare la qualità del modello, è prima necessario ottenerla.
Osservare l'uso del metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) della variabile globale `_trainedModel` di apprendimento automatico (un oggetto [ITransformer](xref:Microsoft.ML.ITransformer)) per l'input di funzionalità e la generazione di stime. Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:

[!code-csharp[Evaluate](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

Le metriche seguenti vengono valutate per la classificazione multiclasse:

* MicroAccuracy (Accuratezza micro): ogni coppia campione-classe contribuisce nello stesso modo alla metrica di accuratezza.  Il valore desiderato per MicroAccuracy è il valore più prossimo a 1.

* MacroAccuracy (Accuratezza macro): ogni classe contribuisce nello stesso modo alla metrica di accuratezza. Alle classi di minoranza viene assegnato un peso uguale a quello delle classi più grandi. Il valore desiderato per MacroAccuracy è il valore più prossimo a 1.

* LogLoss (Perdita di log): vedere [Perdita di log](../resources/glossary.md#log-loss). Il valore desiderato per LogLoss è il valore più prossimo a 0.

* LogLossReduction (Riduzione della perdita di log): è compreso nell'intervallo [-inf, 100], dove 100 corrisponde a stime perfette e 0 indica stime medie. Il valore desiderato per LogLossReduction è il valore più prossimo a 0.

### <a name="displaying-the-metrics-for-model-validation"></a>Visualizzazione delle metriche per la convalida del modello

Usare il codice seguente per visualizzare le metriche, condividere i risultati e quindi intervenire su di essi:

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

## <a name="deploy-and-predict-with-a-model"></a>Eseguire distribuzione e stime con un modello

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:

[!code-csharp[CallPredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

Creare il metodo `PredictIssue`, subito dopo il metodo `Evaluate` e subito prima del metodo `SaveModelAsFile`, usando il codice seguente:

```csharp
private static void PredictIssue()
{

}
```

Il metodo `PredictIssue` esegue le attività seguenti:

* Crea un singolo problema con dati di test.
* Esegue la stima dell'Area in base ai dati di test.
* Combina i dati di test e le stime per i report.
* Visualizza i risultati stimati.

Aggiungere un problema di GitHub per testare la stima del modello sottoposto a training nel metodo `Predict` creando un'istanza di `GitHubIssue`:

[!code-csharp[AddTestIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

Come in precedenza, creare un'istanza `PredictionEngine` con il codice seguente:

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
Usare `PredictionEngine` per stimare l'etichetta di Area GitHub aggiungendo il codice seguente al metodo `PredictIssue` per la stima:

[!code-csharp[PredictIssue](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a>Uso del modello caricato per la stima

Visualizzare `Area` per classificare il problema e agire su di esso di conseguenza. Creare una visualizzazione per i risultati usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[DisplayResults](~/samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a>Risultati

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione della pipeline, vengono visualizzati messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi messaggi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.738
*       MacroAccuracy:    0.668
*       LogLoss:          .919
*       LogLossReduction: .643
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

La procedura è stata completata. È stato creato correttamente un modello di apprendimento automatico per la classificazione e la stima di un'etichetta Area per un problema di GitHub. È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> * Preparare i dati
> * Trasformare i dati
> * Eseguire il training del modello
> * Valutare il modello
> * Eseguire stime con il modello sottoposto a training
> * Eseguire distribuzione e stime con un modello caricato

Passare all'esercitazione successiva per altre informazioni
> [!div class="nextstepaction"]
> [Previsione tariffe dei taxi](taxi-fare.md)
