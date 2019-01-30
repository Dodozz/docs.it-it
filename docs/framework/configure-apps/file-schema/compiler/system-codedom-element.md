---
title: Elemento < System. CodeDom >
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: e2c65044b99e2d5fda7025f24d1d4c4082ded4ec
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268223"
---
# <a name="systemcodedom-element"></a>\<System. CodeDom > elemento
Specifica le impostazioni di configurazione del compilatore per i provider di linguaggi disponibili.  
  
 \<configurazione > elemento  
\<System. CodeDom > elemento  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenitore per gli elementi di configurazione del compilatore. Contiene zero o più [elementi \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
  
## <a name="remarks"></a>Note  
  
## <a name="net-framework-version-20"></a>.NET framework versione 2.0  
 Il [ \<System. CodeDom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggi installati in un computer oltre i provider predefiniti che vengono installati con .NET Framework, ad esempio il <xref:Microsoft.CSharp.CSharpCodeProvider> e il <xref:Microsoft.VisualBasic.VBCodeProvider>. Il [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene zero o più [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementi. Ciascuna [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.  
  
 Gli sviluppatori e i produttori di compilatori possono aggiungere le impostazioni di configurazione al file di configurazione del computer (Machine. config) per un nuovo <xref:System.CodeDom.Compiler.CodeDomProvider> implementazione. Usare il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metodo per enumerare a livello di codice sia il provider del linguaggio predefiniti e i provider di linguaggi identificati dalle impostazioni di configurazione del compilatore in un computer.  
  
> [!NOTE]
>  In .NET Framework versioni 1.0 e 1.1, la lingua predefinita provider forniti da .NET Framework sono identificati i [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento. In .NET Framework versione 2.0, il provider di linguaggi predefiniti non sono identificate nel [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento, ma possono essere enumerati utilizzando il <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> (metodo).  
  
## <a name="net-framework-versions-10-and-11"></a>.NET framework versioni 1.0 e 1.1  
 Il [ \<System. CodeDom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) elemento contiene le impostazioni di configurazione del compilatore per i provider di linguaggi in un computer. Il [ \<compilatori >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene zero o più [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elementi. Ciascuna [ \<compilatore >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento specifica gli attributi di configurazione del compilatore per un provider del linguaggio specifico.  
  
 .NET Framework definisce le impostazioni del compilatore iniziali nel file di configurazione del computer (Machine.config). Gli sviluppatori e i fornitori di compilatori possono aggiungere impostazioni di configurazione per una nuova implementazione di <xref:System.CodeDom.Compiler.CodeDomProvider>. Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> per enumerare a livello di codice le impostazioni di configurazione dei provider di linguaggi e di configurazione del compilatore in un computer.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione del computer e il file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra una configurazione tipica del compilatore.  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Schema di impostazioni del compilatore e del provider di linguaggi](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)
- [\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) (Elemento <compiler>)
