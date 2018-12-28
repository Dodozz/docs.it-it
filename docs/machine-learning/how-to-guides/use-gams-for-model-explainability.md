---
title: Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli in ML.NET
description: Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli in ML.NET
ms.date: 12/04/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 489aee34d0404293bc080b934636c01bdab92fe9
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156629"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a>Usare modelli additivi generalizzati e funzioni di forma per la comprensibilità dei modelli in ML.NET

Quando si creano modelli di Machine Learning, spesso non è sufficiente eseguire semplicemente stime. Spesso gli sviluppatori, i responsabili delle decisioni e gli utenti interessati ai modelli devono comprendere quali criteri vengono adottati dai modelli di Machine Learning per prendere decisioni e quali caratteristiche contribuiscono alle relative prestazioni. I **modelli additivi personalizzati** (GAM, Generalized Additive Model) vengono usati internamente presso Microsoft per la comprensibilità dei modelli in modo da aiutare gli sviluppatori di Machine Learning a creare modelli con capacità elevata facilmente interpretabili da altri.

I modelli GAM sono una classe di **modelli interpretabili**, ovvero modelli lineari in cui i termini sono funzioni non lineari, denominate "funzioni di forma" di una singola variabile. In quanto lineari, questi modelli vengono interpretati facilmente, ma poiché apprendono funzioni relative a caratteristiche anziché a una singola ponderazione, possono modellare relazioni più complesse rispetto a un modello lineare semplice. Il modello predittivo GAM risultante ha un termine di intercetta che rappresenta la stima media relativa al set di training e funzioni di forma che rappresentano la deviazione dalla stima media. Le funzioni di forma possono essere esaminate visivamente per verificare la risposta del modello ai diversi valori di una caratteristica e possono essere rappresentate con il grafico seguente, riportato dopo l'esempio di codice. L'algoritmo di apprendimento GAM in ML.NET viene implementato usando alberi con gradient boosting, ad esempio ceppi di albero, per apprendere le funzioni di forma non parametriche ed è basato sul metodo descritto nell'articolo [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (Modelli intelligibili per la classificazione e la regressione) di Lou, Caruana e Gehrke.

```csharp
// Train the Generalized Additive Model
var gamTrainer = mlContext.Regression.Trainers.GeneralizedAdditiveModels()
var gamModel = gamTrainer.Fit(data);
 
// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
 
// Get the feature names from the training set
var featureNames = data.Schema.GetColumns()
                .Select(tuple => tuple.column.Name) // Get the column names
                .Where(name => name != labelName) // Drop the Label
                .ToArray();
 
// Get the index of a variable from the training data
var myFeatureIndex = featureNames.ToList().FindIndex(str => str.Equals("MyFeature"));
 
// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetFeatureBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetFeatureWeights(myFeatureIndex);
 
// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
  Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
```

![Grafico delle funzioni di forma dei modelli additivi generalizzati](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

Per un esempio di come eseguire il training di un modello GAM e analizzare e interpretare i risultati, vedere il [repository dotnet/machinelearning in GitHub](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).