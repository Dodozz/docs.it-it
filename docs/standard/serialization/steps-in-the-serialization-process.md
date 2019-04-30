---
title: Passaggi del processo di serializzazione
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: b697e8c590d0865b26eaa9f66a333504a5faece2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954050"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="053d3-102">Passaggi del processo di serializzazione</span><span class="sxs-lookup"><span data-stu-id="053d3-102">Steps in the serialization process</span></span>
<span data-ttu-id="053d3-103">Quando viene chiamato il metodo <xref:System.Runtime.Serialization.Formatter.Serialize*> su un [formattatore](xref:System.Runtime.Serialization.Formatter), la serializzazione dell'oggetto continua secondo la sequenza di regole riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="053d3-103">When the <xref:System.Runtime.Serialization.Formatter.Serialize*> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="053d3-104">Viene effettuato un controllo per determinare se il formattatore dispone di un selettore di surrogati.</span><span class="sxs-lookup"><span data-stu-id="053d3-104">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="053d3-105">In caso affermativo, controllare se il selettore di surrogati gestisce oggetti del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="053d3-105">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="053d3-106">Se il selettore gestisce il tipo di oggetto, viene chiamato <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType> sul selettore di surrogati.</span><span class="sxs-lookup"><span data-stu-id="053d3-106">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="053d3-107">Se non è presente alcun selettore di surrogati o il tipo di oggetto non viene gestito, viene effettuato un controllo per determinare se l'oggetto è contrassegnato con l'attributo [Serializable](xref:System.SerializableAttribute).</span><span class="sxs-lookup"><span data-stu-id="053d3-107">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="053d3-108">Se l'oggetto non è contrassegnato, viene generata una <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="053d3-108">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="053d3-109">Se l'oggetto è contrassegnato in modo appropriato, controllare se l'oggetto implementa l'interfaccia <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="053d3-109">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="053d3-110">In caso affermativo, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*> viene chiamato sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="053d3-110">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*> is called on the object.</span></span>
  
- <span data-ttu-id="053d3-111">Se l'oggetto non implementa <xref:System.Runtime.Serialization.ISerializable>, vengono usati i criteri di serializzazione predefiniti, che serializzano tutti i campi non contrassegnati come [NonSerialized](xref:System.NonSerializedAttribute).</span><span class="sxs-lookup"><span data-stu-id="053d3-111">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="053d3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="053d3-112">See also</span></span>

- [<span data-ttu-id="053d3-113">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="053d3-113">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="053d3-114">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="053d3-114">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
