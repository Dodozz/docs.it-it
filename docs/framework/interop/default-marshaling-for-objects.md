---
title: Marshalling predefinito per gli oggetti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84a3ea24120a9548c9d1cd2b7b83997a2c849cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528020"
---
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="ad228-102">Marshalling predefinito per gli oggetti</span><span class="sxs-lookup"><span data-stu-id="ad228-102">Default Marshaling for Objects</span></span>
<span data-ttu-id="ad228-103">I parametri e i campi tipizzati come <xref:System.Object?displayProperty=nameWithType> possono essere esposti al codice non gestito come uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad228-103">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>  
  
-   <span data-ttu-id="ad228-104">Una variante quando l'oggetto è un parametro.</span><span class="sxs-lookup"><span data-stu-id="ad228-104">A variant when the object is a parameter.</span></span>  
  
-   <span data-ttu-id="ad228-105">Un'interfaccia quando l'oggetto è un campo della struttura.</span><span class="sxs-lookup"><span data-stu-id="ad228-105">An interface when the object is a structure field.</span></span>  
  
 <span data-ttu-id="ad228-106">Solo l'interoperabilità COM supporta il marshalling per i tipi di oggetto.</span><span class="sxs-lookup"><span data-stu-id="ad228-106">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="ad228-107">Il comportamento predefinito è il marshalling degli oggetti alle varianti COM.</span><span class="sxs-lookup"><span data-stu-id="ad228-107">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="ad228-108">Queste regole si applicano solo al tipo **Object** e non agli oggetti fortemente tipizzati derivanti dalla classe **Object**.</span><span class="sxs-lookup"><span data-stu-id="ad228-108">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>  
  
 <span data-ttu-id="ad228-109">Questo argomento offre le informazioni aggiuntive seguenti sul marshalling dei tipi di oggetto:</span><span class="sxs-lookup"><span data-stu-id="ad228-109">This topic provides the following additional information about marshaling object types:</span></span>  
  
-   [<span data-ttu-id="ad228-110">Opzioni di marshalling</span><span class="sxs-lookup"><span data-stu-id="ad228-110">Marshaling Options</span></span>](#cpcondefaultmarshalingforobjectsanchor7)  
  
-   [<span data-ttu-id="ad228-111">Marshalling dell'oggetto all'interfaccia</span><span class="sxs-lookup"><span data-stu-id="ad228-111">Marshaling Object to Interface</span></span>](#cpcondefaultmarshalingforobjectsanchor2)  
  
-   [<span data-ttu-id="ad228-112">Marshalling dell'oggetto alla variante</span><span class="sxs-lookup"><span data-stu-id="ad228-112">Marshaling Object to Variant</span></span>](#cpcondefaultmarshalingforobjectsanchor3)  
  
-   [<span data-ttu-id="ad228-113">Marshalling della variante all'oggetto</span><span class="sxs-lookup"><span data-stu-id="ad228-113">Marshaling Variant to Object</span></span>](#cpcondefaultmarshalingforobjectsanchor4)  
  
-   [<span data-ttu-id="ad228-114">Marshalling di varianti ByRef</span><span class="sxs-lookup"><span data-stu-id="ad228-114">Marshaling ByRef Variants</span></span>](#cpcondefaultmarshalingforobjectsanchor6)  
  
<a name="cpcondefaultmarshalingforobjectsanchor7"></a>   
## <a name="marshaling-options"></a><span data-ttu-id="ad228-115">Opzioni di marshalling</span><span class="sxs-lookup"><span data-stu-id="ad228-115">Marshaling Options</span></span>  
 <span data-ttu-id="ad228-116">La tabella seguente illustra le opzioni di marshalling per il tipo di dati **Object**.</span><span class="sxs-lookup"><span data-stu-id="ad228-116">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="ad228-117">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per effettuare il marshalling di oggetti.</span><span class="sxs-lookup"><span data-stu-id="ad228-117">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>  
  
|<span data-ttu-id="ad228-118">Tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="ad228-118">Enumeration type</span></span>|<span data-ttu-id="ad228-119">Descrizione del formato non gestito</span><span class="sxs-lookup"><span data-stu-id="ad228-119">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="ad228-120">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="ad228-120">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="ad228-121">(predefinita per i parametri)</span><span class="sxs-lookup"><span data-stu-id="ad228-121">(default for parameters)</span></span>|<span data-ttu-id="ad228-122">Una variante di tipo COM.</span><span class="sxs-lookup"><span data-stu-id="ad228-122">A COM-style variant.</span></span>|  
|<span data-ttu-id="ad228-123">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="ad228-123">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="ad228-124">Un'interfaccia **IDispatch**, se possibile; in caso contrario, un'interfaccia **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="ad228-124">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|  
|<span data-ttu-id="ad228-125">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="ad228-125">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="ad228-126">(predefinita per i campi)</span><span class="sxs-lookup"><span data-stu-id="ad228-126">(default for fields)</span></span>|<span data-ttu-id="ad228-127">Un' interfaccia **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="ad228-127">An **IUnknown** interface.</span></span>|  
|<span data-ttu-id="ad228-128">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="ad228-128">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="ad228-129">Un'interfaccia **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="ad228-129">An **IDispatch** interface.</span></span>|  
  
 <span data-ttu-id="ad228-130">L'esempio seguente illustra la definizione dell'interfaccia gestita per `MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="ad228-130">The following example shows the managed interface definition for `MarshalObject`.</span></span>  
  
```vb  
Interface MarshalObject  
   Sub SetVariant(o As Object)  
   Sub SetVariantRef(ByRef o As Object)  
   Function GetVariant() As Object  
  
   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)  
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _  
      As Object)  
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object  
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)  
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _  
      As Object)  
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object  
End Interface  
```  
  
```csharp  
interface MarshalObject {  
   void SetVariant(Object o);  
   void SetVariantRef(ref Object o);  
   Object GetVariant();  
  
   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);  
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);  
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();  
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);  
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);  
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();  
}  
```  
  
 <span data-ttu-id="ad228-131">Il codice seguente esporta l'interfaccia `MarshalObject` in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="ad228-131">The following code exports the `MarshalObject` interface to a type library.</span></span>  
  
```  
interface MarshalObject {  
   HRESULT SetVariant([in] VARIANT o);  
   HRESULT SetVariantRef([in,out] VARIANT *o);  
   HRESULT GetVariant([out,retval] VARIANT *o)   
   HRESULT SetIDispatch([in] IDispatch *o);  
   HRESULT SetIDispatchRef([in,out] IDispatch **o);  
   HRESULT GetIDispatch([out,retval] IDispatch **o)   
   HRESULT SetIUnknown([in] IUnknown *o);  
   HRESULT SetIUnknownRef([in,out] IUnknown **o);  
   HRESULT GetIUnknown([out,retval] IUnknown **o)   
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="ad228-132">Il gestore di marshalling di interoperabilità libera automaticamente gli oggetti allocati nella variante dopo la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-132">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>  
  
