---
title: Esplorazione dei tentativi di chiamate HTTP personalizzate con backoff esponenziale
description: Informazioni su come è possibile implementare, partendo da zero, i tentativi di chiamata HTTP con backoff esponenziale per gestire possibili scenari di errore HTTP.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: b7aaad9199bb275f45fd088a6207d707e8e5751c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145098"
---
# <a name="explore-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="20f1f-103">Esplorazione dei tentativi di chiamate HTTP personalizzate con backoff esponenziale</span><span class="sxs-lookup"><span data-stu-id="20f1f-103">Explore custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="20f1f-104">Per creare microservizi resilienti, è necessario gestire i possibili scenari di errore HTTP.</span><span class="sxs-lookup"><span data-stu-id="20f1f-104">To create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="20f1f-105">Un modo di gestire tali errori, ma non consigliabile, è quello di creare la propria implementazione di tentativi con il backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="20f1f-105">One way of handling those failures, although not recommended, is to create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="20f1f-106">**Nota importante:** questa sezione illustra come è possibile creare il proprio codice personalizzato per implementare i tentativi di chiamata HTTP.</span><span class="sxs-lookup"><span data-stu-id="20f1f-106">**Important note:** This section shows you how you could create your own custom code to implement HTTP call retries.</span></span> <span data-ttu-id="20f1f-107">Tuttavia, non è consigliabile eseguire questa operazione da soli, ma avvalersi di un meccanismo potente e affidabile e più semplice da usare come `HttpClientFactory` con Polly, disponibile a partire da .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="20f1f-107">However, it is not recommended to do it by your own but to use more powerful and reliable while simpler to use mechanisms, such as `HttpClientFactory` with Polly, available since .NET Core 2.1.</span></span> <span data-ttu-id="20f1f-108">Questi approcci consigliati sono illustrati nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="20f1f-108">Those recommended approaches are explained in the next sections.</span></span> 

<span data-ttu-id="20f1f-109">Per iniziare, è possibile implementare codice personalizzato con una classe di utilità per il backoff esponenziale come in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260) e del codice come quello riportato di seguito (disponibile anche in questo [repository in GitHub](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span><span class="sxs-lookup"><span data-stu-id="20f1f-109">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following (which is also available at this [GitHub repo](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span></span>

```csharp
public sealed class RetryWithExponentialBackoff
{
    private readonly int maxRetries, delayMilliseconds, maxDelayMilliseconds;

    public RetryWithExponentialBackoff(int maxRetries = 50,
        int delayMilliseconds = 200,
        int maxDelayMilliseconds = 2000)
    {
        this.maxRetries = maxRetries;
        this.delayMilliseconds = delayMilliseconds;
        this.maxDelayMilliseconds = maxDelayMilliseconds;
    }

    public async Task RunAsync(Func<Task> func)
    {
        ExponentialBackoff backoff = new ExponentialBackoff(this.maxRetries,
            this.delayMilliseconds,
            this.maxDelayMilliseconds);
        retry:
        try
        {
            await func();
        }
        catch (Exception ex) when (ex is TimeoutException ||
            ex is System.Net.Http.HttpRequestException)
        {
            Debug.WriteLine("Exception raised is: " +
                ex.GetType().ToString() +
                " –Message: " + ex.Message +
                " -- Inner Message: " +
                ex.InnerException.Message);
            await backoff.Delay();
            goto retry;
        }
    }
}

public struct ExponentialBackoff
{
    private readonly int m_maxRetries, m_delayMilliseconds, m_maxDelayMilliseconds;
    private int m_retries, m_pow;

    public ExponentialBackoff(int maxRetries, int delayMilliseconds,
        int maxDelayMilliseconds)
    {
        m_maxRetries = maxRetries;
        m_delayMilliseconds = delayMilliseconds;
        m_maxDelayMilliseconds = maxDelayMilliseconds;
        m_retries = 0;
        m_pow = 1;
    }

    public Task Delay()
    {
        if (m_retries == m_maxRetries)
        {
            throw new TimeoutException("Max retry attempts exceeded.");
        }
        ++m_retries;
        if (m_retries < 31)
        {
            m_pow = m_pow << 1; // m_pow = Pow(2, m_retries - 1)
        }
        int delay = Math.Min(m_delayMilliseconds * (m_pow - 1) / 2,
            m_maxDelayMilliseconds);
        return Task.Delay(delay);
    }
}
```

<span data-ttu-id="20f1f-110">Usando il codice in un'applicazione client C\# (un altro microservizio client dell'API Web, un'applicazione MVC ASP.NET o anche un'applicazione Xamarin C\#) è semplice.</span><span class="sxs-lookup"><span data-stu-id="20f1f-110">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="20f1f-111">L'esempio seguente spiega come procedere usando la classe HttpClient.</span><span class="sxs-lookup"><span data-stu-id="20f1f-111">The following example shows how, using the HttpClient class.</span></span>

```csharp
public async Task<Catalog> GetCatalogItems(int page,int take, int? brand, int? type)
{
    _apiClient = new HttpClient();
    var itemsQs = $"items?pageIndex={page}&pageSize={take}";
    var filterQs = "";
    var catalogUrl = $"{_remoteServiceBaseUrl}items{filterQs}?pageIndex={page}&pageSize={take}";
    var dataString = "";
    //
    // Using HttpClient with Retry and Exponential Backoff
    //
    var retry = new RetryWithExponentialBackoff();
    await retry.RunAsync(async () =>
    {
        // work with HttpClient call
        dataString = await _apiClient.GetStringAsync(catalogUrl);
    });
    return JsonConvert.DeserializeObject<Catalog>(dataString);
}
```

<span data-ttu-id="20f1f-112">Ricordare che questo codice è adatto solo come modello di verifica.</span><span class="sxs-lookup"><span data-stu-id="20f1f-112">Remember that this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="20f1f-113">Le sezioni successive illustrano come usare approcci più sofisticati, anche se più semplici, tramite HttpClientFactory.</span><span class="sxs-lookup"><span data-stu-id="20f1f-113">The next sections explain how to use more sophisticated approaches while simpler, by using HttpClientFactory.</span></span>
<span data-ttu-id="20f1f-114">HttpClientFactory è disponibile a partire dalla versione di .NET Core 2.1, con le librerie di resilienza collaudate come Polly.</span><span class="sxs-lookup"><span data-stu-id="20f1f-114">HttpClientFactory is available since .NET Core 2.1, with proven resiliency libraries like Polly.</span></span> 

>[!div class="step-by-step"]
><span data-ttu-id="20f1f-115">[Precedente](implement-resilient-entity-framework-core-sql-connections.md)
>[Successivo](use-httpclientfactory-to-implement-resilient-http-requests.md)</span><span class="sxs-lookup"><span data-stu-id="20f1f-115">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](use-httpclientfactory-to-implement-resilient-http-requests.md)</span></span>