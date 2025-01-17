---
title: Attributi e commenti di localizzazione
ms.date: 03/30/2017
helpviewer_keywords:
- localization [WPF], attributes
- localization [WPF], comments
ms.assetid: ead2d9ac-b709-4ec1-a924-39927a29d02f
ms.openlocfilehash: a242dc1f69c79b2c1a67c1a9235d3e942553caf1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598736"
---
# <a name="localization-attributes-and-comments"></a>Attributi e commenti di localizzazione
I commenti di localizzazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sono proprietà all'interno del codice sorgente [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] usate dagli sviluppatori per fornire regole e suggerimenti per la localizzazione. I commenti di localizzazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contengono due set di informazioni: attributi di localizzabilità e commenti di localizzazione in formato libero. Gli attributi di localizzabilità vengono usati dall'API di localizzazione di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per indicare le risorse da localizzare. I commenti in formato libero comprendono tutte le informazioni che l'autore dell'applicazione vuole includere.  

<a name="Localizer_Comments_"></a>   
## <a name="localization-comments"></a>Commenti di localizzazione  
 Se gli autori dell'applicazione di markup necessitano di elementi specifici nel codice [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], ad esempio vincoli relativi alla lunghezza del testo, alla famiglia o alle dimensioni del carattere, possono trasmettere queste informazioni ai localizzatori con commenti nel codice [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Il processo di aggiunta di commenti al codice sorgente è il seguente:  
  
1. Lo sviluppatore dell'applicazione aggiunge i commenti di localizzazione al codice sorgente [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
2. Durante il processo di compilazione, nel file con estensione proj è possibile specificare se mantenere i commenti di localizzazione in formato libero nell'assembly, se rimuoverne una parte o se rimuoverli tutti. I commenti rimossi vengono inseriti in un file separato. Per indicare la scelta si usa un tag `LocalizationDirectivesToLocFile`, ad esempio:  
  
     `<LocalizationDirectivesToLocFile>` *valore* `</LocalizationDirectivesToLocFile>`  
  
3. I valori che è possibile assegnare sono:  
  
    - **None**: sia i commenti che gli attributi rimangono nell'assembly e non viene generato alcun file separato.  
  
    - **CommentsOnly**: dall'assembly vengono rimossi solo i commenti, che vengono inseriti nel LocFile separato.  
  
    - **All**: dall'assembly vengono rimossi sia i commenti che gli attributi, che vengono inseriti entrambi in un LocFile separato.  
  
4. Se le risorse localizzabili vengono estratte da [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)], l'API di localizzazione di [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)] rispetta gli attributi di localizzabilità.  
  
5. I file dei commenti di localizzazione, nei quali sono contenuti solo commenti in formato libero, vengono incorporati al processo di localizzazione in un secondo momento.  
  
 L'esempio seguente illustra come aggiungere commenti di localizzazione a un file [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
 `<TextBlock x:Id = "text01"`  
  
 `FontFamily = "Microsoft Sans Serif"`  
  
 `FontSize = "12"`  
  
 `Localization.Attributes = "$Content (Unmodifiable Readable Text)`  
  
 `FontFamily (Unmodifiable Readable)"`  
  
 `Localization.Comments = "$Content (Trademark)`  
  
 `FontSize (Trademark font size)" >`  
  
 `Microsoft`  
  
 `</TextBlock>`  
  
 Nella sezione Localization.Attributes dell'esempio precedente sono disponibili gli attributi di localizzazione, mentre nella sezione Localization.Comments sono disponibili i commenti in formato libero. La tabella seguente illustra gli attributi, i commenti e il relativo significato per il localizzatore.  
  
|Attributi di localizzazione|Significato|  
|-----------------------------|-------------|  
|$Content (testo leggibile non modificabile)|Il contenuto dell'elemento TextBlock non può essere modificato. I localizzatori non possono modificare la parola "Microsoft". Il contenuto è visibile (leggibile) per il localizzatore. La categoria del contenuto è testo.|  
|FontFamily (leggibile non modificabile)|La proprietà della famiglia di caratteri dell'elemento TextBlock non può essere modificata, ma è visibile per il localizzatore.|  
  
