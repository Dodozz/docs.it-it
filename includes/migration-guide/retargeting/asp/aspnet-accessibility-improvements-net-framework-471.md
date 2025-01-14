---
ms.openlocfilehash: 1b68caebb3abad36f1809ff3ba096b24de3e1ab4
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211992"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a>Miglioramenti di accessibilità ASP.NET in .NET Framework 4.7.1

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.1, in ASP.NET è stato migliorato il funzionamento dei controlli Web ASP.NET con tecnologia di accessibilità in Visual Studio per supportare al meglio i clienti ASP.NET.  Sono incluse le modifiche seguenti:<ul><li>Modifiche per implementare pattern di accessibilità dell'interfaccia utente mancanti nei controlli, come la finestra di dialogo Aggiungi campo nella procedura guidata DetailsView o la finestra di dialogo Configura ListView nella procedura guidata ListView.</li><li>Modifiche per migliorare la visualizzazione nella modalità a contrasto elevato, ad esempio l'Editor campi del pager di dati.</li><li>Modifiche per migliorare la navigazione tramite tastiera per controlli, come la finestra di dialogo Campi nella procedura guidata Modifica campi del pager del controllo DataPager, la finestra di dialogo Configura ObjectContext o la finestra di dialogo Configura selezione dati della procedura guidata Configura origine dati.</li></ul>|
|Suggerimento|<strong>Come accettare o rifiutare queste modifiche</strong> Per poter usufruire di queste modifiche nella finestra di progettazione di Visual Studio, l'applicazione deve essere eseguita in .NET Framework 4.7.1 o versione successiva. L'applicazione Web può trarre vantaggio da queste modifiche in uno dei modi seguenti:<ul><li>Installare Visual Studio 2017 15.3 o versione successiva, che supporta le nuove funzionalità di accessibilità con l'opzione di AppContext seguente per impostazione predefinita.</li><li>Rifiutare i comportamenti di accessibilità legacy aggiungendo l'<code>Switch.UseLegacyAccessibilityFeatures</code>opzione di AppContext alla sezione <code>&lt;runtime&gt;</code> del file di configurazione devenv.config e impostandola su <code>false</code>, come illustrato nell'esempio seguente.</li></ul><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;...&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false&#39;  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;...&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Le applicazioni che usano .NET Framework 4.7.1 o versione successiva e che vogliono mantenere il comportamento di accessibilità legacy possono scegliere di usare le funzionalità di accessibilità legacy impostando in modo esplicito questa opzione di AppContext su <code>true</code>.|
|Ambito|Secondario|
|Versione|4.7.1|
|Tipo|Ridestinazione|
