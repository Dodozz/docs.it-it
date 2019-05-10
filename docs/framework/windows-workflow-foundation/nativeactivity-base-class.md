---
title: Classe di base NativeActivity
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: 188181211c6171cfce07120b262c2cb798e52ad6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649351"
---
# <a name="nativeactivity-base-class"></a>Classe di base NativeActivity

<xref:System.Activities.NativeActivity> è una classe astratta con un costruttore protetto. Come l'oggetto <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> viene usato per la scrittura del comportamento imperativo implementando un metodo <xref:System.Activities.NativeActivity.Execute%2A>. A differenza dell'oggetto <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> dispone di accesso a tutte le funzionalità esposte dell'esecuzione del flusso di lavoro tramite l'oggetto <xref:System.Activities.NativeActivityContext> passato al metodo <xref:System.Activities.NativeActivity.Execute%2A>.

## <a name="using-nativeactivitycontext"></a>Uso di NativeActivityContext
 L'accesso a funzionalità dell'esecuzione del flusso di lavoro può essere eseguito dall'interno del metodo <xref:System.Activities.NativeActivity.Execute%2A> tramite i membri del parametro `context`, di tipo <xref:System.Activities.NativeActivityContext>. Tra le funzionalità disponibili tramite l'oggetto <xref:System.Activities.NativeActivityContext> sono incluse le seguenti:

- Recupero e impostazione di argomenti e variabili.

- Pianificazione delle attività figlio con il metodo <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>

- Interruzione dell'esecuzione di attività tramite il metodo <xref:System.Activities.NativeActivityContext.Abort%2A>.

- Annullamento dell'esecuzione di oggetti figlio tramite i metodi <xref:System.Activities.NativeActivityContext.CancelChild%2A> e <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.

- Accesso ai segnalibri delle attività tramite metodi come <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> e <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.

- Funzionalità di rilevamento personalizzate tramite <xref:System.Activities.CodeActivityContext.Track%2A>.

- Accesso alle proprietà di esecuzione e a quelle del valore dell'attività tramite i metodi <xref:System.Activities.CodeActivityContext.GetProperty%2A> e <xref:System.Activities.NativeActivityContext.GetValue%2A>.

- Pianificazione di azioni e funzioni di attività tramite <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> e <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a>Per creare un'attività personalizzata che eredita da NativeActivity

1. OpenVisual Studio 2010.

2. Selezionare **File**, **nuove**e quindi **progetto**. Selezionare **Workflow 4.0** sotto **Visual c#** nel **tipi di progetto** finestra e selezionare il **v2010** nodo. Selezionare **libreria di attività** nel **modelli** finestra. Assegnare al nuovo progetto il nome HelloActivity.

3. Fare doppio clic su Activity1.xaml nel progetto HelloActivity e selezionare **Elimina**.

4. Pulsante destro del mouse sul progetto HelloActivity e selezionare **Add**e quindi **classe**. Assegnare alla nuova classe il nome HelloActivity.cs.

5. Nel file HelloActivity.cs aggiungere le seguenti istruzioni `using`.

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. Assicurarsi che la nuova classe erediti dall'oggetto <xref:System.Activities.NativeActivity> aggiungendo una classe base alla dichiarazione di classe.

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. Aggiungere la funzionalità alla classe aggiungendo un metodo <xref:System.Activities.NativeActivity.Execute%2A>.

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. Eseguire l'override del metodo <xref:System.Activities.NativeActivity.CacheMetadata%2A> e chiamare il metodo Add appropriato per inviare al runtime del flusso di lavoro le informazioni sulle variabili, gli argomenti, gli elementi figlio e i delegati dell'attività personalizzata. Per altre informazioni, vedere la classe <xref:System.Activities.NativeActivityMetadata>.

9. Usare l'oggetto <xref:System.Activities.NativeActivityContext> per pianificare un segnalibro. Per informazioni dettagliate sulla creazione, pianificazione e ripresa di un segnalibro, vedere <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>.

    ```
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```