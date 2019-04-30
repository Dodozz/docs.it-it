---
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
ms.openlocfilehash: 15304630eb8a14e01d4815ddddc84cd32796fdcf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963449"
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="e4971-102">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="e4971-102">LocalServiceSecuritySettings</span></span>
<span data-ttu-id="e4971-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="e4971-103">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4971-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4971-104">Syntax</span></span>  
  
```csharp
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e4971-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e4971-105">Methods</span></span>  
 <span data-ttu-id="e4971-106">La classe LocalServiceSecuritySettings non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="e4971-106">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e4971-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e4971-107">Properties</span></span>  
 <span data-ttu-id="e4971-108">La classe LocalServiceSecuritySettings dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4971-108">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="e4971-109">DetectReplays</span><span class="sxs-lookup"><span data-stu-id="e4971-109">DetectReplays</span></span>  
 <span data-ttu-id="e4971-110">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="e4971-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="e4971-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-112">Valore booleano che specifica se gli attacchi di tipo replay contro il canale vengono rilevati e gestiti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e4971-112">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="e4971-113">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="e4971-113">InactivityTimeout</span></span>  
 <span data-ttu-id="e4971-114">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e4971-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="e4971-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-116">Numero massimo di sessioni di sicurezza in sospeso supportate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="e4971-116">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="e4971-117">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="e4971-117">IssuedCookieLifetime</span></span>  
 <span data-ttu-id="e4971-118">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e4971-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="e4971-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-120">TimeSpan che specifica la durata per tutti i nuovi cookie di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e4971-120">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="e4971-121">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="e4971-121">MaxCachedCookies</span></span>  
 <span data-ttu-id="e4971-122">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e4971-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="e4971-123">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-124">Numero massimo di cookie che possono essere memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="e4971-124">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="e4971-125">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="e4971-125">MaxClockSkew</span></span>  
 <span data-ttu-id="e4971-126">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e4971-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="e4971-127">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-128">TimeSpan che specifica la differenza massima di tempo tra gli orologi di sistema delle due parti che stanno comunicando.</span><span class="sxs-lookup"><span data-stu-id="e4971-128">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="e4971-129">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="e4971-129">MaxPendingSessions</span></span>  
 <span data-ttu-id="e4971-130">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e4971-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="e4971-131">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-132">Numero massimo di connessioni in sospeso nel servizio.</span><span class="sxs-lookup"><span data-stu-id="e4971-132">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="e4971-133">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="e4971-133">MaxStatefulNegotiations</span></span>  
 <span data-ttu-id="e4971-134">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e4971-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="e4971-135">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-136">Numero di negoziazioni di sicurezza che possono essere attive contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e4971-136">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="e4971-137">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="e4971-137">NegotiationTimeout</span></span>  
 <span data-ttu-id="e4971-138">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e4971-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="e4971-139">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-140">TimeSpan che specifica la durata massima della fase di negoziazione della protezione tra server e client.</span><span class="sxs-lookup"><span data-stu-id="e4971-140">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="e4971-141">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="e4971-141">ReconnectTransportOnFailure</span></span>  
 <span data-ttu-id="e4971-142">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="e4971-142">Data type: boolean</span></span>  
  
 <span data-ttu-id="e4971-143">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-144">Valore booleano che specifica se le connessioni che utilizzano WS-Reliable Messaging tentano la riconnessione in caso di errori del trasporto.</span><span class="sxs-lookup"><span data-stu-id="e4971-144">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="e4971-145">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="e4971-145">ReplayCacheSize</span></span>  
 <span data-ttu-id="e4971-146">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="e4971-146">Data type: sint32</span></span>  
  
 <span data-ttu-id="e4971-147">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-148">Numero di parametri nonce utilizzato per il rilevamento degli attacchi di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="e4971-148">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="e4971-149">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="e4971-149">ReplayWindow</span></span>  
 <span data-ttu-id="e4971-150">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e4971-150">Data type: datetime</span></span>  
  
 <span data-ttu-id="e4971-151">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-152">TimeSpan che specifica la durata di validità dei singoli nonce dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="e4971-152">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="e4971-153">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="e4971-153">SessionKeyRenewalInterval</span></span>  
 <span data-ttu-id="e4971-154">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e4971-154">Data type: datetime</span></span>  
  
 <span data-ttu-id="e4971-155">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-156">Timespan che specifica l'intervallo di tempo dopo il quale l'iniziatore rinnova la chiave per la sessione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e4971-156">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="e4971-157">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="e4971-157">SessionKeyRolloverInterval</span></span>  
 <span data-ttu-id="e4971-158">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e4971-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="e4971-159">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-160">TimeSpan che specifica l'intervallo di tempo per il quale la chiave della sessione precedente è valida nei messaggi in arrivo durante un rinnovo della chiave.</span><span class="sxs-lookup"><span data-stu-id="e4971-160">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="e4971-161">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="e4971-161">TimestampValidityDuration</span></span>  
 <span data-ttu-id="e4971-162">Tipo di dati: DateTime</span><span class="sxs-lookup"><span data-stu-id="e4971-162">Data type: datetime</span></span>  
  
 <span data-ttu-id="e4971-163">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="e4971-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4971-164">TimeSpan che specifica il periodo di validità di un timestamp.</span><span class="sxs-lookup"><span data-stu-id="e4971-164">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4971-165">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4971-165">Requirements</span></span>  
  
|<span data-ttu-id="e4971-166">MOF</span><span class="sxs-lookup"><span data-stu-id="e4971-166">MOF</span></span>|<span data-ttu-id="e4971-167">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e4971-167">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e4971-168">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="e4971-168">Namespace</span></span>|<span data-ttu-id="e4971-169">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e4971-169">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4971-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4971-170">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
