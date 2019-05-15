---
title: 'Mitigazione: Convalida di XML Schema'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc0232e0187c795fe20e6a99d4a710ba6244e34e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599669"
---
# <a name="mitigation-xml-schema-validation"></a>Mitigazione: Convalida di XML Schema
In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] la convalida dello schema XSD rileva la violazione di vincoli univoci se viene usata una chiave composta e una chiave è vuota.  
  
## <a name="impact"></a>Impatto  
 L'impatto di questa modifica potrebbe essere minimo: basato sulla specifica dello schema, un errore di convalida dello schema è previsto se `xsd:unique` viene violato da una chiave composta con una chiave vuota.  
  
## <a name="mitigation"></a>Mitigazione  
 La rilevazione di un errore di convalida dello schema se una chiave composta possiede una chiave vuota è una funzione configurabile:  
  
- A partire dalle app destinate a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la rilevazione dell'errore di convalida dello schema viene abilitata per impostazione predefinita; tuttavia, è possibile escluderla, in modo che l'errore di convalida dello schema non venga rilevato.  
  
- Nelle app eseguite in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ma destinate a [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] e versioni successive la rilevazione di un errore di convalida dello schema non viene eseguita per impostazione predefinita; è possibile consentirla in modo che l'errore di convalida dello schema venga rilevato.  
  
 Questo comportamento può essere configurato usando la classe <xref:System.AppContext> per definire il valore dell'opzione `System.Xml.IgnoreEmptyKeySequences`. Dal momento che il valore predefinito dell'opzione è `false` (le sequenze di tasti vuote non vengono ignorate), le app destinate a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] possono escludere il comportamento usando il codice seguente per impostare il valore dell'opzione su `true`:  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Per le app destinate a [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] e versioni precedenti, dal momento che il valore predefinito dell'opzione è `true` (le sequenze vuote di chiavi vengono ignorate), è possibile garantire che una chiave composta con una chiave vuota generi un errore di convalida dello schema usando il codice seguente per impostare il valore dell'opzione su `false`.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Modifiche di reindirizzamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