 <span data-ttu-id="ad228-133">L'esempio seguente illustra un tipo valore formattato.</span><span class="sxs-lookup"><span data-stu-id="ad228-133">The following example shows a formatted value type.</span></span>  
  
```vb  
Public Structure ObjectHolder  
   Dim o1 As Object  
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object  
End Structure  
```  
  
```csharp  
public struct ObjectHolder {  
   Object o1;  
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;  
}  
```  
  
 <span data-ttu-id="ad228-134">Il codice seguente esporta il tipo formattato in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="ad228-134">The following code exports the formatted type to a type library.</span></span>  
  
```  
struct ObjectHolder {  
   VARIANT o1;  
   IDispatch *o2;  
}  
```  
  
<a name="cpcondefaultmarshalingforobjectsanchor2"></a>   
## <a name="marshaling-object-to-interface"></a><span data-ttu-id="ad228-135">Marshalling dell'oggetto all'interfaccia</span><span class="sxs-lookup"><span data-stu-id="ad228-135">Marshaling Object to Interface</span></span>  
 <span data-ttu-id="ad228-136">Quando un oggetto viene esposto a COM come interfaccia, tale interfaccia è l'interfaccia di classe del tipo gestito <xref:System.Object> (interfaccia **_Object**).</span><span class="sxs-lookup"><span data-stu-id="ad228-136">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="ad228-137">Questa interfaccia viene tipizzata come **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) o **IUnknown** (**UnmanagedType.IUnknown**) nella libreria dei tipi risultante.</span><span class="sxs-lookup"><span data-stu-id="ad228-137">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="ad228-138">I client COM possono richiamare in modo dinamico i membri della classe gestita o eventuali membri implementati dalle classi derivate tramite l'interfaccia **_Object**.</span><span class="sxs-lookup"><span data-stu-id="ad228-138">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="ad228-139">Il client può anche chiamare **QueryInterface** per ottenere le altre interfacce implementate in modo esplicito dal tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="ad228-139">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor3"></a>   
## <a name="marshaling-object-to-variant"></a><span data-ttu-id="ad228-140">Marshalling dell'oggetto alla variante</span><span class="sxs-lookup"><span data-stu-id="ad228-140">Marshaling Object to Variant</span></span>  
 <span data-ttu-id="ad228-141">Quando viene effettuato il marshalling di un oggetto a una variante, il tipo di variante interno viene determinato in fase di esecuzione, in base alle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad228-141">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>  
  
-   <span data-ttu-id="ad228-142">Se il riferimento all'oggetto è null (**Nothing** in Visual Basic), viene effettuato il marshalling dell'oggetto a una variante di tipo **VT_EMPTY**.</span><span class="sxs-lookup"><span data-stu-id="ad228-142">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>  
  
-   <span data-ttu-id="ad228-143">Se l'oggetto è un'istanza di un tipo elencato nella tabella seguente, il tipo di variante risultante viene determinato dalle regole incluse nel gestore di marshalling e visualizzate nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ad228-143">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>  
  
-   <span data-ttu-id="ad228-144">Gli altri oggetti che devono controllare in modo esplicito il comportamento di marshalling possono implementare l'interfaccia <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="ad228-144">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="ad228-145">In tal caso, il tipo di variante viene determinato dal codice del tipo restituito dal metodo <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad228-145">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ad228-146">In caso contrario, viene effettuato il marshalling dell'oggetto come variante di tipo **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="ad228-146">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>  
  
### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="ad228-147">Marshalling di tipi di sistema alla variante</span><span class="sxs-lookup"><span data-stu-id="ad228-147">Marshaling System Types to Variant</span></span>  
 <span data-ttu-id="ad228-148">La tabella seguente illustra i tipi di oggetto gestito e i corrispondenti tipi di varianti COM.</span><span class="sxs-lookup"><span data-stu-id="ad228-148">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="ad228-149">Questi tipi vengono convertiti solo quando la firma del metodo chiamato è di tipo <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad228-149">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
|<span data-ttu-id="ad228-150">Tipo di oggetto</span><span class="sxs-lookup"><span data-stu-id="ad228-150">Object type</span></span>|<span data-ttu-id="ad228-151">Tipo di variante COM</span><span class="sxs-lookup"><span data-stu-id="ad228-151">COM variant type</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="ad228-152">Riferimento all'oggetto null (**Nothing** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="ad228-152">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="ad228-153">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="ad228-153">**VT_EMPTY**</span></span>|  
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="ad228-154">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="ad228-154">**VT_NULL**</span></span>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="ad228-155">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="ad228-155">**VT_ERROR**</span></span>|  
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="ad228-156">**VT_ERROR** con **E_PARAMNOTFOUND**</span><span class="sxs-lookup"><span data-stu-id="ad228-156">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="ad228-157">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="ad228-157">**VT_DISPATCH**</span></span>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="ad228-158">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="ad228-158">**VT_UNKNOWN**</span></span>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="ad228-159">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="ad228-159">**VT_CY**</span></span>|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="ad228-160">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="ad228-160">**VT_BOOL**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="ad228-161">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="ad228-161">**VT_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="ad228-162">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="ad228-162">**VT_UI1**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="ad228-163">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="ad228-163">**VT_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="ad228-164">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="ad228-164">**VT_UI2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="ad228-165">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="ad228-165">**VT_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="ad228-166">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="ad228-166">**VT_UI4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="ad228-167">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="ad228-167">**VT_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="ad228-168">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="ad228-168">**VT_UI8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="ad228-169">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="ad228-169">**VT_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="ad228-170">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="ad228-170">**VT_R8**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="ad228-171">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="ad228-171">**VT_DECIMAL**</span></span>|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="ad228-172">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="ad228-172">**VT_DATE**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="ad228-173">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="ad228-173">**VT_BSTR**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="ad228-174">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="ad228-174">**VT_INT**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="ad228-175">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="ad228-175">**VT_UINT**</span></span>|  
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="ad228-176">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="ad228-176">**VT_ARRAY**</span></span>|  
  
