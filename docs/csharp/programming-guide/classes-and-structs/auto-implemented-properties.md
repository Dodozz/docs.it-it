---
title: Proprietà implementate automaticamente - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 1277e0908b42b6f8185219a33c2b28537c8b6607
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244193"
---
# <a name="auto-implemented-properties-c-programming-guide"></a>Proprietà implementate automaticamente (Guida per programmatori C#)
In C# 3.0 e versioni successive, le proprietà implementate automaticamente rendono più concisa la dichiarazione di proprietà quando nelle funzioni di accesso della proprietà non è necessaria alcuna logica aggiuntiva. Consentono inoltre al codice client di creare oggetti. Quando si dichiara una proprietà come mostrato nel seguente esempio, il compilatore crea un campo sottostante privato anonimo accessibile solo tramite le funzioni di accesso `get` e `set` della proprietà.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra una classe semplice con alcune proprietà implementate automaticamente:  
  
 [!code-csharp[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 In C# 6 e versioni successive, è possibile inizializzare le proprietà implementate automaticamente in modo simile ai campi:  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 La classe mostrata nell'esempio precedente è modificabile. Il codice client può modificare i valori negli oggetti dopo che sono stati creati. Nelle classi complesse che contengono un comportamento significativo (metodi) oltre ai dati, spesso è necessario disporre di proprietà pubbliche. Tuttavia, per le classi o gli struct di piccole dimensioni che incapsulano solo un set di valori (dati) e non hanno comportamenti oppure hanno comportamenti limitati, è consigliabile rendere gli oggetti non modificabili dichiarando la funzione di accesso set come [private](../../../csharp/language-reference/keywords/private.md) (non modificabile dai consumer) o dichiarando solo una funzione di accesso get (non modificabile, tranne che nel costruttore).  Per altre informazioni, vedere [Procedura: Implementare una classe leggera con proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).  
  
 Gli attributi sono consentiti nelle proprietà implementate automaticamente, ma ovviamente non nei campi sottostanti perché non sono accessibili dal codice sorgente. Se è necessario usare un attributo nel campo sottostante di una proprietà, è sufficiente creare una normale proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)
