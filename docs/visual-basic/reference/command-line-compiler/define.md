---
title: -define (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: 3560ea14236bfa2fffbc309847e8ef9e4b821de9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739271"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="bee89-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bee89-102">-define (Visual Basic)</span></span>
<span data-ttu-id="bee89-103">Definisce le costanti del compilatore condizionali.</span><span class="sxs-lookup"><span data-stu-id="bee89-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bee89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bee89-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="bee89-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="bee89-105">Arguments</span></span>  
  
|<span data-ttu-id="bee89-106">Termine</span><span class="sxs-lookup"><span data-stu-id="bee89-106">Term</span></span>|<span data-ttu-id="bee89-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="bee89-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="bee89-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bee89-108">Required.</span></span> <span data-ttu-id="bee89-109">Il simbolo da definire.</span><span class="sxs-lookup"><span data-stu-id="bee89-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="bee89-110">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="bee89-110">Optional.</span></span> <span data-ttu-id="bee89-111">Il valore da assegnare a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="bee89-111">The value to assign `symbol`.</span></span> <span data-ttu-id="bee89-112">Se `value` è una stringa, deve essere racchiuso tra sequenze di barre rovesciate/virgolette (\\") anziché le virgolette.</span><span class="sxs-lookup"><span data-stu-id="bee89-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="bee89-113">Se non è specificato un valore, è considerato True.</span><span class="sxs-lookup"><span data-stu-id="bee89-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bee89-114">Note</span><span class="sxs-lookup"><span data-stu-id="bee89-114">Remarks</span></span>  
 <span data-ttu-id="bee89-115">Il `-define` opzione ha un effetto simile all'uso di un `#Const` direttiva per il preprocessore nel file di origine, ad eccezione che le costanti definite con `-define` sono pubblici e si applicano a tutti i file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="bee89-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="bee89-116">È possibile usare i simboli creati mediante questa opzione con la direttiva `#If`...`Then`...`#Else` per eseguire la compilazione condizionale dei file di origine.</span><span class="sxs-lookup"><span data-stu-id="bee89-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="bee89-117">`-d` è la versione abbreviata di `-define`.</span><span class="sxs-lookup"><span data-stu-id="bee89-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="bee89-118">È possibile definire più simboli con `-define`, separando le definizioni dei simboli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="bee89-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="bee89-119">Per impostare /define nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bee89-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="bee89-120">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="bee89-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bee89-121">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="bee89-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="bee89-122">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="bee89-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="bee89-123">3.  Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="bee89-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="bee89-124">4.  Modificare il valore di **stanti personalizzate** casella.</span><span class="sxs-lookup"><span data-stu-id="bee89-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bee89-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="bee89-125">Example</span></span>  
 <span data-ttu-id="bee89-126">Nel codice seguente sono definite e usate due costanti di compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="bee89-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bee89-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bee89-127">See also</span></span>
- [<span data-ttu-id="bee89-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bee89-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bee89-129">Direttive #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="bee89-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="bee89-130">Direttiva #Const</span><span class="sxs-lookup"><span data-stu-id="bee89-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="bee89-131">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="bee89-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
