---
title: proprietà di chiave esterna
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: 74117b30ca54f7c57bd970003fc6f5dcc54d553f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218017"
---
# <a name="foreign-key-property"></a>proprietà di chiave esterna
Oggetto *proprietà di chiave esterna* in Entity Data Model (EDM) è un tipo primitivo [proprietà](../../../../docs/framework/data/adonet/property.md) (o un set di proprietà di tipo primitivo) in un [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md) che contiene il [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md) di un altro tipo di entità.  
  
 Una proprietà di chiave esterna è analoga a una colonna di chiave esterna in un database relazionale. Nello stesso modo che le colonne chiave esterna vengono utilizzate in un database relazionale per creare relazioni tra le righe delle tabelle, le proprietà di chiave esterna in un modello concettuale vengono utilizzate per stabilire [associazioni](../../../../docs/framework/data/adonet/association-type.md) tra tipi di entità. Oggetto [vincolo di integrità referenziale](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) viene usato per definire un'associazione tra due tipi di entità quando uno dei tipi dispone di una proprietà di chiave esterna.  
  
## <a name="example"></a>Esempio  
 Nel diagramma seguente viene illustrato un modello concettuale con tre tipi di entità: `Book`, `Publisher` e `Author`. Il tipo di entità `Book` dispone di una proprietà, `PublisherId`, che fa riferimento alla chiave di entità del tipo di entità `Publisher` quando si definisce un vincolo di integrità referenziale sull'associazione `PublishedBy`.  
  
 ![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "esempio di un modello di vincolo referenziale")  
  
 Il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa un linguaggio specifico di dominio (DSL) denominato conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) per definire i modelli concettuali. Il linguaggio CSDL seguente usa la proprietà di chiave esterna `PublisherId` per definire un vincolo di integrità referenziale sull'associazione `PublishedBy` illustrata nel modello concettuale precedente.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Vedere anche

- [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