|Commenti di localizzazione in formato libero|Significato|  
|--------------------------------------|-------------|  
|$Content (marchio)|L'autore dell'applicazione indica al localizzatore che il contenuto dell'elemento TextBlock è un marchio.|  
|FontSize (dimensioni del carattere del marchio)|L'autore dell'applicazione indica che la proprietà delle dimensioni del carattere deve rispettare la dimensione standard del marchio.|  
  
### <a name="localizability-attributes"></a>Attributi di localizzabilità  
 Le informazioni disponibili nella sezione Localization.Attributes contengono un elenco di coppie: il nome del valore di destinazione e i valori di localizzabilità associati. Il nome di destinazione può essere un nome di proprietà o il nome speciale $Content. Se si tratta di un nome di proprietà, il valore di destinazione è il valore della proprietà. Se si tratta di $Content, il valore di destinazione è il contenuto dell'elemento.  
  
 Sono disponibili tre tipi di attributi:  
  
- **Category**. Specifica se un valore può essere modificato con uno strumento del localizzatore. Vedere <xref:System.Windows.LocalizabilityAttribute.Category%2A>.  
  
- **Leggibilità**. Specifica se uno strumento del localizzatore deve essere in grado di leggere (e visualizzare) un valore. Vedere <xref:System.Windows.LocalizabilityAttribute.Readability%2A>.  
  
- **Modificabilità**. Specifica se uno strumento del localizzatore consente la modifica di un valore. Vedere <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>.  
  
 Questi attributi possono essere specificati in qualsiasi ordine e devono essere delimitati da uno spazio. Nel caso in cui vengano specificati attributi duplicati, l'ultimo sostituisce i precedenti. Ad esempio, Localization.Attributes = "Unmodifiable Modifiable" imposta Modifiability su Modifiable poiché questo è l'ultimo valore.  
  
 Gli attributi Modifiability e Readability sono di facile comprensione. L'attributo Category fornisce categorie predefinite che supportano il localizzatore nella traduzione del testo. Categorie quali Text, Label e Title offrono al localizzatore informazioni sulla modalità di traduzione del testo. Sono disponibili anche categorie speciali: None, ereditano, ignorare e NeverLocalize.  
  
 La tabella seguente illustra il significato delle categorie speciali.  
  
|Category|Significato|  
|--------------|-------------|  
|nessuno|Per il valore di destinazione non è definita alcuna categoria.|  
|Eredita|Il valore di destinazione eredita la categoria dall'elemento padre.|  
|Ignora|Il valore di destinazione viene ignorato nel processo di localizzazione. Questa categoria influisce solo sul valore corrente e non sui nodi figlio.|  
|NeverLocalize|Il valore corrente non può essere localizzato. Questa categoria viene ereditata dagli elementi figlio di un elemento.|  
  
<a name="Localization_Comments"></a>   
## <a name="localization-comments"></a>Commenti di localizzazione  
 La sezione Localization.Comments contiene le stringhe in formato libero relative al valore di destinazione. Gli sviluppatori dell'applicazione possono aggiungere informazioni per offrire ai localizzatori suggerimenti sulla modalità di traduzione del testo delle applicazioni. Il formato dei commenti può essere una qualsiasi stringa racchiusa tra "()". Usare '\\' come carattere di escape.  
  
## <a name="see-also"></a>Vedere anche

- [Globalizzazione per WPF](globalization-for-wpf.md)
- [Utilizzare un layout automatico per creare un pulsante](how-to-use-automatic-layout-to-create-a-button.md)
- [Usare una griglia per il layout automatico](how-to-use-a-grid-for-automatic-layout.md)
- [Localizzare un'applicazione](how-to-localize-an-application.md)
