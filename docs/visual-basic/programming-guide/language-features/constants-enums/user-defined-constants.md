---
title: Costanti definite dall'utente (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: dc940105bbeb5e54819b8df5d5b3c831c7a6e145
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527315"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="098ba-102">Costanti definite dall'utente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="098ba-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="098ba-103">Una costante è un nome significativo che prende il posto di un numero o una stringa che non cambia.</span><span class="sxs-lookup"><span data-stu-id="098ba-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="098ba-104">Archiviano i valori che, come suggerisce il nome, rimangono costanti durante l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="098ba-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="098ba-105">È possibile usare le costanti che vengono definite tramite i controlli o si lavora con i componenti oppure è possibile crearne uno.</span><span class="sxs-lookup"><span data-stu-id="098ba-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="098ba-106">Vengono descritte le costanti personalizzate come *definite dall'utente*.</span><span class="sxs-lookup"><span data-stu-id="098ba-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="098ba-107">Consente di dichiarare una costante con i `Const` istruzione, utilizzando le stesse linee guida si farebbe per la creazione di un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="098ba-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="098ba-108">Se `Option Strict` è `On`, è necessario dichiarare in modo esplicito il tipo di costante.</span><span class="sxs-lookup"><span data-stu-id="098ba-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="098ba-109">Utilizzo dell'istruzione const</span><span class="sxs-lookup"><span data-stu-id="098ba-109">Const Statement Usage</span></span>  
 <span data-ttu-id="098ba-110">Oggetto `Const` istruzione può rappresentare un matematiche o date/time quantity:</span><span class="sxs-lookup"><span data-stu-id="098ba-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 <span data-ttu-id="098ba-111">Inoltre possibile definire `String` costanti:</span><span class="sxs-lookup"><span data-stu-id="098ba-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 <span data-ttu-id="098ba-112">L'espressione a destra del segno di uguale ( `=` ) è spesso un numero o valore letterale stringa, ma può essere anche un'espressione che restituisce un numero o una stringa (anche se tale espressione non può contenere chiamate alle funzioni).</span><span class="sxs-lookup"><span data-stu-id="098ba-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="098ba-113">È anche possibile definire le costanti in termini di costanti definite in precedenza:</span><span class="sxs-lookup"><span data-stu-id="098ba-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="098ba-114">Ambito delle costanti definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="098ba-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="098ba-115">Oggetto `Const` ambito dell'istruzione è uguale a quello di una variabile dichiarata nello stesso percorso.</span><span class="sxs-lookup"><span data-stu-id="098ba-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="098ba-116">È possibile specificare l'ambito in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="098ba-116">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="098ba-117">Per creare una costante che esiste solo all'interno di una routine, dichiararlo all'interno di tale procedura.</span><span class="sxs-lookup"><span data-stu-id="098ba-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="098ba-118">Per creare una costante che sia disponibile per tutte le routine all'interno di una classe, ma non a qualsiasi codice all'esterno di tale modulo, dichiararlo nella sezione delle dichiarazioni della classe.</span><span class="sxs-lookup"><span data-stu-id="098ba-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="098ba-119">Per creare una costante che sia disponibile per tutti i membri di un assembly, ma non ai client all'esterno dell'assembly, dichiarare usando il `Friend` parola chiave nella sezione delle dichiarazioni della classe.</span><span class="sxs-lookup"><span data-stu-id="098ba-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="098ba-120">Per creare una costante disponibile in tutta l'applicazione, dichiarare usando il `Public` parola chiave nelle dichiarazioni di sezione la classe.</span><span class="sxs-lookup"><span data-stu-id="098ba-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="098ba-121">Per altre informazioni, vedere [Procedura: Dichiarare una costante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="098ba-121">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="098ba-122">Evitare riferimenti circolari</span><span class="sxs-lookup"><span data-stu-id="098ba-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="098ba-123">Poiché le costanti possono essere definite in termini di altre costanti, è possibile creare inavvertitamente un *ciclo*, o riferimento circolare tra due o più costanti.</span><span class="sxs-lookup"><span data-stu-id="098ba-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="098ba-124">Un ciclo si verifica quando si dispone di due o più costanti pubbliche, ognuno dei quali è definito in termini di altro, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="098ba-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 <span data-ttu-id="098ba-125">Se si verifica un ciclo, Visual Basic genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="098ba-125">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="098ba-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="098ba-126">See also</span></span>
- [<span data-ttu-id="098ba-127">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="098ba-127">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="098ba-128">Tipi di dati costanti e letterali</span><span class="sxs-lookup"><span data-stu-id="098ba-128">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="098ba-129">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="098ba-129">Constants and Enumerations</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="098ba-130">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="098ba-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="098ba-131">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="098ba-131">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="098ba-132">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="098ba-132">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="098ba-133">Procedura: Dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="098ba-133">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="098ba-134">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="098ba-134">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="098ba-135">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="098ba-135">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
