---
title: 'Procedura: Implementare funzioni di callback'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0a033e6881f9c0c8741fda26211b0f565762de4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331325"
---
# <a name="how-to-implement-callback-functions"></a>Procedura: Implementare funzioni di callback
La procedura e l'esempio seguenti illustrano come un'applicazione gestita, usando il platform invoke, può stampare il valore di handle per ogni finestra sul computer locale. In particolare, la procedura e l'esempio usano la funzione **EnumWindows** per esaminare l'elenco di finestre e una funzione di callback gestita (denominata CallBack) per visualizzare il valore di handle della finestra.  
  
### <a name="to-implement-a-callback-function"></a>Per implementare una funzione di callback  
  
1. Esaminare la firma per la funzione **EnumWindows** prima di procedere con l'implementazione. **EnumWindows** presenta in genere la firma seguente:  
  
    ```  
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)  
    ```  
  
     Un’indicazione del fatto che questa funzione richiede un callback è la presenza dell'argomento **lpEnumFunc**. È frequente vedere il prefisso **lp** (puntatore di tipo long) combinato con il suffisso **Func** nel nome di argomenti che accettano un puntatore a una funzione di callback. Per informazioni sulle funzioni Win32, vedere Microsoft Platform SDK.  
  
2. Creare la funzione di callback gestita. L'esempio dichiara un tipo delegato, denominato `CallBack`, che accetta due argomenti (**hwnd** e **lparam**). Il primo argomento è un handle alla finestra, mentre il secondo è definito dall'applicazione. In questa versione entrambi gli argomenti devono essere numeri interi.  
  
     Funzioni di callback restituiscono in genere valori diversi da zero per indicare l’esito positivo e zero per indicare l’esito negativo. Questo esempio imposta in modo esplicito il valore restituito su **true** per continuare l'enumerazione.  
  
3. Creare un delegato e passarlo come argomento alla funzione **EnumWindows**. Platform invoke converte automaticamente il delegato in un formato di callback conosciuto.  
  
4. Assicurarsi che il garbage collector non recuperi il delegato prima che venga completata la funzione di callback. Quando si passa un delegato come parametro o si passa un delegato contenuto come campo in una struttura, questo non viene interessato per la durata della chiamata. Quindi, come nel seguente esempio di enumerazione, la funzione di callback viene completata prima che venga restituita la chiamata e non richiede operazioni aggiuntive dal chiamante gestito.  
  
     Se, tuttavia, la funzione di callback può essere richiamata dopo che viene restituita la chiamata, il chiamante gestito deve provvedere a garantire che il delegato non venga interessato fino al completamento della funzione di richiamata. Per informazioni dettagliate su come evitare operazioni di Garbage Collection, vedere [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md) con platform invoke.  
  
## <a name="example"></a>Esempio  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
  
Public Delegate Function CallBack( _  
hwnd As Integer, lParam As Integer) As Boolean  
  
Public Class EnumReportApp  
  
    Declare Function EnumWindows Lib "user32" ( _  
       x As CallBack, y As Integer) As Integer  
  
    Public Shared Sub Main()  
        EnumWindows(AddressOf EnumReportApp.Report, 0)  
    End Sub 'Main  
  
    Public Shared Function Report(hwnd As Integer, lParam As Integer) _  
    As Boolean  
        Console.Write("Window handle is ")  
        Console.WriteLine(hwnd)  
        Return True  
    End Function 'Report  
End Class 'EnumReportApp  
```  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public delegate bool CallBack(int hwnd, int lParam);  
  
public class EnumReportApp  
{  
    [DllImport("user32")]  
    public static extern int EnumWindows(CallBack x, int y);   
  
    public static void Main()   
    {  
        CallBack myCallBack = new CallBack(EnumReportApp.Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    public static bool Report(int hwnd, int lParam)  
    {   
        Console.Write("Window handle is ");  
        Console.WriteLine(hwnd);  
        return true;  
    }  
}  
```  
  
```cpp  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// A delegate type.  
delegate bool CallBack(int hwnd, int lParam);  
  
// Managed type with the method to call.  
ref class EnumReport  
{  
// Report the window handle.  
public:  
    [DllImport("user32")]  
    static int EnumWindows(CallBack^ x, int y);  
  
    static void Main()  
    {  
        EnumReport^ er = gcnew EnumReport;  
        CallBack^ myCallBack = gcnew CallBack(&EnumReport::Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    static bool Report(int hwnd, int lParam)  
    {  
       Console::Write(L"Window handle is ");  
       Console::WriteLine(hwnd);  
       return true;  
    }  
};  
  
int main()  
{  
    EnumReport::Main();  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di callback](../../../docs/framework/interop/callback-functions.md)
- [Chiamata a una funzione di DLL](../../../docs/framework/interop/calling-a-dll-function.md)
