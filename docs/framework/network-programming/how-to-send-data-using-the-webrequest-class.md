---
title: 'Procedura: Inviare dati con la classe WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 1f10c5e0c6c266b7b31d658ec561bd8d6d85697b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129467"
---
# <a name="how-to-send-data-using-the-webrequest-class"></a><span data-ttu-id="172e7-102">Procedura: Inviare dati con la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="172e7-102">How to: Send Data Using the WebRequest Class</span></span>
<span data-ttu-id="172e7-103">La procedura seguente descrive i passaggi usati per inviare dati a un server.</span><span class="sxs-lookup"><span data-stu-id="172e7-103">The following procedure describes the steps used to send data to a server.</span></span> <span data-ttu-id="172e7-104">Questa procedura viene comunemente usata per pubblicare dati in una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="172e7-104">This procedure is commonly used to post data to a Web page.</span></span>  
  
### <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="172e7-105">Per inviare dati a un server host</span><span class="sxs-lookup"><span data-stu-id="172e7-105">To send data to a host server</span></span>  
  
1.  <span data-ttu-id="172e7-106">Creare un'istanza di <xref:System.Net.WebRequest> chiamando <xref:System.Net.WebRequest.Create%2A> con l'URI della risorsa che accetta i dati, ad esempio, uno script o una pagina ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="172e7-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource that accepts data, for example, a script or ASP.NET page.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="172e7-107">.NET Framework fornisce le classi specifiche del protocollo derivate da **WebRequest** e **WebResponse** per gli URI che iniziano con "http:", "https:", "ftp:" e "file:".</span><span class="sxs-lookup"><span data-stu-id="172e7-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="172e7-108">Per accedere alle risorse con altri protocolli, è necessario implementare classi specifiche del protocollo che derivano da **WebRequest** e **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="172e7-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="172e7-109">Per altre informazioni, vedere [Programmazione di protocolli di collegamento](../../../docs/framework/network-programming/programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="172e7-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="172e7-110">Impostare i valori di proprietà necessari in **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="172e7-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="172e7-111">Per abilitare l'autenticazione, ad esempio, impostare la proprietà **Credentials** su un'istanza della classe <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="172e7-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="172e7-112">Nella maggior parte dei casi, l'istanza stessa di **WebRequest** è sufficiente per inviare i dati.</span><span class="sxs-lookup"><span data-stu-id="172e7-112">In most cases, the **WebRequest** instance itself is sufficient to send data.</span></span> <span data-ttu-id="172e7-113">Tuttavia, se è necessario impostare le proprietà specifiche del protocollo, è necessario eseguire il cast di **WebRequest** sul tipo specifico del protocollo.</span><span class="sxs-lookup"><span data-stu-id="172e7-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="172e7-114">Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebRequest>, eseguire il cast di **WebRequest** su un riferimento **HttpWebRequest**.</span><span class="sxs-lookup"><span data-stu-id="172e7-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="172e7-115">L'esempio di codice seguente mostra come impostare la proprietà <xref:System.Net.HttpWebRequest.UserAgent%2A> specifica di HTTP.</span><span class="sxs-lookup"><span data-stu-id="172e7-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="172e7-116">Specificare un metodo di protocollo che consente l'invio dei dati con una richiesta, ad esempio il metodo **POST** HTTP.</span><span class="sxs-lookup"><span data-stu-id="172e7-116">Specify a protocol method that permits data to be sent with a request, such as the HTTP **POST** method.</span></span>  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  <span data-ttu-id="172e7-117">Impostare la proprietà **ContentLength**.</span><span class="sxs-lookup"><span data-stu-id="172e7-117">Set the **ContentLength** property.</span></span>  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  <span data-ttu-id="172e7-118">Impostare la proprietà **ContentType** su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="172e7-118">Set the **ContentType** property to an appropriate value.</span></span>  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  <span data-ttu-id="172e7-119">Ottenere il flusso che contiene i dati della richiesta chiamando il metodo <xref:System.Net.WebRequest.GetRequestStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="172e7-119">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span>  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  <span data-ttu-id="172e7-120">Scrivere i dati nell'oggetto <xref:System.IO.Stream> restituito da questo metodo.</span><span class="sxs-lookup"><span data-stu-id="172e7-120">Write the data to the <xref:System.IO.Stream> object returned by this method.</span></span>  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  <span data-ttu-id="172e7-121">Chiudere il flusso della richiesta chiamando il metodo **Stream.Close**.</span><span class="sxs-lookup"><span data-stu-id="172e7-121">Close the request stream by calling the **Stream.Close** method.</span></span>  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. <span data-ttu-id="172e7-122">Inviare la richiesta al server chiamando <xref:System.Net.WebRequest.GetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="172e7-122">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="172e7-123">Questo metodo restituisce un oggetto contenente la risposta del server.</span><span class="sxs-lookup"><span data-stu-id="172e7-123">This method returns an object containing the server's response.</span></span> <span data-ttu-id="172e7-124">Il tipo dell'oggetto <xref:System.Net.WebResponse> restituito viene determinato dallo schema dell'URI della richiesta.</span><span class="sxs-lookup"><span data-stu-id="172e7-124">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="172e7-125">Dopo aver finito di usare un oggetto <xref:System.Net.WebResponse>, è necessario chiuderlo chiamando il metodo <xref:System.Net.WebResponse.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="172e7-125">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="172e7-126">In alternativa, se è stato usato il flusso di risposta dall'oggetto risposta, è possibile chiudere il flusso tramite la chiamata del metodo <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="172e7-126">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="172e7-127">Se non si chiude la risposta o il flusso, l'applicazione può esaurire le connessioni al server e non essere più in grado di elaborare ulteriori richieste.</span><span class="sxs-lookup"><span data-stu-id="172e7-127">If you do not close the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
10. <span data-ttu-id="172e7-128">È possibile accedere alle proprietà di **WebResponse** oppure eseguire il cast di **WebResponse** su un'istanza specifica del protocollo per leggere le proprietà specifiche del protocollo.</span><span class="sxs-lookup"><span data-stu-id="172e7-128">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="172e7-129">Ad esempio, per accedere alle proprietà specifiche di HTTP di <xref:System.Net.HttpWebResponse>, eseguire il cast di **WebResponse** su un riferimento **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="172e7-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to an **HttpWebResponse** reference.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. <span data-ttu-id="172e7-130">Per ottenere il flusso contenente i dati di risposta inviati dal server, chiamare il metodo <xref:System.Net.WebResponse.GetResponseStream%2A> di **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="172e7-130">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. <span data-ttu-id="172e7-131">Dopo la lettura dei dati dalla risposta, è necessario chiudere il flusso di risposta tramite il metodo **Stream.Close** oppure chiudere la risposta tramite il metodo **WebResponse.Close**.</span><span class="sxs-lookup"><span data-stu-id="172e7-131">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="172e7-132">Non è necessario chiamare il metodo **Close** sia sul flusso di risposta che su **WebResponse**, ma non si tratta di un'operazione che può causare danni.</span><span class="sxs-lookup"><span data-stu-id="172e7-132">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="172e7-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="172e7-133">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestPostExample  
    {  
        public static void Main ()  
        {  
            // Create a request using a URL that can receive a post.   
            WebRequest request = WebRequest.Create ("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  
            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes (postData);  
            // Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length;  
            // Get the request stream.  
            Stream dataStream = request.GetRequestStream ();  
            // Write the data to the request stream.  
            dataStream.Write (byteArray, 0, byteArray.Length);  
            // Close the Stream object.  
            dataStream.Close ();  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams.  
            reader.Close ();  
            dataStream.Close ();  
            response.Close ();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  
Namespace Examples.System.Net  
    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  
            ' Create a request using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  
            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  
            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  
            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the Stream object.  
            dataStream.Close()  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams.  
            reader.Close()  
            dataStream.Close()  
            response.Close()  
        End Sub  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="172e7-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="172e7-134">See Also</span></span>  
 [<span data-ttu-id="172e7-135">Creazione di richieste Internet</span><span class="sxs-lookup"><span data-stu-id="172e7-135">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="172e7-136">Uso di flussi nella rete</span><span class="sxs-lookup"><span data-stu-id="172e7-136">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="172e7-137">Accesso a Internet con un proxy</span><span class="sxs-lookup"><span data-stu-id="172e7-137">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="172e7-138">Richiesta di dati</span><span class="sxs-lookup"><span data-stu-id="172e7-138">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="172e7-139">Procedura: Richiedere dati con la classe WebRequest</span><span class="sxs-lookup"><span data-stu-id="172e7-139">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
