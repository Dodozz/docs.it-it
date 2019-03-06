---
title: Associazione di una proprietà di attività personalizzata a un controllo di progettazione
ms.date: 03/30/2017
ms.assetid: 2e8061ea-10f5-407c-a31f-d0d74ce12f27
ms.openlocfilehash: 142a9eb273a98d3a2d83a1239d6d7c891d5cc305
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468572"
---
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a>Associazione di una proprietà di attività personalizzata a un controllo di progettazione

L'associazione di un controllo di progettazione casella di testo a un argomento di un'attività è abbastanza semplice; d'altra parte, l'associazione di un controllo di progettazione complesso (quale una casella combinata) a un argomento di un'attività può risultare problematica. In questo argomento viene illustrato come associare un argomento di un'attività a un controllo casella combinata in un ActivityDesigner personalizzato.

## <a name="creating-the-combo-box-item-converter"></a>Creazione del convertitore dell'elemento casella combinata

1. Creare una nuova soluzione vuota in Visual Studio 2010 denominata CustomProperty.

2. Creare una nuova classe denominata ComboBoxItemConverter. Aggiungere un riferimento a System.Windows.Data e fare in modo che la classe esegua la derivazione da <xref:System.Windows.Data.IValueConverter>. Impostare Visual Studio in modo che implementi l'interfaccia per generare stub per `Convert` e `ConvertBack`.

3. Aggiungere al metodo `Convert` il seguente codice. Questo codice converte l'oggetto <xref:System.Activities.InArgument%601> di tipo <xref:System.String> dell'attività nel valore da posizionare nella finestra di progettazione.

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            VisualBasicValue<string> vbexpression = expression as VisualBasicValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (vbexpression != null)
            {
                return vbexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

     L'espressione nell'esempio di codice precedente può essere creata anche usando <xref:Microsoft.CSharp.Activities.CSharpValue%601> anziché <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            CSharpValue<string> csexpression = expression as CSharpValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (csexpression != null)
            {
                return csexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

4. Aggiungere al metodo `ConvertBack` il seguente codice. Questo codice converte l'elemento casella combinata in ingresso nuovamente in <xref:System.Activities.InArgument%601>.

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(vbArgument);
                return inArgument;
    ```

     L'espressione nell'esempio di codice precedente può essere creata anche usando <xref:Microsoft.CSharp.Activities.CSharpValue%601> anziché <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(csArgument);
                return inArgument;
    ```

## <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a>Aggiunta di ComboBoxItemConverter all'ActivityDesigner personalizzato

1. Aggiungere un nuovo elemento al progetto. Nella finestra di dialogo Nuovo elemento, selezionare il nodo Flusso di lavoro, quindi selezionare ActivityDesigner come tipo del nuovo elemento. Denominare l'elemento CustomPropertyDesigner.

2. Aggiungere una casella combinata alla nuova finestra di progettazione. Nella proprietà Items aggiungere un paio di elementi alla casella combinata, con i valori di contenuto di "Item1" e 'Item2."

3. Modificare il codice XAML della casella combinata in modo da aggiungere il nuovo convertitore di elementi come convertitore di elementi da usare per la casella combinata. Il convertitore viene aggiunto come risorsa nel segmento ActivityDesigner.Resources e specifica il convertitore nell'attributo Converter di <xref:System.Windows.Controls.ComboBox>. Notare che lo spazio dei nomi del progetto viene specificato negli attributi degli spazi dei nomi di ActivityDesigner; se la finestra di progettazione deve essere usata in un progetto diverso, questo spazio dei nomi dovrà essere modificato.

    ```xaml
    <sap:ActivityDesigner x:Class="CustomProperty.CustomPropertyDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:c="clr-namespace:CustomProperty"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">

        <sap:ActivityDesigner.Resources>
            <ResourceDictionary>
                <c:ComboBoxItemConverter x:Key="comboBoxItemConverter"/>
            </ResourceDictionary>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ComboBox SelectedValue="{Binding Path=ModelItem.Text, Mode=TwoWay, Converter={StaticResource comboBoxItemConverter}}"  Height="23" HorizontalAlignment="Left" Margin="132,5,0,0" Name="comboBox1" VerticalAlignment="Top" Width="120" ItemsSource="{Binding}">
                <ComboBoxItem>item1</ComboBoxItem>
                <ComboBoxItem>item2</ComboBoxItem>
            </ComboBox>
        </Grid>
    </sap:ActivityDesigner>
    ```

4. Creare un nuovo elemento di tipo <xref:System.Activities.CodeActivity>. Il codice predefinito creato dall'IDE per l'attività sarà sufficiente per questo esempio.

5. Aggiungere l'attributo seguente alla definizione di classe:

    ```csharp
    [Designer(typeof(CustomPropertyDesigner))]
    ```

     Con questa riga si associa la nuova finestra di progettazione alla nuova classe.

 La nuova attività dovrebbe ora essere associata alla finestra di progettazione. Per testare la nuova attività, aggiungerla a un flusso di lavoro e impostare la casella combinata sui due valori. La finestra delle proprietà dovrebbe essere aggiornata per riflettere il valore della casella combinata.
