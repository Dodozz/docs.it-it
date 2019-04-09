---
title: Esempio di pacchetto di tipi di carattere OpenType
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: 96a0a5feaf14a7f040402681e90fba8f9766324b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199037"
---
# <a name="sample-opentype-font-pack"></a>Esempio di pacchetto di tipi di carattere OpenType
Questo argomento offre una panoramica dei tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] di esempio distribuiti con [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)]. I tipi di carattere di esempio supportano funzionalità [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] estese che possono essere usate dalle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

<a name="overview"></a>   
## <a name="fonts-in-the-opentype-font-pack"></a>Tipi di carattere nel pacchetto di caratteri OpenType  
 [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] contiene un set di tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] di esempio che è possibile usare nella creazione di applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. I tipi di carattere di esempio sono concessi in licenza da Ascender Corporation. Questi tipi di carattere implementano solo un subset delle funzionalità totali definite dal formato [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]. La tabella seguente contiene un elenco dei nomi dei tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] di esempio.  
  
|**Nome**|**File**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Bold|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero Bold|Pescab.ttf|  
  
 La figura seguente illustra l'aspetto dei tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)].  
  
 ![Elenco di nomi di carattere nel pacchetto di caratteri di esempio](./media/sample-opentype-font-pack/font-names-sample-pack.gif)  
  
 I tipi di carattere di esempio sono concessi in licenza da Ascender Corporation. Ascender è un provider di tipi di carattere avanzati. Per ottenere in licenza versioni estese o personalizzate dei tipi di carattere di esempio, vedere il [sito Web di Ascender Corporation](https://go.microsoft.com/fwlink/?LinkId=182627).  
  
> [!NOTE]
>  È responsabilità degli sviluppatori verificare di disporre dei diritti di licenza necessari per qualsiasi tipo di carattere incorporato all'interno di un'applicazione o ridistribuito in altro modo.  
  
<a name="installing_the_fonts"></a>   
## <a name="installing-the-fonts"></a>Installazione dei tipi di carattere  
 È possibile installare i tipi di carattere [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] di esempio nella directory dei tipi di carattere di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] predefinita, ovvero **\WINDOWS\Fonts**. Per l'installazione, usare il pannello di controllo Tipi di carattere. Dopo l'installazione nel computer, questi tipi di carattere saranno accessibili a tutte le applicazioni che fanno riferimento ai tipi di carattere predefiniti di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. È possibile visualizzare un set di caratteri rappresentativo in diverse dimensioni facendo doppio clic sul file del tipo di carattere. La screenshot seguente mostra il file del tipo di carattere Lindsey, ovvero Linds.ttf.  
  
 ![Tipo di carattere Lindsey &#40;OpenType&#41;](./media/typographyinwpf-04.png "TypographyInWPF_04")  
Visualizzazione del tipo di carattere Lindsey  
  
<a name="using_the_fonts"></a>   
## <a name="using-the-fonts"></a>Uso dei tipi di carattere  
 Nell'applicazione si possono usare i tipi di carattere in due modi. È possibile aggiungere tipi di carattere all'applicazione come elementi di contenuto del progetto non incorporati come risorse in un assembly. In alternativa, si possono aggiungere tipi di carattere all'applicazione come elementi risorsa del progetto incorporati nei file di assembly dell'applicazione. Per altre informazioni, vedere [Includere i tipi di carattere nel pacchetto delle applicazioni](packaging-fonts-with-applications.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Documents.Typography>
- [Funzionalità dei tipi di carattere OpenType](opentype-font-features.md)
- [Includere i tipi di carattere nel pacchetto delle applicazioni](packaging-fonts-with-applications.md)
