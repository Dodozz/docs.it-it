---
title: "Procedura: Eseguire l'override dei metadati per una proprietà di dipendenza"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
ms.openlocfilehash: ba2f98d262f5c43dbd0c07d356556cdc3ec4b8dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589753"
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a>Procedura: Eseguire l'override dei metadati per una proprietà di dipendenza
Questo esempio illustra come eseguire l'override di metadati di proprietà di dipendenza predefinito che derivano da una classe ereditata, chiamando il <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> (metodo) e fornendo i metadati specifici del tipo.  
  
## <a name="example"></a>Esempio  
 Con la definizione relativa <xref:System.Windows.PropertyMetadata>, una classe possa definire i comportamenti della proprietà di dipendenza, ad esempio il callback del sistema predefinita valore e proprietà. Molte classi della proprietà di dipendenza dispongono già di metadati predefiniti stabiliti nell'ambito del processo di registrazione. Sono incluse le proprietà di dipendenza che fanno parte delle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]. Una classe che eredita la proprietà di dipendenza tramite l'ereditarietà di classe può eseguire l'override dei metadati originali in modo che le caratteristiche della proprietà che è possibile modificare tramite i metadati soddisfino qualsiasi requisito specifico della sottoclasse.  
  
 L'override dei metadati di una proprietà di dipendenza deve essere eseguito prima che la proprietà venga resa utilizzabile dal sistema di proprietà, vale a dire nel momento in cui vengono create istanze specifiche degli oggetti che registrano la proprietà. Le chiamate a <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> devono essere eseguite all'interno dei costruttori statici del tipo che fornisce se stesso come il `forType` parametro di <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>. Il tentativo di modificare i metadati dopo la creazione delle istanze del tipo di proprietario non genererà eccezioni, ma darà come risultato comportamenti incoerenti nel sistema di proprietà. Inoltre, l'override dei metadati può essere eseguito solo una volta per tipo. I tentativi successivi di eseguire l'override dei metadati sullo stesso tipo genereranno un'eccezione.  
  
 Nell'esempio seguente la classe personalizzata `MyAdvancedStateControl` esegue l'override dei metadati forniti per `StateProperty` da `MyAdvancedStateControl` con i nuovi metadati delle proprietà. Ad esempio, il valore predefinito di `StateProperty` sarà `true` quando viene eseguita una query sulla proprietà in un'istanza `MyAdvancedStateControl` appena creata.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.DependencyProperty>
- [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
