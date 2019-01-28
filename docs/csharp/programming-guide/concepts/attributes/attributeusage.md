---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: a3a82e33d7259ec56ec3e907bc3d4d9f8a01167d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589311"
---
# <a name="attributeusage-c"></a><span data-ttu-id="97b64-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="97b64-102">AttributeUsage (C#)</span></span>

<span data-ttu-id="97b64-103">Determina come usare una classe di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="97b64-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="97b64-104"><xref:System.AttributeUsageAttribute> è un attributo che si applica alle definizioni di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="97b64-104"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="97b64-105">L'attributo `AttributeUsage` consente di controllare:</span><span class="sxs-lookup"><span data-stu-id="97b64-105">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="97b64-106">Elementi del programma a cui l'attributo può essere applicato.</span><span class="sxs-lookup"><span data-stu-id="97b64-106">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="97b64-107">Se non se ne limita l'utilizzo, un attributo può essere applicato a uno qualsiasi degli elementi del programma seguenti:</span><span class="sxs-lookup"><span data-stu-id="97b64-107">Unless you restrict its usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="97b64-108">assembly</span><span class="sxs-lookup"><span data-stu-id="97b64-108">assembly</span></span>
  - <span data-ttu-id="97b64-109">module</span><span class="sxs-lookup"><span data-stu-id="97b64-109">module</span></span>
  - <span data-ttu-id="97b64-110">campo</span><span class="sxs-lookup"><span data-stu-id="97b64-110">field</span></span>
  - <span data-ttu-id="97b64-111">event</span><span class="sxs-lookup"><span data-stu-id="97b64-111">event</span></span>
  - <span data-ttu-id="97b64-112">metodo</span><span class="sxs-lookup"><span data-stu-id="97b64-112">method</span></span>
  - <span data-ttu-id="97b64-113">param</span><span class="sxs-lookup"><span data-stu-id="97b64-113">param</span></span>
  - <span data-ttu-id="97b64-114">proprietà</span><span class="sxs-lookup"><span data-stu-id="97b64-114">property</span></span>
  - <span data-ttu-id="97b64-115">return</span><span class="sxs-lookup"><span data-stu-id="97b64-115">return</span></span>
  - <span data-ttu-id="97b64-116">tipo</span><span class="sxs-lookup"><span data-stu-id="97b64-116">type</span></span>
- <span data-ttu-id="97b64-117">Se un attributo può essere applicato più volte a un singolo elemento del programma.</span><span class="sxs-lookup"><span data-stu-id="97b64-117">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="97b64-118">Se gli attributi vengono ereditati dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="97b64-118">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="97b64-119">Le impostazioni predefinite sono simili all'esempio seguente quando vengono applicate in modo esplicito:</span><span class="sxs-lookup"><span data-stu-id="97b64-119">The default settings look like the following example when applied explicitly:</span></span>

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

<span data-ttu-id="97b64-120">In questo esempio la classe `NewAttribute` può essere applicata a qualsiasi elemento del programma supportato,</span><span class="sxs-lookup"><span data-stu-id="97b64-120">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="97b64-121">ma solo una volta a ogni entità.</span><span class="sxs-lookup"><span data-stu-id="97b64-121">But it can be applied only once to each entity.</span></span> <span data-ttu-id="97b64-122">L'attributo viene ereditato dalle classi derivate se applicato a una classe base.</span><span class="sxs-lookup"><span data-stu-id="97b64-122">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="97b64-123">Gli argomenti <xref:System.AttributeUsageAttribute.AllowMultiple> e <xref:System.AttributeUsageAttribute.Inherited> sono facoltativi, quindi il codice seguente ha lo stesso effetto:</span><span class="sxs-lookup"><span data-stu-id="97b64-123">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

<span data-ttu-id="97b64-124">Il primo argomento <xref:System.AttributeUsageAttribute> deve consistere di uno o più elementi dell'enumerazione <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="97b64-124">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="97b64-125">Più tipi di destinazione possono essere collegati con l'operatore OR, nel modo illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="97b64-125">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

