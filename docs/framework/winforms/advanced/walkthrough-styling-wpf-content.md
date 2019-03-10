---
title: 'Procedura dettagliata: Applicazione degli stili WPF contenuto'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 6329f25b8ead128c32ae0c7aca1f0bceaac8474c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712396"
---
# <a name="walkthrough-styling-wpf-content"></a>Procedura dettagliata: Applicazione degli stili WPF contenuto
Questa procedura dettagliata mostra come applicare uno stile a un controllo Windows Presentation Foundation (WPF) incluso in un Windows Form.

 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:

-   Creare il progetto.

-   Creare il tipo di controllo WPF.

-   Applicare uno stile al controllo WPF.

> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   Visual Studio 2012.  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto Windows Form.  
  
> [!NOTE]
>  Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
-   Creare un nuovo progetto Windows Forms Application in Visual Basic o Visual c# denominato `StylingWpfContent`.  
  
## <a name="creating-the-wpf-control-types"></a>Creazione di tipi di controllo WPF  
 Dopo avere aggiunto un tipo di controllo WPF al progetto, è possibile inserirlo in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### <a name="to-create-wpf-control-types"></a>Per creare i tipi di controllo WPF  
  
1.  Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per altre informazioni, vedere [Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  In visualizzazione Progettazione verificare che `UserControl1` sia selezionato. Per altre informazioni, vedere [Procedura: Selezionare e spostare gli elementi nell'area di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).  
  
3.  Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da `200`.  
  
4.  Aggiungere un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> il controllo al <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà **Annulla**.  
  
5.  Aggiungere una seconda <xref:System.Windows.Controls.Button?displayProperty=nameWithType> il controllo al <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà **OK**.  
  
6.  Compilare il progetto.  
  
## <a name="applying-a-style-to-a-wpf-control"></a>Applicazione di uno stile a un controllo WPF  
 È possibile applicare uno stile diverso a un controllo WPF per modificarne l'aspetto e il comportamento.  
  
#### <a name="to-apply-a-style-to-a-wpf-control"></a>Per applicare uno stile a un controllo WPF  
  
1.  Aprire `Form1` in Progettazione Windows Form.  
  
2.  Nel **casella degli strumenti**, fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.  
  
     L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.  
  
3.  Nel pannello smart tag per `elementHost1`, fare clic su **modifica contenuto ospitato** nell'elenco a discesa.  
  
     `UserControl1` si apre in [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  Nella visualizzazione XAML inserire il seguente codice XAML dopo il tag di apertura `<UserControl>`.  
  
     Questo codice XAML crea una sfumatura con un bordo sfumato a contrasto. Quando si fa clic sul controllo, le sfumature vengono modificate per generare l'aspetto di un pulsante premuto. Per altre informazioni, vedere [Applicazione di stili e modelli](../../wpf/controls/styling-and-templating.md).  
  
```xaml  
<UserControl.Resources>  
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#FFF" Offset="0.0"/>  
        <GradientStop Color="#CCC" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#BBB" Offset="0.0"/>  
        <GradientStop Color="#EEE" Offset="0.1"/>  
        <GradientStop Color="#EEE" Offset="0.9"/>  
        <GradientStop Color="#FFF" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#444" Offset="0.0"/>  
        <GradientStop Color="#888" Offset="1.0"/>  
    </LinearGradientBrush>  
  
    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>  
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>  
        <Setter Property="Template">  
            <Setter.Value>  
                <ControlTemplate TargetType="{x:Type Button}">  
                    <Grid x:Name="Grid">  
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>  
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>  
                    </Grid>  
                    <ControlTemplate.Triggers>  
                        <Trigger Property="IsPressed" Value="true">  
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>  
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>  
                        </Trigger>  
                    </ControlTemplate.Triggers>  
                </ControlTemplate>  
            </Setter.Value>  
        </Setter>  
    </Style>  
</UserControl.Resources>  
```  
  
1.  Applicare al pulsante Cancel lo stile `SimpleButton` definito nel passaggio precedente inserendo il seguente codice XAML nel tag `<Button>` del pulsante Cancel.  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     La dichiarazione del pulsante sarà simile al seguente codice XAML.  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1.  Compilare il progetto.  
  
2.  Aprire `Form1` in Progettazione Windows Form.  
  
3.  Il nuovo stile viene applicato al pulsante.  
  
4.  Dal **Debug** dal menu **Avvia debug** per eseguire l'applicazione.  
  
5.  Fare clic sui pulsanti OK e Cancel e visualizzare le differenze.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](../../wpf/advanced/migration-and-interoperability.md)
- [Uso di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Cenni preliminari su XAML (WPF)](../../wpf/advanced/xaml-overview-wpf.md)
- [Applicazione di stili e modelli](../../wpf/controls/styling-and-templating.md)
