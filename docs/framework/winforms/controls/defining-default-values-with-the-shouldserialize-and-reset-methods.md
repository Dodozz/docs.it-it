---
title: Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: f1f5a668c5d4f52ef7dd9f60a31c04f2173165f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090615"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="34596-102">Definizione dei valori predefiniti utilizzando i metodi ShouldSerialize e Reset</span><span class="sxs-lookup"><span data-stu-id="34596-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="34596-103">`ShouldSerialize` e `Reset` sono metodi facoltativi che è possibile specificare per una proprietà, se la proprietà non presenta un valore predefinito semplice.</span><span class="sxs-lookup"><span data-stu-id="34596-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="34596-104">Se la proprietà ha un valore predefinito semplice, è consigliabile applicare il <xref:System.ComponentModel.DefaultValueAttribute> e fornire invece il valore predefinito per il costruttore di classe di attributo.</span><span class="sxs-lookup"><span data-stu-id="34596-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="34596-105">Uno di questi meccanismi Abilita le funzionalità seguenti nella finestra di progettazione:</span><span class="sxs-lookup"><span data-stu-id="34596-105">Either of these mechanisms enables the following features in the designer:</span></span>  
  
-   <span data-ttu-id="34596-106">La proprietà fornisce un'indicazione visiva nel Visualizzatore proprietà se è stato modificato rispetto al valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="34596-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>  
  
-   <span data-ttu-id="34596-107">L'utente può fare doppio clic sulla proprietà e scegliere **reimpostare** per ripristinare la proprietà sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="34596-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>  
  
-   <span data-ttu-id="34596-108">La finestra di progettazione genera codice più efficiente.</span><span class="sxs-lookup"><span data-stu-id="34596-108">The designer generates more efficient code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="34596-109">Entrambi si applicano i <xref:System.ComponentModel.DefaultValueAttribute> o fornire `Reset` *PropertyName* e `ShouldSerialize` *PropertyName* metodi.</span><span class="sxs-lookup"><span data-stu-id="34596-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="34596-110">Non utilizzare entrambi.</span><span class="sxs-lookup"><span data-stu-id="34596-110">Do not use both.</span></span>  
  
 <span data-ttu-id="34596-111">Il `Reset` *NomeProprietà* metodo imposta una proprietà sul valore predefinito, come illustrato nel frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="34596-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>  
  
```vb  
Public Sub ResetMyFont()  
   MyFont = Nothing  
End Sub  
```  
  
```csharp  
public void ResetMyFont() {  
   MyFont = null;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="34596-112">Se una proprietà non ha un `Reset` metodo, non è contrassegnato con un <xref:System.ComponentModel.DefaultValueAttribute>e non dispone di un valore predefinito fornito nella relativa dichiarazione, il `Reset` opzione per tale proprietà è disabilitata nel menu di scelta rapida del **proprietà** finestra di progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="34596-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>  
  
 <span data-ttu-id="34596-113">Finestre di progettazione, ad esempio Visual Studio usare il `ShouldSerialize` *NomeProprietà* metodo per verificare se una proprietà è stata modificata rispetto al valore predefinito e per scrivere codice nel form solo in una proprietà viene modificato, consentendo in tal modo per il codice più efficiente generazione.</span><span class="sxs-lookup"><span data-stu-id="34596-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="34596-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="34596-114">For example:</span></span>  
  
```vb  
'Returns true if the font has changed; otherwise, returns false.  
' The designer writes code to the form only if true is returned.  
Public Function ShouldSerializeMyFont() As Boolean  
   Return Not (thefont Is Nothing)  
End Function  
```  
  
```csharp  
// Returns true if the font has changed; otherwise, returns false.  
// The designer writes code to the form only if true is returned.  
public bool ShouldSerializeMyFont() {  
   return thefont != null;  
}  
```  
  
 <span data-ttu-id="34596-115">Segue un esempio di codice completo.</span><span class="sxs-lookup"><span data-stu-id="34596-115">A complete code example follows.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class MyControl  
   Inherits Control  
  
   ' Declare an instance of the Font class  
   ' and set its default value to Nothing.  
   Private thefont As Font = Nothing  
  
   ' The MyFont property.   
   Public Property MyFont() As Font  
      ' Note that the Font property never  
      ' returns null.  
      Get  
         If Not (thefont Is Nothing) Then  
            Return thefont  
         End If  
         If Not (Parent Is Nothing) Then  
            Return Parent.Font  
         End If  
         Return Control.DefaultFont  
      End Get  
      Set  
         thefont = value  
      End Set  
   End Property  
  
   Public Function ShouldSerializeMyFont() As Boolean  
      Return Not (thefont Is Nothing)  
   End Function  
  
   Public Sub ResetMyFont()  
      MyFont = Nothing  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class MyControl : Control {  
   // Declare an instance of the Font class  
   // and set its default value to null.  
   private Font thefont = null;  
  
   // The MyFont property.      
   public Font MyFont {  
      // Note that the MyFont property never  
      // returns null.  
      get {  
         if (thefont != null) return thefont;  
         if (Parent != null) return Parent.Font;  
         return Control.DefaultFont;  
      }  
      set {  
         thefont = value;  
      }  
   }  
  
   public bool ShouldSerializeMyFont() {  
      return thefont != null;  
   }  
  
   public void ResetMyFont() {  
      MyFont = null;  
   }  
}  
```  
  
 <span data-ttu-id="34596-116">In questo caso, anche quando il valore della variabile privata accessibile dal `MyFont` proprietà è `null`, il Visualizzatore proprietà non viene visualizzata `null`; in alternativa, viene visualizzato il <xref:System.Windows.Forms.Control.Font%2A> proprietà dell'elemento padre, se non è `null`, o il valore predefinito <xref:System.Windows.Forms.Control.Font%2A> valore definito <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="34596-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="34596-117">In questo modo il valore predefinito per `MyFont` non è possibile impostare semplicemente e un <xref:System.ComponentModel.DefaultValueAttribute> non può essere applicato a questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="34596-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="34596-118">Al contrario, il `ShouldSerialize` e `Reset` devono essere implementati i metodi per il `MyFont` proprietà.</span><span class="sxs-lookup"><span data-stu-id="34596-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34596-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34596-119">See also</span></span>

- [<span data-ttu-id="34596-120">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="34596-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="34596-121">Definizione di una proprietà</span><span class="sxs-lookup"><span data-stu-id="34596-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="34596-122">Eventi di modifica delle proprietà</span><span class="sxs-lookup"><span data-stu-id="34596-122">Property-Changed Events</span></span>](property-changed-events.md)
