---
title: 'Procedura: Specificare una posizione personalizzata per un controllo Popup'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: dc516f0eb1cfcbac6662497eb4019041eefec2a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200584"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Procedura: Specificare una posizione personalizzata per un controllo Popup
In questo esempio viene illustrato come specificare una posizione personalizzata per un <xref:System.Windows.Controls.Primitives.Popup> controllare quando i <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.  
  
## <a name="example"></a>Esempio  
 Quando la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, il <xref:System.Windows.Controls.Primitives.Popup> chiama un'istanza definita del <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegare. Questo delegato restituisce un set di possibili punti relativi rispetto all'angolo superiore sinistro dell'area di destinazione e l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>. Il <xref:System.Windows.Controls.Primitives.Popup> posizionamento si verifica nel momento in cui offre la migliore visibilità.  
  
 Nell'esempio seguente viene illustrato come definire la posizione di un <xref:System.Windows.Controls.Primitives.Popup> impostando la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Viene inoltre illustrato come creare e assegnare un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato per posizionare il <xref:System.Windows.Controls.Primitives.Popup>.  Il delegato di callback restituisce due <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> oggetti.  Se il <xref:System.Windows.Controls.Primitives.Popup> è nascosto da un bordo dello schermo in corrispondenza della prima posizione, la <xref:System.Windows.Controls.Primitives.Popup> viene posizionato in corrispondenza della posizione di secondo.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Per l'esempio completo, vedere [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.Popup>
- [Cenni preliminari sul controllo Popup](popup-overview.md)
- [Procedure relative](popup-how-to-topics.md)
