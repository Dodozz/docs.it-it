---
title: 'Risoluzione dei problemi: listener di log (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 3d21024a7ebda749f337a95b0fca419b529d2872
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662816"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a>Risoluzione dei problemi: listener di log (Visual Basic)
È possibile usare gli oggetti `My.Application.Log` e `My.Log` per registrare informazioni sugli eventi che si verificano nell'applicazione.  
  
 Per determinare i listener di log che ricevono questi messaggi, vedere [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
 L'oggetto `Log` può usare il filtro di log per limitare la quantità di informazioni registrate. Se i filtri non sono configurati correttamente, i log possono contenere informazioni errate. Per altre informazioni sui filtri, vedere [Procedura dettagliata: Filtro dell'output di My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).  
  
 Se tuttavia un log è configurato in modo errato, potrebbero essere necessarie maggiori informazioni sulla configurazione corrente. È possibile ottenere tali informazioni grazie alla proprietà avanzata `TraceSource` del log.  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a>Per determinare i listener di log per l'oggetto Log nel codice  
  
1.  Importare lo spazio dei nomi <xref:System.Diagnostics> all'inizio del file di codice. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
     [!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]  
  
2.  Creare una funzione che consente di restituire una stringa costituita dalle informazioni relative a ognuno dei listener di log.  
  
     [!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]  
  
3.  Passare la raccolta dei listener di traccia del log alla funzione `GetListeners` e visualizzare il valore restituito.  
  
     [!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]  
  
     Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Utilizzo dei log applicazione](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
