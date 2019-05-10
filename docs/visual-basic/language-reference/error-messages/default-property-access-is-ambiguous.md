---
title: L'accesso a una proprietà predefinita è ambiguo tra i membri di interfaccia ereditati '<defaultpropertyname>' dell'interfaccia '<interfacename1>' e '<defaultpropertyname>' dell'interfaccia '<interfacename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 99d5dc2e0f8389f8c9e90786c4d9d0fa037eb828
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651424"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a><span data-ttu-id="30c43-102">Accesso alla proprietà predefinita è ambiguo tra i membri di interfaccia ereditati\<defaultpropertyname >' dell'interfaccia '\<interfacename1 >' e '\<defaultpropertyname >' dell'interfaccia '\< interfacename2 >'</span><span class="sxs-lookup"><span data-stu-id="30c43-102">Default property access is ambiguous between the inherited interface members '\<defaultpropertyname>' of interface '\<interfacename1>' and '\<defaultpropertyname>' of interface '\<interfacename2>'</span></span>
<span data-ttu-id="30c43-103">Un'interfaccia eredita da due interfacce, ognuno dei quali dichiara una proprietà predefinita con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="30c43-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="30c43-104">Il compilatore non è possibile risolvere un accesso a questa proprietà predefinito senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="30c43-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="30c43-105">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="30c43-105">The following example illustrates this.</span></span>  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="30c43-106">Quando si specifica `testObj(1)`, il compilatore cerca di risolvere il problema per la proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="30c43-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="30c43-107">Tuttavia, esistono due possibili proprietà predefinite a causa di interfacce ereditate, il compilatore segnala questo errore.</span><span class="sxs-lookup"><span data-stu-id="30c43-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>  
  
 <span data-ttu-id="30c43-108">**ID errore:** BC30686</span><span class="sxs-lookup"><span data-stu-id="30c43-108">**Error ID:** BC30686</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="30c43-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="30c43-109">To correct this error</span></span>  
  
- <span data-ttu-id="30c43-110">Evitare di ereditare tutti i membri con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="30c43-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="30c43-111">Nell'esempio precedente, se `testObj` non è necessario uno qualsiasi dei membri di, ad esempio, `Iface2`, dichiararla come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="30c43-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     <span data-ttu-id="30c43-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="30c43-112">-or-</span></span>  
  
- <span data-ttu-id="30c43-113">Implementare l'interfaccia che eredita in una classe.</span><span class="sxs-lookup"><span data-stu-id="30c43-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="30c43-114">È quindi possibile implementare ognuna delle proprietà ereditate con nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="30c43-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="30c43-115">Tuttavia, solo uno di essi può essere la proprietà predefinita della classe di implementazione.</span><span class="sxs-lookup"><span data-stu-id="30c43-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="30c43-116">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="30c43-116">The following example illustrates this.</span></span>  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="30c43-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30c43-117">See also</span></span>

- [<span data-ttu-id="30c43-118">Interfacce</span><span class="sxs-lookup"><span data-stu-id="30c43-118">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
