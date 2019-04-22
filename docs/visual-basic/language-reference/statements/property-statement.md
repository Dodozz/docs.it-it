---
title: Istruzione Property (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 7b2d388cbcd1995178adf4102520ecaa1c9b1889
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814190"
---
# <a name="property-statement"></a>Property Statement
Dichiara il nome di una proprietà e le routine della proprietà utilizzate per archiviare e recuperare il valore della proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
```  
  
## <a name="parts"></a>Parti  
  
-   `attributelist`  
  
     Facoltativo. Elenco di attributi che si applicano a questa proprietà o `Get` o `Set` procedure. Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Default`  
  
     Facoltativo. Specifica che questa proprietà è la proprietà predefinita per la classe o struttura in cui è definito. Impostazione predefinita deve accettare parametri e possono essere impostare e recuperare proprietà senza specificare il nome della proprietà. Se si dichiara la proprietà come `Default`, non è possibile usare `Private` sulla proprietà o in una delle routine della proprietà.  
  
-   `accessmodifier`  
  
     Facoltativo nella `Property` istruzione e al massimo uno tra il `Get` e `Set` istruzioni. Può essere uno dei seguenti:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [Protected Friend](../../language-reference/modifiers/protected-friend.md) 

    - [Private Protected](../../language-reference/modifiers/private-protected.md)
  
     Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `propertymodifiers`  
  
     Facoltativo. Può essere uno dei seguenti:  
  
    -   [Overload](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Facoltativo. Visualizzare [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Facoltativo. Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `ReadOnly`  
  
     Facoltativo. Visualizzare [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WriteOnly`  
  
     Facoltativo. Visualizzare [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   `Iterator`  
  
     Facoltativo. Visualizzare [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Obbligatorio. Nome della proprietà. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `parameterlist`  
  
     Facoltativo. Elenco di nomi delle variabili locali che rappresentano i parametri di questa proprietà e gli eventuali parametri aggiuntivi del `Set` procedure. Visualizzare [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `returntype`  
  
     Obbligatorio se `Option Strict` è `On`. Tipo di dati del valore restituito da questa proprietà.  
  
-   `Implements`  
  
     Facoltativo. Indica che questa proprietà implementa una o più proprietà, ognuno dei quali definito in un'interfaccia implementata dalla classe o struttura contenente questa proprietà. Visualizzare [implementa istruzione](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
-   `implementslist`  
  
     Necessario se si fornisce `Implements`. Elenco di proprietà in fase di implementazione.  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     Ogni `implementedproperty` presenta la sintassi e le parti seguenti:  
  
     `interface.definedname`  
  
    |Parte|Descrizione|  
    |---|---|  
    |`interface`|Obbligatorio. Nome di un'interfaccia implementata da questa proprietà che contiene classe o struttura.|  
    |`definedname`|Obbligatorio. Nome mediante il quale la proprietà è definita in `interface`.|  
  
-   `Get`  
  
     Facoltativo. Obbligatorio se la proprietà è contrassegnata `WriteOnly`. Avvia un `Get` routine della proprietà che viene utilizzato per restituire il valore della proprietà.  
  
-   `statements`  
  
     Facoltativo. Blocco di istruzioni da eseguire all'interno di `Get` o `Set` procedure.  
  
-   `End Get`  
  
     Termina il `Get` routine della proprietà.  
  
-   `Set`  
  
     Facoltativo. Obbligatorio se la proprietà è contrassegnata `ReadOnly`. Avvia un `Set` routine della proprietà che viene usato per archiviare il valore della proprietà.  
  
-   `End Set`  
  
     Termina il `Set` routine della proprietà.  
  
-   `End Property`  
  
     Termina la definizione di questa proprietà.  
  
## <a name="remarks"></a>Note  
 Il `Property` istruzione introduce la dichiarazione di una proprietà. Una proprietà può avere una `Get` procedure (sola lettura), un `Set` procedure (sola scrittura) o entrambe (lettura-scrittura). È possibile omettere il `Get` e `Set` procedura quando si usa una proprietà implementata automaticamente. Per altre informazioni, vedere [Proprietà implementate automaticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 È possibile usare `Property` solo a livello di classe. Ciò significa che il *contesto della dichiarazione* per una proprietà deve essere una classe, struttura, modulo o interfaccia e non può essere un file di origine, lo spazio dei nomi, procedura o blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Per impostazione predefinita, le proprietà usano l'accesso pubblico. È possibile modificare il livello di accesso della proprietà con un modificatore di accesso nella `Property` istruzione ed è anche possibile impostare una delle routine della proprietà a un livello di accesso più restrittivo.  
  
 Visual Basic passa un parametro per il `Set` procedura durante le assegnazioni di proprietà. Se non si specifica un parametro per `Set`, l'ambiente di sviluppo integrato (IDE) usa un parametro implicito denominato `value`. Questo parametro contiene il valore da assegnare alla proprietà. In genere archivia questo valore in una variabile locale privata e restituirlo ogni volta che il `Get` routine viene chiamata.  
  
## <a name="rules"></a>Regole  
  
-   **Livelli di accesso misti.** Se si sta definendo una proprietà di lettura / scrittura, è possibile specificare facoltativamente un livello di accesso diversi per il `Get` o il `Set` procedure, ma non entrambi. In questo caso, il livello di accesso di routine deve essere più restrittivo rispetto a livello di accesso della proprietà. Ad esempio, se la proprietà è dichiarata `Friend`, è possibile dichiarare il `Set` routine `Private`, ma non `Public`.  
  
     Se si sta definendo un `ReadOnly` oppure `WriteOnly` proprietà, la procedura singola proprietà (`Get` o `Set`rispettivamente) rappresenta tutte le proprietà. È possibile dichiarare un livello di accesso diversi per una procedura, poiché verrebbero specificati due livelli di accesso per la proprietà.  
  
-   **Tipo restituito.** Il `Property` istruzione può dichiarare il tipo di dati del valore restituito. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.  
  
     Se non si specifica `returntype`, la proprietà restituisce `Object`.  
  
-   **Implementazione.** Se questa proprietà Usa il `Implements` parola chiave, alla classe o struttura deve avere un' `Implements` istruzione immediatamente successiva a relativo `Class` o `Structure` istruzione. Il `Implements` istruzione deve includere ogni interfaccia specificata `implementslist`. Tuttavia, il nome mediante il quale definisce un'interfaccia di `Property` (in `definedname`) non deve essere identico al nome di questa proprietà (in `name`).  
  
## <a name="behavior"></a>Comportamento  
  
-   **Restituzione da una routine di proprietà.** Quando la `Get` o `Set` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo ha richiamato.  
  
     Il `Exit Property` e `Return` istruzioni di uscire immediatamente da una routine di proprietà. Un numero qualsiasi di `Exit Property` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Property` e `Return` istruzioni.  
  
-   **Valore restituito.** Per restituire un valore da un `Get` procedure, è possibile assegnare il valore per il nome della proprietà o includerlo in un `Return` istruzione. L'esempio seguente assegna il valore restituito per il nome della proprietà `quoteForTheDay` e quindi Usa il `Exit Property` istruzione da restituire.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     Se si usa `Exit Property` senza assegnarle un valore per `name`, il `Get` procedure restituisce il valore predefinito per il tipo di dati della proprietà.  
  
     Il `Return` istruzione allo stesso tempo assegna il `Get` procedure restituire valore e viene chiuso la procedura. L'esempio seguente illustra questo.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente dichiara una proprietà in una classe.  
  
 [!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]  
  
## <a name="see-also"></a>Vedere anche

- [Proprietà implementate automaticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)
- [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
- [Elenco dei parametri](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Default](../../../visual-basic/language-reference/modifiers/default.md)