 <span data-ttu-id="ad228-177">Usando l'interfaccia `MarshalObject` definita nell'esempio precedente, l'esempio di codice seguente illustra come passare diversi tipi di varianti a un server COM.</span><span class="sxs-lookup"><span data-stu-id="ad228-177">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>  
  
```vb  
Dim mo As New MarshalObject()  
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.  
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.  
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.  
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.  
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.  
```  
  
```csharp  
MarshalObject mo = new MarshalObject();  
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.  
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.  
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.  
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.  
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.  
```  
  
 <span data-ttu-id="ad228-178">È possibile effettuare il marshalling dei tipi COM privi di tipi gestiti corrispondenti usando classi wrapper, ad esempio <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper> e <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span><span class="sxs-lookup"><span data-stu-id="ad228-178">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="ad228-179">L'esempio di codice seguente illustra come usare questi wrapper per passare diversi tipi di varianti a un server COM.</span><span class="sxs-lookup"><span data-stu-id="ad228-179">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
' Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(New UnknownWrapper(inew))  
' Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(New DispatchWrapper(inew))  
' Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(New ErrorWrapper(&H80054002))  
' Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))  
```  
  
```csharp  
using System.Runtime.InteropServices;  
// Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(new UnknownWrapper(inew));  
// Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(new DispatchWrapper(inew));  
// Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(new ErrorWrapper(0x80054002));  
// Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));  
```  
  
 <span data-ttu-id="ad228-180">Le classi wrapper vengono definite nello spazio dei nomi <xref:System.Runtime.InteropServices>.</span><span class="sxs-lookup"><span data-stu-id="ad228-180">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="ad228-181">Marshalling dell'interfaccia IConvertible alla variante</span><span class="sxs-lookup"><span data-stu-id="ad228-181">Marshaling the IConvertible Interface to Variant</span></span>  
 <span data-ttu-id="ad228-182">I tipi diversi da quelli elencati nella sezione precedente possono controllare come viene effettuato il marshalling implementando l'interfaccia <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="ad228-182">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="ad228-183">Se l'oggetto implementa l'interfaccia **IConvertible**, il tipo di variante COM viene determinato in fase di esecuzione dal valore dell'enumerazione <xref:System.TypeCode> restituita dal metodo <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad228-183">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="ad228-184">La tabella seguente illustra i possibili valori per l'enumerazione **TypeCode** e il tipo di variante COM corrispondente per ogni valore.</span><span class="sxs-lookup"><span data-stu-id="ad228-184">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>  
  
|<span data-ttu-id="ad228-185">TypeCode</span><span class="sxs-lookup"><span data-stu-id="ad228-185">TypeCode</span></span>|<span data-ttu-id="ad228-186">Tipo di variante COM</span><span class="sxs-lookup"><span data-stu-id="ad228-186">COM variant type</span></span>|  
|--------------|----------------------|  
|<span data-ttu-id="ad228-187">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="ad228-187">**TypeCode.Empty**</span></span>|<span data-ttu-id="ad228-188">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="ad228-188">**VT_EMPTY**</span></span>|  
|<span data-ttu-id="ad228-189">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="ad228-189">**TypeCode.Object**</span></span>|<span data-ttu-id="ad228-190">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="ad228-190">**VT_UNKNOWN**</span></span>|  
|<span data-ttu-id="ad228-191">**TypeCode.DBNull**</span><span class="sxs-lookup"><span data-stu-id="ad228-191">**TypeCode.DBNull**</span></span>|<span data-ttu-id="ad228-192">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="ad228-192">**VT_NULL**</span></span>|  
|<span data-ttu-id="ad228-193">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="ad228-193">**TypeCode.Boolean**</span></span>|<span data-ttu-id="ad228-194">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="ad228-194">**VT_BOOL**</span></span>|  
|<span data-ttu-id="ad228-195">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="ad228-195">**TypeCode.Char**</span></span>|<span data-ttu-id="ad228-196">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="ad228-196">**VT_UI2**</span></span>|  
|<span data-ttu-id="ad228-197">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="ad228-197">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="ad228-198">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="ad228-198">**VT_I1**</span></span>|  
|<span data-ttu-id="ad228-199">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="ad228-199">**TypeCode.Byte**</span></span>|<span data-ttu-id="ad228-200">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="ad228-200">**VT_UI1**</span></span>|  
|<span data-ttu-id="ad228-201">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="ad228-201">**TypeCode.Int16**</span></span>|<span data-ttu-id="ad228-202">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="ad228-202">**VT_I2**</span></span>|  
|<span data-ttu-id="ad228-203">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="ad228-203">**TypeCode.UInt16**</span></span>|<span data-ttu-id="ad228-204">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="ad228-204">**VT_UI2**</span></span>|  
|<span data-ttu-id="ad228-205">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="ad228-205">**TypeCode.Int32**</span></span>|<span data-ttu-id="ad228-206">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="ad228-206">**VT_I4**</span></span>|  
|<span data-ttu-id="ad228-207">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="ad228-207">**TypeCode.UInt32**</span></span>|<span data-ttu-id="ad228-208">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="ad228-208">**VT_UI4**</span></span>|  
|<span data-ttu-id="ad228-209">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="ad228-209">**TypeCode.Int64**</span></span>|<span data-ttu-id="ad228-210">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="ad228-210">**VT_I8**</span></span>|  
|<span data-ttu-id="ad228-211">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="ad228-211">**TypeCode.UInt64**</span></span>|<span data-ttu-id="ad228-212">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="ad228-212">**VT_UI8**</span></span>|  
|<span data-ttu-id="ad228-213">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="ad228-213">**TypeCode.Single**</span></span>|<span data-ttu-id="ad228-214">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="ad228-214">**VT_R4**</span></span>|  
|<span data-ttu-id="ad228-215">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="ad228-215">**TypeCode.Double**</span></span>|<span data-ttu-id="ad228-216">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="ad228-216">**VT_R8**</span></span>|  
|<span data-ttu-id="ad228-217">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="ad228-217">**TypeCode.Decimal**</span></span>|<span data-ttu-id="ad228-218">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="ad228-218">**VT_DECIMAL**</span></span>|  
|<span data-ttu-id="ad228-219">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="ad228-219">**TypeCode.DateTime**</span></span>|<span data-ttu-id="ad228-220">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="ad228-220">**VT_DATE**</span></span>|  
|<span data-ttu-id="ad228-221">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="ad228-221">**TypeCode.String**</span></span>|<span data-ttu-id="ad228-222">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="ad228-222">**VT_BSTR**</span></span>|  
|<span data-ttu-id="ad228-223">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="ad228-223">Not supported.</span></span>|<span data-ttu-id="ad228-224">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="ad228-224">**VT_INT**</span></span>|  
|<span data-ttu-id="ad228-225">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="ad228-225">Not supported.</span></span>|<span data-ttu-id="ad228-226">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="ad228-226">**VT_UINT**</span></span>|  
|<span data-ttu-id="ad228-227">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="ad228-227">Not supported.</span></span>|<span data-ttu-id="ad228-228">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="ad228-228">**VT_ARRAY**</span></span>|  
|<span data-ttu-id="ad228-229">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="ad228-229">Not supported.</span></span>|<span data-ttu-id="ad228-230">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="ad228-230">**VT_RECORD**</span></span>|  
|<span data-ttu-id="ad228-231">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="ad228-231">Not supported.</span></span>|<span data-ttu-id="ad228-232">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="ad228-232">**VT_CY**</span></span>|  
|<span data-ttu-id="ad228-233">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="ad228-233">Not supported.</span></span>|<span data-ttu-id="ad228-234">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="ad228-234">**VT_VARIANT**</span></span>|  
  
 <span data-ttu-id="ad228-235">Il valore della variante COM viene determinato chiamando l'interfaccia **IConvertible.To** *Type*, dove **To** *Type* è la routine di conversione che corrisponde al tipo restituito da **IConvertible.GetTypeCode**.</span><span class="sxs-lookup"><span data-stu-id="ad228-235">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="ad228-236">Ad esempio, il marshalling di un oggetto che restituisce **TypeCode.Double** da **IConvertible.GetTypeCode** viene effettuato come variante COM di tipo **VT_R8**.</span><span class="sxs-lookup"><span data-stu-id="ad228-236">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="ad228-237">Per ottenere il valore della variante (archiviata nel campo **dblVal** della variante COM), è possibile eseguire il cast all'interfaccia **IConvertible** e chiamare il metodo <xref:System.IConvertible.ToDouble%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad228-237">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor4"></a>   
## <a name="marshaling-variant-to-object"></a><span data-ttu-id="ad228-238">Marshalling della variante all'oggetto</span><span class="sxs-lookup"><span data-stu-id="ad228-238">Marshaling Variant to Object</span></span>  
 <span data-ttu-id="ad228-239">Quando si effettua il marshalling di una variante a un oggetto, il tipo e a volte il valore della variante di cui viene effettuato il marshalling determinano il tipo dell'oggetto prodotto.</span><span class="sxs-lookup"><span data-stu-id="ad228-239">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="ad228-240">La tabella seguente identifica tale tipo di variante e il tipo di oggetto corrispondente creato dal gestore di marshalling quando una variante viene passata da COM a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad228-240">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>  
  
|<span data-ttu-id="ad228-241">Tipo di variante COM</span><span class="sxs-lookup"><span data-stu-id="ad228-241">COM variant type</span></span>|<span data-ttu-id="ad228-242">Tipo di oggetto</span><span class="sxs-lookup"><span data-stu-id="ad228-242">Object type</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="ad228-243">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="ad228-243">**VT_EMPTY**</span></span>|<span data-ttu-id="ad228-244">Riferimento all'oggetto null (**Nothing** in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="ad228-244">Null object reference (**Nothing** in Visual Basic).</span></span>|  
|<span data-ttu-id="ad228-245">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="ad228-245">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-246">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="ad228-246">**VT_DISPATCH**</span></span>|<span data-ttu-id="ad228-247">**System.__ComObject** o null se (pdispVal == null)</span><span class="sxs-lookup"><span data-stu-id="ad228-247">**System.__ComObject** or null if (pdispVal == null)</span></span>|  
|<span data-ttu-id="ad228-248">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="ad228-248">**VT_UNKNOWN**</span></span>|<span data-ttu-id="ad228-249">**System.__ComObject** o null se (punkVal == null)</span><span class="sxs-lookup"><span data-stu-id="ad228-249">**System.__ComObject** or null if (punkVal == null)</span></span>|  
|<span data-ttu-id="ad228-250">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="ad228-250">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-251">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="ad228-251">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-252">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="ad228-252">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-253">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="ad228-253">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-254">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="ad228-254">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-255">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="ad228-255">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-256">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="ad228-256">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-257">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="ad228-257">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-258">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="ad228-258">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-259">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="ad228-259">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-260">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="ad228-260">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-261">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="ad228-261">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-262">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="ad228-262">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-263">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="ad228-263">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-264">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="ad228-264">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-265">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="ad228-265">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-266">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="ad228-266">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-267">**VT_ARRAY** &#124; **VT_**\*</span><span class="sxs-lookup"><span data-stu-id="ad228-267">**VT_ARRAY** &#124; **VT_**\*</span></span>|<xref:System.Array?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-268">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="ad228-268">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="ad228-269">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="ad228-269">**VT_RECORD**</span></span>|<span data-ttu-id="ad228-270">Tipo valore boxed corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ad228-270">Corresponding boxed value type.</span></span>|  
|<span data-ttu-id="ad228-271">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="ad228-271">**VT_VARIANT**</span></span>|<span data-ttu-id="ad228-272">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="ad228-272">Not supported.</span></span>|  
  
 <span data-ttu-id="ad228-273">I tipi di variante passati da COM al codice gestito e quindi di nuovo a COM potrebbero non conservare lo stesso tipo di variante per tutta la durata della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-273">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="ad228-274">Si consideri che cosa accade quando una variante di tipo **VT_DISPATCH** viene passata da COM a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ad228-274">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="ad228-275">Durante il marshalling, la variante viene convertita in <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ad228-275">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ad228-276">Se **Object** viene quindi passato nuovamente a COM, ne viene effettuato il marshalling a una variante di tipo **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="ad228-276">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="ad228-277">Non esiste garanzia che la variante prodotta quando viene effettuato il marshalling di un oggetto dal codice gestito a COM sarà dello stesso tipo della variante usata inizialmente per produrre l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ad228-277">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor6"></a>   
## <a name="marshaling-byref-variants"></a><span data-ttu-id="ad228-278">Marshalling di varianti ByRef</span><span class="sxs-lookup"><span data-stu-id="ad228-278">Marshaling ByRef Variants</span></span>  
 <span data-ttu-id="ad228-279">Anche se le varianti in sé possono essere passate in base al valore o al riferimento, è anche possibile usare il flag **VT_BYREF** con qualsiasi variante per indicare che i contenuti della variante verranno passati in base al riferimento invece che al valore.</span><span class="sxs-lookup"><span data-stu-id="ad228-279">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="ad228-280">La differenza tra il marshalling delle varianti in base al riferimento e il marshalling di una variante con il flag **VT_BYREF** impostato può risultare poco chiara.</span><span class="sxs-lookup"><span data-stu-id="ad228-280">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="ad228-281">La figura seguente illustra le differenze.</span><span class="sxs-lookup"><span data-stu-id="ad228-281">The following illustration clarifies the differences.</span></span>  
  
 <span data-ttu-id="ad228-282">![Variante passata allo stack](./media/interopvariant.gif "Variante di interoperabilità")</span><span class="sxs-lookup"><span data-stu-id="ad228-282">![Variant passed on the stack](./media/interopvariant.gif "interopvariant")</span></span>  
<span data-ttu-id="ad228-283">Varianti passate per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="ad228-283">Variants passed by value and by reference</span></span>  
  
 <span data-ttu-id="ad228-284">**Comportamento predefinito per il marshalling di oggetti e varianti per valore**</span><span class="sxs-lookup"><span data-stu-id="ad228-284">**Default behavior for marshaling objects and variants by value**</span></span>  
  
-   <span data-ttu-id="ad228-285">Quando si passano gli oggetti dal codice gestito a COM, i contenuti dell'oggetto vengono copiati in una nuova variante creata dal gestore di marshalling, usando le regole definite in [Marshalling dell'oggetto alla variante](#cpcondefaultmarshalingforobjectsanchor3).</span><span class="sxs-lookup"><span data-stu-id="ad228-285">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#cpcondefaultmarshalingforobjectsanchor3).</span></span> <span data-ttu-id="ad228-286">Le modifiche apportate alla variante sul lato non gestito non vengono propagate all'oggetto originale al ritorno dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-286">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>  
  
-   <span data-ttu-id="ad228-287">Quando si passano le varianti da COM al codice gestito, i contenuti della variante vengono copiati in un nuovo oggetto creato, usando le regole definite in [Marshalling della variante all'oggetto](#cpcondefaultmarshalingforobjectsanchor4).</span><span class="sxs-lookup"><span data-stu-id="ad228-287">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#cpcondefaultmarshalingforobjectsanchor4).</span></span> <span data-ttu-id="ad228-288">Le modifiche apportate all'oggetto sul lato gestito non vengono propagate alla variante originale al ritorno dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-288">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>  
  
 <span data-ttu-id="ad228-289">**Comportamento predefinito per il marshalling di oggetti e varianti per riferimento**</span><span class="sxs-lookup"><span data-stu-id="ad228-289">**Default behavior for marshaling objects and variants by reference**</span></span>  
  
 <span data-ttu-id="ad228-290">Per propagare le modifiche al chiamante, i parametri devono essere passati per riferimento.</span><span class="sxs-lookup"><span data-stu-id="ad228-290">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="ad228-291">È ad esempio possibile usare la parola chiave **ref** in C# (o **ByRef** nel codice gestito di Visual Basic) per passare i parametri per riferimento.</span><span class="sxs-lookup"><span data-stu-id="ad228-291">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="ad228-292">In COM i parametri per riferimento vengono passati usando un puntatore, ad esempio una **variante \***.</span><span class="sxs-lookup"><span data-stu-id="ad228-292">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>  
  
-   <span data-ttu-id="ad228-293">Quando si passa un oggetto a COM per riferimento, il gestore di marshalling crea una nuova variante e copia i contenuti del riferimento all'oggetto nella variante prima che venga effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-293">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="ad228-294">La variante viene passata alla funzione non gestita in cui l'utente può modificare i contenuti della variante.</span><span class="sxs-lookup"><span data-stu-id="ad228-294">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="ad228-295">Al ritorno dalla chiamata, le modifiche apportate alla variante sul lato non gestito vengono propagate all'oggetto originale.</span><span class="sxs-lookup"><span data-stu-id="ad228-295">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="ad228-296">Se il tipo della variante è diverso dal tipo della variante passata alla chiamata, le modifiche vengono propagate a un oggetto di tipo diverso,</span><span class="sxs-lookup"><span data-stu-id="ad228-296">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="ad228-297">ovvero il tipo dell'oggetto passato nella chiamata può essere diverso dal tipo dell'oggetto restituito dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-297">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>  
  
-   <span data-ttu-id="ad228-298">Quando si passa una variante al codice gestito per riferimento, il gestore di marshalling crea un nuovo oggetto e copia i contenuti della variante nell'oggetto prima di effettuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-298">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="ad228-299">Un riferimento all'oggetto viene passato alla funzione non gestita, in cui l'utente può modificare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ad228-299">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="ad228-300">Al ritorno dalla chiamata, le modifiche apportate all'oggetto di riferimento vengono propagate alla variante originale.</span><span class="sxs-lookup"><span data-stu-id="ad228-300">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="ad228-301">Se il tipo dell'oggetto è diverso dal tipo dell'oggetto passato alla chiamata, il tipo della variante originale viene modificato e il valore viene propagato nella variante.</span><span class="sxs-lookup"><span data-stu-id="ad228-301">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="ad228-302">Anche in questo caso il tipo della variante passata nella chiamata può essere diverso dal tipo della variante restituita dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-302">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>  
  
 <span data-ttu-id="ad228-303">**Comportamento predefinito per il marshalling di una variante con il flag VT_BYREF impostato**</span><span class="sxs-lookup"><span data-stu-id="ad228-303">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>  
  
-   <span data-ttu-id="ad228-304">Una variante che viene passata al codice gestito per valore può avere il flag **VT_BYREF** impostato per indicare che la variante contiene un riferimento invece che un valore.</span><span class="sxs-lookup"><span data-stu-id="ad228-304">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="ad228-305">In questo caso, viene ancora effettuato il marshalling della variante a un oggetto perché la variante verrà passata per valore.</span><span class="sxs-lookup"><span data-stu-id="ad228-305">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="ad228-306">Il gestore di marshalling dereferenzia automaticamente i contenuti della variante e la copia in un nuovo oggetto creato prima di eseguire la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-306">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="ad228-307">L'oggetto viene quindi passato nella funzione gestita, tuttavia, al ritorno dalla chiamata, l'oggetto non viene propagato nella variante originale.</span><span class="sxs-lookup"><span data-stu-id="ad228-307">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="ad228-308">Le modifiche apportate all'oggetto gestito vengono perse.</span><span class="sxs-lookup"><span data-stu-id="ad228-308">Changes made to the managed object are lost.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="ad228-309">Non è possibile modificare il valore di una variante passata per valore, anche se la variante ha il flag **VT_BYREF** impostato.</span><span class="sxs-lookup"><span data-stu-id="ad228-309">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>  
  
-   <span data-ttu-id="ad228-310">Una variante che viene passata al codice gestito per riferimento può anche avere il flag **VT_BYREF** impostato per indicare che la variante contiene un altro riferimento.</span><span class="sxs-lookup"><span data-stu-id="ad228-310">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="ad228-311">In questo caso, viene effettuato il marshalling della variante a un oggetto **ref** perché la variante verrà passata per riferimento.</span><span class="sxs-lookup"><span data-stu-id="ad228-311">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="ad228-312">Il gestore di marshalling dereferenzia automaticamente i contenuti della variante e la copia in un nuovo oggetto creato prima di eseguire la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad228-312">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="ad228-313">Al ritorno dalla chiamata, il valore dell'oggetto viene propagato al riferimento nella variante originale solo se l'oggetto è dello stesso tipo dell'oggetto passato,</span><span class="sxs-lookup"><span data-stu-id="ad228-313">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="ad228-314">ovvero la propagazione non modifica il tipo di una variante con il flag **VT_BYREF** impostato.</span><span class="sxs-lookup"><span data-stu-id="ad228-314">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="ad228-315">Se il tipo dell'oggetto viene modificato durante la chiamata, al ritorno dalla chiamata viene generata un'eccezione <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="ad228-315">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>  
  
 <span data-ttu-id="ad228-316">La tabella seguente riepiloga le regole di propagazione per varianti e oggetti.</span><span class="sxs-lookup"><span data-stu-id="ad228-316">The following table summarizes the propagation rules for variants and objects.</span></span>  
  
|<span data-ttu-id="ad228-317">Da</span><span class="sxs-lookup"><span data-stu-id="ad228-317">From</span></span>|<span data-ttu-id="ad228-318">A</span><span class="sxs-lookup"><span data-stu-id="ad228-318">To</span></span>|<span data-ttu-id="ad228-319">Modifiche propagate</span><span class="sxs-lookup"><span data-stu-id="ad228-319">Changes propagated back</span></span>|  
|----------|--------|-----------------------------|  
|<span data-ttu-id="ad228-320">**Variante**  *v*</span><span class="sxs-lookup"><span data-stu-id="ad228-320">**Variant**  *v*</span></span>|<span data-ttu-id="ad228-321">**Oggetto**  *o*</span><span class="sxs-lookup"><span data-stu-id="ad228-321">**Object**  *o*</span></span>|<span data-ttu-id="ad228-322">Never</span><span class="sxs-lookup"><span data-stu-id="ad228-322">Never</span></span>|  
|<span data-ttu-id="ad228-323">**Oggetto**  *o*</span><span class="sxs-lookup"><span data-stu-id="ad228-323">**Object**  *o*</span></span>|<span data-ttu-id="ad228-324">**Variante**  *v*</span><span class="sxs-lookup"><span data-stu-id="ad228-324">**Variant**  *v*</span></span>|<span data-ttu-id="ad228-325">Never</span><span class="sxs-lookup"><span data-stu-id="ad228-325">Never</span></span>|  
|<span data-ttu-id="ad228-326">**Variante**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="ad228-326">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="ad228-327">**Oggetto ref**  *o*</span><span class="sxs-lookup"><span data-stu-id="ad228-327">**Ref Object**  *o*</span></span>|<span data-ttu-id="ad228-328">Sempre</span><span class="sxs-lookup"><span data-stu-id="ad228-328">Always</span></span>|  
|<span data-ttu-id="ad228-329">**Oggetto ref**  *o*</span><span class="sxs-lookup"><span data-stu-id="ad228-329">**Ref object**  *o*</span></span>|<span data-ttu-id="ad228-330">**Variante**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="ad228-330">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="ad228-331">Sempre</span><span class="sxs-lookup"><span data-stu-id="ad228-331">Always</span></span>|  
|<span data-ttu-id="ad228-332">**Variante**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span><span class="sxs-lookup"><span data-stu-id="ad228-332">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="ad228-333">**Oggetto**  *o*</span><span class="sxs-lookup"><span data-stu-id="ad228-333">**Object**  *o*</span></span>|<span data-ttu-id="ad228-334">Never</span><span class="sxs-lookup"><span data-stu-id="ad228-334">Never</span></span>|  
|<span data-ttu-id="ad228-335">**Variante**  *v* **(VT_BYREF** *&#124;* **VT_)**</span><span class="sxs-lookup"><span data-stu-id="ad228-335">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="ad228-336">**Oggetto ref**  *o*</span><span class="sxs-lookup"><span data-stu-id="ad228-336">**Ref Object**  *o*</span></span>|<span data-ttu-id="ad228-337">Solo se il tipo non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="ad228-337">Only if the type has not changed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad228-338">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad228-338">See also</span></span>
- [<span data-ttu-id="ad228-339">Comportamento di marshalling predefinito</span><span class="sxs-lookup"><span data-stu-id="ad228-339">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="ad228-340">Tipi copiabili e non copiabili</span><span class="sxs-lookup"><span data-stu-id="ad228-340">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="ad228-341">[Attributi direzionali](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ad228-341">[Directional Attributes](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span></span>
- [<span data-ttu-id="ad228-342">Copia e blocco</span><span class="sxs-lookup"><span data-stu-id="ad228-342">Copying and Pinning</span></span>](copying-and-pinning.md)
