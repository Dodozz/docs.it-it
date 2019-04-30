---
title: Estensione del markup x:Null
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: e46d8561b62d9137d4fed4df447338a97fc0577b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938912"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="174fa-102">Estensione del markup x:Null</span><span class="sxs-lookup"><span data-stu-id="174fa-102">x:Null Markup Extension</span></span>
<span data-ttu-id="174fa-103">Specifica `null` come valore per un membro XAML.</span><span class="sxs-lookup"><span data-stu-id="174fa-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="174fa-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="174fa-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="174fa-105">Note</span><span class="sxs-lookup"><span data-stu-id="174fa-105">Remarks</span></span>  
 <span data-ttu-id="174fa-106">La parola chiave per un riferimento null in C# e [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] è null.</span><span class="sxs-lookup"><span data-stu-id="174fa-106">The keyword for a null reference in C# and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="174fa-107">La parola chiave Microsoft Visual Basic per un riferimento null viene `Nothing`, ma è sempre usare `{x:Null}` come l'utilizzo XAML indipendentemente dal linguaggio di code-behind è associare il XAML.</span><span class="sxs-lookup"><span data-stu-id="174fa-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="174fa-108">Il `x:Null` estensione di markup non contiene proprietà impostabili.</span><span class="sxs-lookup"><span data-stu-id="174fa-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="174fa-109">Un utilizzo di null è spesso associato all'esposizione del membro XAML di un tipo CLR <xref:System.Nullable%601> valore.</span><span class="sxs-lookup"><span data-stu-id="174fa-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="174fa-110">Il `x:Null` estensione di markup, come tutte le estensioni di markup XAML, Usa le parentesi graffe (`{,}`) per eseguire l'escape la gestione di valori di attributo sia diverso da valori letterali o i riferimenti del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="174fa-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="174fa-111">Sintassi dell'attributo è in genere usati con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="174fa-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="174fa-112">La sintassi degli elementi oggetto `<x:Null />` sia tecnicamente possibile, ma viene usato raramente perché il `x:Null` estensione di markup non dispone di parametri posizionali o argomenti di costruzione.</span><span class="sxs-lookup"><span data-stu-id="174fa-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="174fa-113">Per informazioni sulle estensioni di markup, vedere [estensioni di Markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="174fa-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="174fa-114">Nei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per il <xref:System.Windows.Markup.NullExtension> classe.</span><span class="sxs-lookup"><span data-stu-id="174fa-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="174fa-115">Note sull'utilizzo WPF</span><span class="sxs-lookup"><span data-stu-id="174fa-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="174fa-116">Si noti che `null` non è necessariamente il valore iniziale non impostato per una proprietà di dipendenza di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="174fa-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="174fa-117">Il valore predefinito iniziale può variare per ogni proprietà di dipendenza e può essere basato su proprietà specifiche metadati.</span><span class="sxs-lookup"><span data-stu-id="174fa-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="174fa-118">Molte proprietà di dipendenza non accettano `null` come valore, tramite markup o codice a causa delle implementazioni dei callback di convalida.</span><span class="sxs-lookup"><span data-stu-id="174fa-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="174fa-119">Per altre informazioni sulle proprietà di dipendenza, vedere [Cenni preliminari sulle proprietà di dipendenza](../wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="174fa-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174fa-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="174fa-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="174fa-121">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="174fa-121">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="174fa-122">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="174fa-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