<span data-ttu-id="97b64-126">A partire da C# 7.3, gli attributi possono essere applicati alla proprietà o al campo sottostante per una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="97b64-126">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="97b64-127">L'attributo si applica alla proprietà, a meno che non si specifichi l'identificatore `field` per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="97b64-127">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="97b64-128">Entrambe le situazioni sono illustrate nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="97b64-128">Both are shown in the following example:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

<span data-ttu-id="97b64-129">Se l'argomento <xref:System.AttributeUsageAttribute.AllowMultiple> è `true`, l'attributo restituito può essere applicato più volte a una singola entità, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="97b64-129">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

<span data-ttu-id="97b64-130">In questo caso, `MultiUseAttribute` può essere applicato più volte perché `AllowMultiple` è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="97b64-130">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="97b64-131">Entrambi i formati illustrati per applicare più attributi sono validi.</span><span class="sxs-lookup"><span data-stu-id="97b64-131">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="97b64-132">Se <xref:System.AttributeUsageAttribute.Inherited> è `false`, l'attributo non viene ereditato dalle classi derivate da una classe con attributi.</span><span class="sxs-lookup"><span data-stu-id="97b64-132">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="97b64-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="97b64-133">For example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

<span data-ttu-id="97b64-134">In questo caso `NonInheritedAttribute` non viene applicato a `DClass` attraverso l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="97b64-134">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="remarks"></a><span data-ttu-id="97b64-135">Note</span><span class="sxs-lookup"><span data-stu-id="97b64-135">Remarks</span></span>

<span data-ttu-id="97b64-136">L'attributo `AttributeUsage` è un attributo monouso ovvero non può essere applicato più volte alla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="97b64-136">The `AttributeUsage` attribute is a single-use attribute--it can't be applied more than once to the same class.</span></span> <span data-ttu-id="97b64-137">`AttributeUsage` è un alias per <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="97b64-137">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>

<span data-ttu-id="97b64-138">Per altre informazioni, vedere [Accesso agli attributi tramite reflection (C#)](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="97b64-138">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="example"></a><span data-ttu-id="97b64-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="97b64-139">Example</span></span>

<span data-ttu-id="97b64-140">L'esempio seguente illustra l'effetto degli argomenti <xref:System.AttributeUsageAttribute.Inherited> e <xref:System.AttributeUsageAttribute.AllowMultiple> nell'attributo <xref:System.AttributeUsageAttribute> e come gli attributi personalizzati applicati a una classe possono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="97b64-140">The following example demonstrates the effect of the <xref:System.AttributeUsageAttribute.Inherited> and <xref:System.AttributeUsageAttribute.AllowMultiple> arguments to the <xref:System.AttributeUsageAttribute> attribute, and how the custom attributes applied to a class can be enumerated.</span></span>

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a><span data-ttu-id="97b64-141">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="97b64-141">Sample Output</span></span>

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a><span data-ttu-id="97b64-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97b64-142">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="97b64-143">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="97b64-143">C# Programming Guide</span></span>](../..//index.md)
- [<span data-ttu-id="97b64-144">Attributi</span><span class="sxs-lookup"><span data-stu-id="97b64-144">Attributes</span></span>](../../../..//standard/attributes/index.md)
- [<span data-ttu-id="97b64-145">Reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="97b64-145">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="97b64-146">Attributi</span><span class="sxs-lookup"><span data-stu-id="97b64-146">Attributes</span></span>](index.md)
- [<span data-ttu-id="97b64-147">Creazione di attributi personalizzati (C#)</span><span class="sxs-lookup"><span data-stu-id="97b64-147">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)
- <span data-ttu-id="97b64-148">[Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md) (Accesso agli attributi tramite reflection (C#))</span><span class="sxs-lookup"><span data-stu-id="97b64-148">[Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md)</span></span>
