---
title: 'Procedura: Copiare ToolStripMenuItems'
ms.date: 03/30/2017
helpviewer_keywords:
- menu items [Windows Forms], copying and pasting
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], copying and pasting
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
ms.openlocfilehash: 18077f542b1b49f8e81e68fc1e7a5d3e1e417a21
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713878"
---
# <a name="how-to-copy-toolstripmenuitems"></a>Procedura: Copiare ToolStripMenuItems
In fase di progettazione è possibile copiare interi menu di primo livello e le voci dei relativi sottomenu in un'altra posizione in <xref:System.Windows.Forms.MenuStrip>. È anche possibile copiare singole voci di menu tra i menu di primo livello o modificare la posizione delle voci di menu all'interno di un menu.  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-another-top-level-location"></a>Per copiare un menu di primo livello e le voci dei relativi sottomenu in un'altra posizione di primo livello  
  
1.  Fare clic sul menu da copiare, premere CTRL+C o fare clic con il pulsante destro del mouse sul menu e selezionare **Copia** dal menu di scelta rapida.  
  
2.  Fare clic sul menu di primo livello dopo la nuova posizione individuata e premere CTRL+V oppure fare clic con il pulsante destro del mouse sulla voce di menu di primo livello che precede la nuova posizione e selezionare **Incolla** dal menu di scelta rapida.  
  
     Il menu copiato viene inserito prima del menu di primo livello selezionato.  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-a-drop-down-location"></a>Per copiare un menu di primo livello e le voci dei relativi sottomenu in una posizione a discesa  
  
1.  Fare clic sul menu da spostare, premere CTRL+C o fare clic con il pulsante destro del mouse sul menu e selezionare **Copia** dal menu di scelta rapida.  
  
2.  Nel menu di primo livello di destinazione, fare clic sulla voce del sottomenu che precede la nuova posizione individuata e premere CTRL+V oppure fare clic con il pulsante destro del mouse sulla voce di sottomenu che precede la nuova posizione e selezionare **Incolla** dal menu di scelta rapida.  
  
     Il menu copiato viene inserito prima della voce di sottomenu selezionata.  
  
### <a name="to-copy-a-submenu-item-to-another-menu"></a>Per copiare una voce di sottomenu in un altro menu  
  
1.  Fare clic sulla voce di sottomenu da copiare, premere CTRL+C o fare clic con il pulsante destro del mouse sulla voce di sottomenu e selezionare **Copia** dal menu di scelta rapida.  
  
2.  Fare clic sul menu che conterrà la voce di sottomenu tagliata.  
  
3.  Fare clic sulla voce di sottomenu che precede la nuova posizione individuata e premere CTRL+V oppure fare clic con il pulsante destro del mouse sulla voce di sottomenu che precede la nuova posizione e selezionare **Incolla** dal menu di scelta rapida.  
  
     La voce di sottomenu copiata viene inserita prima della voce di sottomenu selezionata.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Panoramica sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)
