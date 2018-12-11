---
title: Convenzioni per l'utilizzo di maiuscole e minuscole
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
author: KrzysztofCwalina
ms.openlocfilehash: 159635d6e3ce414c8fd45ff7f02a75fd7cbdfe7e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131092"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="4bfb8-102">Convenzioni per l'utilizzo di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="4bfb8-102">Capitalization Conventions</span></span>
<span data-ttu-id="4bfb8-103">Le linee guida in questo capitolo disporre un metodo semplice per l'utilizzo di case che, quando applicata in modo coerente, verificare gli identificatori per i tipi, membri e parametri di facile lettura.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="4bfb8-104">Regole di maiuscole/minuscole per gli identificatori</span><span class="sxs-lookup"><span data-stu-id="4bfb8-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="4bfb8-105">Per differenziare le parole in un identificatore, converte in maiuscolo la prima lettera di ogni parola nell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="4bfb8-106">Non usare caratteri di sottolineatura per differenziare le parole o parimenti, in qualsiasi punto negli identificatori.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="4bfb8-107">Esistono due modi appropriati da convertire in maiuscolo identificatori, a seconda dell'utilizzo dell'identificatore:</span><span class="sxs-lookup"><span data-stu-id="4bfb8-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
-   <span data-ttu-id="4bfb8-108">Sistema Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-108">PascalCasing</span></span>  
  
-   <span data-ttu-id="4bfb8-109">notazione camel</span><span class="sxs-lookup"><span data-stu-id="4bfb8-109">camelCasing</span></span>  
  
 <span data-ttu-id="4bfb8-110">La convenzione, il sistema Pascal utilizzata per tutti gli identificatori, ad eccezione di nomi di parametro, converte in maiuscolo il primo carattere di ogni parola (inclusi gli acronimi su due lettere), come illustrato negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4bfb8-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="4bfb8-111">Un caso speciale viene effettuato per due lettere acronimi in cui sia le lettere sono in maiuscolo, come illustrato nell'identificatore seguente:</span><span class="sxs-lookup"><span data-stu-id="4bfb8-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="4bfb8-112">La convenzione camel, usata solo per i nomi dei parametri, converte in maiuscolo il primo carattere di ogni parola eccetto la prima parola, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="4bfb8-113">Come illustrato anche nell'esempio, gli acronimi di due lettere che iniziano un identificatore di maiuscole/minuscole camel sono entrambi caratteri minuscoli.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="4bfb8-114">**✓ DO** utilizzare il sistema Pascal per tutti i membri, tipo e spazio dei nomi nomi pubblici composta da più parole.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="4bfb8-115">**✓ DO** utilizzare camel per i nomi dei parametri.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="4bfb8-116">Nella tabella seguente vengono descritte le regole di maiuscole/minuscole per i diversi tipi di identificatori.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="4bfb8-117">Identificatore</span><span class="sxs-lookup"><span data-stu-id="4bfb8-117">Identifier</span></span>|<span data-ttu-id="4bfb8-118">Maiuscole/minuscole</span><span class="sxs-lookup"><span data-stu-id="4bfb8-118">Casing</span></span>|<span data-ttu-id="4bfb8-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bfb8-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="4bfb8-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4bfb8-120">Namespace</span></span>|<span data-ttu-id="4bfb8-121">Convenzione Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="4bfb8-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="4bfb8-122">Type</span></span>|<span data-ttu-id="4bfb8-123">Convenzione Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="4bfb8-124">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="4bfb8-124">Interface</span></span>|<span data-ttu-id="4bfb8-125">Convenzione Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="4bfb8-126">Metodo</span><span class="sxs-lookup"><span data-stu-id="4bfb8-126">Method</span></span>|<span data-ttu-id="4bfb8-127">Convenzione Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="4bfb8-128">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4bfb8-128">Property</span></span>|<span data-ttu-id="4bfb8-129">Convenzione Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="4bfb8-130">event</span><span class="sxs-lookup"><span data-stu-id="4bfb8-130">Event</span></span>|<span data-ttu-id="4bfb8-131">Convenzione Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="4bfb8-132">Campo</span><span class="sxs-lookup"><span data-stu-id="4bfb8-132">Field</span></span>|<span data-ttu-id="4bfb8-133">Convenzione Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="4bfb8-134">Valore enum</span><span class="sxs-lookup"><span data-stu-id="4bfb8-134">Enum value</span></span>|<span data-ttu-id="4bfb8-135">Convenzione Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="4bfb8-136">Parametro</span><span class="sxs-lookup"><span data-stu-id="4bfb8-136">Parameter</span></span>|<span data-ttu-id="4bfb8-137">Notazione camel</span><span class="sxs-lookup"><span data-stu-id="4bfb8-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="4bfb8-138">Sfruttando le parole composte e termini comuni</span><span class="sxs-lookup"><span data-stu-id="4bfb8-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="4bfb8-139">La maggior parte dei termini composte vengono considerate come singole parole per scopi di maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="4bfb8-140">**X DO NOT** tutte iniziali maiuscole in cosiddette parole composte forma chiusa.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="4bfb8-141">Queste sono le parole composte scritte come una parola singola, come endpoint.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="4bfb8-142">Ai fini di linee guida per le maiuscole e minuscole, considerare una chiusura parola composta come una singola parola.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="4bfb8-143">Usare un dizionario corrente per determinare se una parola composta è scritto in forma chiusa.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="4bfb8-144">Convenzione Pascal</span><span class="sxs-lookup"><span data-stu-id="4bfb8-144">Pascal</span></span>|<span data-ttu-id="4bfb8-145">Notazione camel</span><span class="sxs-lookup"><span data-stu-id="4bfb8-145">Camel</span></span>|<span data-ttu-id="4bfb8-146">non</span><span class="sxs-lookup"><span data-stu-id="4bfb8-146">Not</span></span>|  
|------------|-----------|---------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## <a name="case-sensitivity"></a><span data-ttu-id="4bfb8-147">Distinzione fra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="4bfb8-147">Case Sensitivity</span></span>  
 <span data-ttu-id="4bfb8-148">I linguaggi che è possano eseguirla in CLR non devono supportare distinzione maiuscole/minuscole, anche se alcune eseguire.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="4bfb8-149">Anche se il linguaggio la supporta, altri linguaggi che potrebbero accedere il framework non.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="4bfb8-150">Tutte le API che siano accessibili esternamente, pertanto, non si basano su case da solo per distinguere tra i due nomi nello stesso contesto.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="4bfb8-151">**X DO NOT** presupporre che tutti i linguaggi di programmazione siano distinzione maiuscole / minuscole.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="4bfb8-152">Ma non lo sono.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-152">They are not.</span></span> <span data-ttu-id="4bfb8-153">I nomi non può essere diversa di maiuscole/minuscole solo.</span><span class="sxs-lookup"><span data-stu-id="4bfb8-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="4bfb8-154">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="4bfb8-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4bfb8-155">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4bfb8-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfb8-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bfb8-156">See also</span></span>

- [<span data-ttu-id="4bfb8-157">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="4bfb8-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="4bfb8-158">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="4bfb8-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
