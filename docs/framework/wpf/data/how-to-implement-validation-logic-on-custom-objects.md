---
title: 'Procedura: Implementare la logica di convalida negli oggetti personalizzati'
ms.date: 08/02/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: e2b77ef65c92ae596c5620c9122dcf3db0bf9462
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525989"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="b3c66-102">Procedura: Implementare la logica di convalida negli oggetti personalizzati</span><span class="sxs-lookup"><span data-stu-id="b3c66-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="b3c66-103">In questo esempio viene illustrato come implementare la logica di convalida in un oggetto personalizzato e quindi eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="b3c66-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3c66-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3c66-104">Example</span></span>  
 <span data-ttu-id="b3c66-105">È possibile fornire la logica di convalida a livello aziendale, se l'oggetto di origine implementa <xref:System.ComponentModel.IDataErrorInfo>, come illustrato nell'esempio seguente, che definisce un `Person` oggetto che implementa <xref:System.ComponentModel.IDataErrorInfo>:</span><span class="sxs-lookup"><span data-stu-id="b3c66-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="b3c66-106">Nell'esempio seguente associa la proprietà text della casella di testo per il `Person.Age` proprietà, che è stato reso disponibile per l'associazione tramite una dichiarazione della risorsa cui viene assegnata il `x:Key` `data`.</span><span class="sxs-lookup"><span data-stu-id="b3c66-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="b3c66-107">Il <xref:System.Windows.Controls.DataErrorValidationRule> verifica la presenza di errori di convalida generati dal <xref:System.ComponentModel.IDataErrorInfo> implementazione.</span><span class="sxs-lookup"><span data-stu-id="b3c66-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="b3c66-108">In alternativa, invece di usare la <xref:System.Windows.Controls.DataErrorValidationRule>, è possibile impostare il <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="b3c66-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c66-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3c66-109">See also</span></span>
- <xref:System.Windows.Controls.ExceptionValidationRule>
- [<span data-ttu-id="b3c66-110">Implementare la convalida dell'associazione</span><span class="sxs-lookup"><span data-stu-id="b3c66-110">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)
- [<span data-ttu-id="b3c66-111">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b3c66-111">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
