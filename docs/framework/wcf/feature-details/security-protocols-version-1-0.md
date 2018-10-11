---
title: Protocolli di sicurezza versione 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
author: BrucePerlerMS
ms.openlocfilehash: 59d82fc3238f12b33f3111c88854b9d6348a5e27
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086791"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="d8bff-102">Protocolli di sicurezza versione 1.0</span><span class="sxs-lookup"><span data-stu-id="d8bff-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="d8bff-103">I protocolli di sicurezza dei servizi Web forniscono meccanismi di sicurezza che soddisfano qualsiasi requisito di sicurezza aziendale esistente relativo alla messaggistica.</span><span class="sxs-lookup"><span data-stu-id="d8bff-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="d8bff-104">Questa sezione vengono descritti i dettagli di Windows Communication Foundation (WCF) versione 1.0 (implementate nel <xref:System.ServiceModel.Channels.SecurityBindingElement>) per i protocolli di sicurezza dei servizi Web seguenti.</span><span class="sxs-lookup"><span data-stu-id="d8bff-104">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="d8bff-105">Specifica/documento</span><span class="sxs-lookup"><span data-stu-id="d8bff-105">Specification/Document</span></span>|<span data-ttu-id="d8bff-106">Link</span><span class="sxs-lookup"><span data-stu-id="d8bff-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="d8bff-107">WSS: SOAP Message Security 1,0</span><span class="sxs-lookup"><span data-stu-id="d8bff-107">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="d8bff-108">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="d8bff-108">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="d8bff-109">WSS: X509 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="d8bff-109">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="d8bff-110">WSS: SAML 1.1 Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="d8bff-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="d8bff-111">WSS: SOAP Message Security 1.1</span><span class="sxs-lookup"><span data-stu-id="d8bff-111">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="d8bff-112">WSS Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="d8bff-112">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="d8bff-113">WSS: X.509 Token Profile 1,1</span><span class="sxs-lookup"><span data-stu-id="d8bff-113">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="d8bff-114">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="d8bff-114">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="d8bff-115">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="d8bff-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="d8bff-116">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="d8bff-116">WS-Secure Conversation</span></span>|<http://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="d8bff-117">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="d8bff-117">WS-Trust</span></span>|<http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="d8bff-118">Note sull'applicazione:</span><span class="sxs-lookup"><span data-stu-id="d8bff-118">Application Note:</span></span><br /><br /> <span data-ttu-id="d8bff-119">Uso di WS-Trust per l'handshake TLS</span><span class="sxs-lookup"><span data-stu-id="d8bff-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="d8bff-120">Non ancora pubblicato</span><span class="sxs-lookup"><span data-stu-id="d8bff-120">To be published</span></span>|  
|<span data-ttu-id="d8bff-121">Note sull'applicazione:</span><span class="sxs-lookup"><span data-stu-id="d8bff-121">Application Note:</span></span><br /><br /> <span data-ttu-id="d8bff-122">Uso di WS-Trust per SPNEGO</span><span class="sxs-lookup"><span data-stu-id="d8bff-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="d8bff-123">Non ancora pubblicato</span><span class="sxs-lookup"><span data-stu-id="d8bff-123">To be published</span></span>|  
|<span data-ttu-id="d8bff-124">Note sull'applicazione:</span><span class="sxs-lookup"><span data-stu-id="d8bff-124">Application Note:</span></span><br /><br /> <span data-ttu-id="d8bff-125">Riferimenti e identità degli endpoint di indirizzamento dei servizi Web</span><span class="sxs-lookup"><span data-stu-id="d8bff-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="d8bff-126">Non ancora pubblicato</span><span class="sxs-lookup"><span data-stu-id="d8bff-126">To be published</span></span>|  
|<span data-ttu-id="d8bff-127">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="d8bff-127">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="d8bff-128">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="d8bff-128">(2005/07)</span></span>|<http://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="d8bff-129">rettificato in base [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) inviato al comitato tecnico OASIS WS-SX TC</span><span class="sxs-lookup"><span data-stu-id="d8bff-129">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="d8bff-130">WCF, la versione 1, offre 17 modalità di autenticazione che può essere utilizzata come base per la configurazione di sicurezza di servizi Web.</span><span class="sxs-lookup"><span data-stu-id="d8bff-130">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="d8bff-131">Ogni modalità è ottimizzata per un set comune di requisiti di distribuzione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d8bff-131">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
-   <span data-ttu-id="d8bff-132">Credenziali usate per l'autenticazione di client e servizi.</span><span class="sxs-lookup"><span data-stu-id="d8bff-132">Credentials used to authenticate client and service.</span></span>  
  
-   <span data-ttu-id="d8bff-133">Meccanismi di sicurezza a livello di messaggio o di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-133">Message or transport security protection mechanisms.</span></span>  
  
-   <span data-ttu-id="d8bff-134">Modelli di scambio dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d8bff-134">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="d8bff-135">Modalità di autenticazione</span><span class="sxs-lookup"><span data-stu-id="d8bff-135">Authentication Mode</span></span>|<span data-ttu-id="d8bff-136">Autenticazione client</span><span class="sxs-lookup"><span data-stu-id="d8bff-136">Client Authentication</span></span>|<span data-ttu-id="d8bff-137">Autenticazione server</span><span class="sxs-lookup"><span data-stu-id="d8bff-137">Server Authentication</span></span>|<span data-ttu-id="d8bff-138">Modalità</span><span class="sxs-lookup"><span data-stu-id="d8bff-138">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="d8bff-139">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-139">UserNameOverTransport</span></span>|<span data-ttu-id="d8bff-140">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="d8bff-140">User name/password</span></span>|<span data-ttu-id="d8bff-141">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-141">X509</span></span>|<span data-ttu-id="d8bff-142">Trasporto</span><span class="sxs-lookup"><span data-stu-id="d8bff-142">Transport</span></span>|  
|<span data-ttu-id="d8bff-143">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-143">CertificateOverTransport</span></span>|<span data-ttu-id="d8bff-144">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-144">X509</span></span>|<span data-ttu-id="d8bff-145">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-145">X509</span></span>|<span data-ttu-id="d8bff-146">Trasporto</span><span class="sxs-lookup"><span data-stu-id="d8bff-146">Transport</span></span>|  
|<span data-ttu-id="d8bff-147">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-147">KerberosOverTransport</span></span>|<span data-ttu-id="d8bff-148">Windows</span><span class="sxs-lookup"><span data-stu-id="d8bff-148">Windows</span></span>|<span data-ttu-id="d8bff-149">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-149">X509</span></span>|<span data-ttu-id="d8bff-150">Trasporto</span><span class="sxs-lookup"><span data-stu-id="d8bff-150">Transport</span></span>|  
|<span data-ttu-id="d8bff-151">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-151">IssuedTokenOverTransport</span></span>|<span data-ttu-id="d8bff-152">Federativa</span><span class="sxs-lookup"><span data-stu-id="d8bff-152">Federated</span></span>|<span data-ttu-id="d8bff-153">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-153">X509</span></span>|<span data-ttu-id="d8bff-154">Trasporto</span><span class="sxs-lookup"><span data-stu-id="d8bff-154">Transport</span></span>|  
|<span data-ttu-id="d8bff-155">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-155">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="d8bff-156">Windows SSPI, negoziata</span><span class="sxs-lookup"><span data-stu-id="d8bff-156">Windows Sspi Negotiated</span></span>|<span data-ttu-id="d8bff-157">Windows SSPI, negoziata</span><span class="sxs-lookup"><span data-stu-id="d8bff-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="d8bff-158">Trasporto</span><span class="sxs-lookup"><span data-stu-id="d8bff-158">Transport</span></span>|  
|<span data-ttu-id="d8bff-159">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="d8bff-159">AnonymousForCertificate</span></span>|<span data-ttu-id="d8bff-160">None</span><span class="sxs-lookup"><span data-stu-id="d8bff-160">None</span></span>|<span data-ttu-id="d8bff-161">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-161">X509</span></span>|<span data-ttu-id="d8bff-162">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-162">Message</span></span>|  
|<span data-ttu-id="d8bff-163">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="d8bff-163">UserNameForCertificate</span></span>|<span data-ttu-id="d8bff-164">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="d8bff-164">User name/password</span></span>|<span data-ttu-id="d8bff-165">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-165">X509</span></span>|<span data-ttu-id="d8bff-166">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-166">Message</span></span>|  
|<span data-ttu-id="d8bff-167">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="d8bff-167">MutualCertificate</span></span>|<span data-ttu-id="d8bff-168">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-168">X509</span></span>|<span data-ttu-id="d8bff-169">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-169">X509</span></span>|<span data-ttu-id="d8bff-170">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-170">Message</span></span>|  
|<span data-ttu-id="d8bff-171">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="d8bff-171">MutualCertificateDuplex</span></span>|<span data-ttu-id="d8bff-172">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-172">X509</span></span>|<span data-ttu-id="d8bff-173">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-173">X509</span></span>|<span data-ttu-id="d8bff-174">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-174">Message</span></span>|  
|<span data-ttu-id="d8bff-175">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="d8bff-175">IssuedTokenForCertificate</span></span>|<span data-ttu-id="d8bff-176">Federativa</span><span class="sxs-lookup"><span data-stu-id="d8bff-176">Federated</span></span>|<span data-ttu-id="d8bff-177">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-177">X509</span></span>|<span data-ttu-id="d8bff-178">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-178">Message</span></span>|  
|<span data-ttu-id="d8bff-179">Kerberos</span><span class="sxs-lookup"><span data-stu-id="d8bff-179">Kerberos</span></span>|<span data-ttu-id="d8bff-180">Windows</span><span class="sxs-lookup"><span data-stu-id="d8bff-180">Windows</span></span>|<span data-ttu-id="d8bff-181">Windows</span><span class="sxs-lookup"><span data-stu-id="d8bff-181">Windows</span></span>|<span data-ttu-id="d8bff-182">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-182">Message</span></span>|  
|<span data-ttu-id="d8bff-183">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="d8bff-183">IssuedToken</span></span>|<span data-ttu-id="d8bff-184">Federativa</span><span class="sxs-lookup"><span data-stu-id="d8bff-184">Federated</span></span>|<span data-ttu-id="d8bff-185">Federativa</span><span class="sxs-lookup"><span data-stu-id="d8bff-185">Federated</span></span>|<span data-ttu-id="d8bff-186">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-186">Message</span></span>|  
|<span data-ttu-id="d8bff-187">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-187">SspiNegotiated</span></span>|<span data-ttu-id="d8bff-188">Windows SSPI, negoziata</span><span class="sxs-lookup"><span data-stu-id="d8bff-188">Windows Sspi Negotiated</span></span>|<span data-ttu-id="d8bff-189">Windows SSPI, negoziata</span><span class="sxs-lookup"><span data-stu-id="d8bff-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="d8bff-190">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-190">Message</span></span>|  
|<span data-ttu-id="d8bff-191">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-191">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="d8bff-192">None</span><span class="sxs-lookup"><span data-stu-id="d8bff-192">None</span></span>|<span data-ttu-id="d8bff-193">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="d8bff-193">X509, TLS-Nego</span></span>|<span data-ttu-id="d8bff-194">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-194">Message</span></span>|  
|<span data-ttu-id="d8bff-195">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-195">UserNameForSslNegotiated</span></span>|<span data-ttu-id="d8bff-196">Nome utente/password</span><span class="sxs-lookup"><span data-stu-id="d8bff-196">User name/password</span></span>|<span data-ttu-id="d8bff-197">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="d8bff-197">X509, TLS-Nego</span></span>|<span data-ttu-id="d8bff-198">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-198">Message</span></span>|  
|<span data-ttu-id="d8bff-199">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-199">MutualSslNegotiated</span></span>|<span data-ttu-id="d8bff-200">X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-200">X509</span></span>|<span data-ttu-id="d8bff-201">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="d8bff-201">X509, TLS-Nego</span></span>|<span data-ttu-id="d8bff-202">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-202">Message</span></span>|  
|<span data-ttu-id="d8bff-203">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-203">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="d8bff-204">Federativa</span><span class="sxs-lookup"><span data-stu-id="d8bff-204">Federated</span></span>|<span data-ttu-id="d8bff-205">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="d8bff-205">X509, TLS-Nego</span></span>|<span data-ttu-id="d8bff-206">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-206">Message</span></span>|  
  
 <span data-ttu-id="d8bff-207">Gli endpoint che usano queste modalità di autenticazione possono definire i propri requisiti di sicurezza tramite la specifica WS-SP (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="d8bff-207">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="d8bff-208">Questo documento descrive per ogni modalità di autenticazione la struttura delle intestazioni di sicurezza e dei messaggi di infrastruttura e fornisce esempi di criteri e messaggi.</span><span class="sxs-lookup"><span data-stu-id="d8bff-208">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="d8bff-209">WCF si basa su WS-SecureConversation per fornire sessioni protette per proteggere gli scambi di più messaggi tra applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d8bff-209">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="d8bff-210">Per i dettagli di implementazione, vedere la sezione di questo argomento relativa alle sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="d8bff-210">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="d8bff-211">Oltre alle modalità di autenticazione, WCF fornisce le impostazioni per controllare i meccanismi di protezione comuni che si applicano alla maggior parte delle modalità di autenticazione basata su sicurezza messaggio, ad esempio: ordine delle firme e operazioni di crittografia, gruppi di algoritmi, derivazione della chiave e la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="d8bff-211">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="d8bff-212">In questo documento vengono usati i prefissi e gli spazi dei nomi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d8bff-212">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="d8bff-213">Prefisso</span><span class="sxs-lookup"><span data-stu-id="d8bff-213">Prefix</span></span>|<span data-ttu-id="d8bff-214">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d8bff-214">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="d8bff-215">s</span><span class="sxs-lookup"><span data-stu-id="d8bff-215">s</span></span>|<https://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="d8bff-216">sp</span><span class="sxs-lookup"><span data-stu-id="d8bff-216">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="d8bff-217">a</span><span class="sxs-lookup"><span data-stu-id="d8bff-217">a</span></span>|<https://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="d8bff-218">wsse</span><span class="sxs-lookup"><span data-stu-id="d8bff-218">wsse</span></span>|<span data-ttu-id="d8bff-219">TBD: URI di OASIS WSS 1,0</span><span class="sxs-lookup"><span data-stu-id="d8bff-219">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="d8bff-220">wsse11</span><span class="sxs-lookup"><span data-stu-id="d8bff-220">wsse11</span></span>|<span data-ttu-id="d8bff-221">TBD: URI di OASIS WSS 1.1</span><span class="sxs-lookup"><span data-stu-id="d8bff-221">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="d8bff-222">wsu</span><span class="sxs-lookup"><span data-stu-id="d8bff-222">wsu</span></span>|<span data-ttu-id="d8bff-223">TBD: URI dell'utilità di OASIS WSS 1.0</span><span class="sxs-lookup"><span data-stu-id="d8bff-223">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="d8bff-224">ds</span><span class="sxs-lookup"><span data-stu-id="d8bff-224">ds</span></span>|<span data-ttu-id="d8bff-225">TBD: URI di W3C XMLDSig</span><span class="sxs-lookup"><span data-stu-id="d8bff-225">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="d8bff-226">wst</span><span class="sxs-lookup"><span data-stu-id="d8bff-226">wst</span></span>|<span data-ttu-id="d8bff-227">TBD: URI di WS-Trust 2005/02</span><span class="sxs-lookup"><span data-stu-id="d8bff-227">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="d8bff-228">wssc</span><span class="sxs-lookup"><span data-stu-id="d8bff-228">wssc</span></span>|<span data-ttu-id="d8bff-229">TBD: URI di WS-SecureConversation 2005/02</span><span class="sxs-lookup"><span data-stu-id="d8bff-229">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="d8bff-230">wsaw</span><span class="sxs-lookup"><span data-stu-id="d8bff-230">wsaw</span></span>|<span data-ttu-id="d8bff-231">TBD: spazio dei nomi dei criteri di WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="d8bff-231">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="d8bff-232">wsp</span><span class="sxs-lookup"><span data-stu-id="d8bff-232">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="d8bff-233">mssp</span><span class="sxs-lookup"><span data-stu-id="d8bff-233">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="d8bff-234">1. Profili dei token</span><span class="sxs-lookup"><span data-stu-id="d8bff-234">1. Token Profiles</span></span>  
 <span data-ttu-id="d8bff-235">Nelle specifiche di sicurezza dei servizi Web le credenziali sono rappresentate come token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d8bff-235">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="d8bff-236">WCF supporta i tipi di token seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-236">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="d8bff-237">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="d8bff-237">1.1 UsernameToken</span></span>  
 <span data-ttu-id="d8bff-238">WCF segue i profili UsernameToken10 e UsernameToken11 con i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-238">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="d8bff-239">R1101: l'attributo PasswordType dell'elemento UsernameToken\Password deve essere omesso oppure impostato sul valore predefinito, ovvero #PasswordText.</span><span class="sxs-lookup"><span data-stu-id="d8bff-239">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="d8bff-240">È possibile implementare il meccanismo #PasswordDigest usando l'estensibilità.</span><span class="sxs-lookup"><span data-stu-id="d8bff-240">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="d8bff-241">Tale meccanismo di sicurezza tramite password è stato spesso erroneamente considerato come sufficientemente efficiente.</span><span class="sxs-lookup"><span data-stu-id="d8bff-241">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="d8bff-242">Tuttavia, questo meccanismo non può essere usato per sostituire il meccanismo di crittografia dell'elemento UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="d8bff-242">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="d8bff-243">L'obiettivo principale di #PasswordDigest è offrire protezione contro gli attacchi di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="d8bff-243">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="d8bff-244">In modalità di autenticazione WCF rischi di attacchi di riproduzione vengono respinto tramite le firme del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d8bff-244">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="d8bff-245">B1102 WCF genera mai i sottoelementi Nonce e Created dell'elemento UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="d8bff-245">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="d8bff-246">Lo scopo di questi sottoelementi è semplificare l'individuazione degli attacchi di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="d8bff-246">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="d8bff-247">WCF Usa invece le firme del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d8bff-247">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="d8bff-248">La specifica OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) ha introdotto la derivazione della chiave a partire dalla funzionalità di password.</span><span class="sxs-lookup"><span data-stu-id="d8bff-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="d8bff-249">B1103: la password UsernameToken non deve essere usata per la derivazione della chiave e pertanto per le operazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="d8bff-249">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="d8bff-250">Motivo: le password sono in genere considerate troppo vulnerabili per essere usate nelle operazioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="d8bff-250">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="d8bff-251">1.2 Token X509</span><span class="sxs-lookup"><span data-stu-id="d8bff-251">1.2 X509 Token</span></span>  
 <span data-ttu-id="d8bff-252">WCF supporta i certificati X509v3 come tipo di credenziale e segue X509TokenProfile1.0 e X509TokenProfile1.1 con i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-252">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="d8bff-253">R1201: l'attributo ValueType dell'elemento BinarySecurityToken deve essere impostato su #X509v3 quando contiene un certificato X509v3.</span><span class="sxs-lookup"><span data-stu-id="d8bff-253">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="d8bff-254">Le specifiche WSS X509 Token Profile 1.0 e 1.1 definiscono anche #X509PKIPathv1 e #PKCS7 come tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="d8bff-254">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="d8bff-255">WCF non supporta questi tipi.</span><span class="sxs-lookup"><span data-stu-id="d8bff-255">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="d8bff-256">R1202: se un'estensione SKI (SubjectKeyIdentifier) è presente in un certificato X509, per i riferimenti esterni al token occorre usare l'elemento wsse:KeyIdentifier. In particolare, occorre impostare l'attributo ValueType su #X509SubjectKeyIdentifier e il relativo contenuto sul valore con codifica Base64 dell'estensione SKI del certificato.</span><span class="sxs-lookup"><span data-stu-id="d8bff-256">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="d8bff-257">I riferimenti SKI sono un tipo di riferimento esterno molto diffuso e di comprovata interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="d8bff-257">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="d8bff-258">R1203: i riferimenti esterni al token di sicurezza X509 non devono usare l'elemento ds:X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="d8bff-258">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="d8bff-259">R1204: se si usa la specifica X509TokenProfile1.1, i riferimenti esterni al token di sicurezza X509 devono usare l'identificazione personale introdotta dalla specifica WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="d8bff-259">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="d8bff-260">WCF supporta X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="d8bff-260">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="d8bff-261">Esistono tuttavia problemi di interoperabilità con X509IssuerSerial: WCF Usa una stringa per confrontare due valori di X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="d8bff-261">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="d8bff-262">Di conseguenza se riordina i componenti del nome del soggetto e invia a un servizio WCF un riferimento a un certificato, è possibile non venga trovato.</span><span class="sxs-lookup"><span data-stu-id="d8bff-262">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="d8bff-263">1.3 Token Kerberos</span><span class="sxs-lookup"><span data-stu-id="d8bff-263">1.3 Kerberos Token</span></span>  
 <span data-ttu-id="d8bff-264">WCF supporta la specifica KerberosTokenProfile1.1 allo scopo di autenticazione di Windows con i vincoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-264">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="d8bff-265">R1301: come definito in GSS_API e nella specifica di Kerberos, un token Kerberos deve contenere il valore di un elemento Kerberos v4 AP_REQ incapsulato in GSS e il relativo attributo ValueType deve essere impostato su #GSS_Kerberosv5_AP_REQ.</span><span class="sxs-lookup"><span data-stu-id="d8bff-265">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="d8bff-266">WCF Usa GSS incapsulati Kerberos AP-REQ, non un AP-req</span><span class="sxs-lookup"><span data-stu-id="d8bff-266">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="d8bff-267">Si tratta di una procedura di sicurezza consigliata.</span><span class="sxs-lookup"><span data-stu-id="d8bff-267">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="d8bff-268">1.4 Token SAML v1.1</span><span class="sxs-lookup"><span data-stu-id="d8bff-268">1.4 SAML v1.1 Token</span></span>  
 <span data-ttu-id="d8bff-269">WCF supporta i profili specifiche WSS SAML Token 1.0 e 1.1 per token SAML v1.1.</span><span class="sxs-lookup"><span data-stu-id="d8bff-269">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="d8bff-270">È possibile implementare altre versioni di formato di token SAML.</span><span class="sxs-lookup"><span data-stu-id="d8bff-270">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="d8bff-271">1.5 Security Context Token</span><span class="sxs-lookup"><span data-stu-id="d8bff-271">1.5 Security Context Token</span></span>  
 <span data-ttu-id="d8bff-272">WCF supporta la protezione rapida Token (SCT) introdotta nella specifica WS-SecureCoversation.</span><span class="sxs-lookup"><span data-stu-id="d8bff-272">WCF supports the Security Context Token (SCT) introduced in WS-SecureCoversation.</span></span> <span data-ttu-id="d8bff-273">Il protocollo SCT viene usato per rappresentare un contesto di sicurezza definito nella specifica SecureConversation nonché i protocolli di negoziazione binaria TLS e SSPI, descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="d8bff-273">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="d8bff-274">2. Parametri comuni di sicurezza a livello di messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-274">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="d8bff-275">2.1 Timestamp</span><span class="sxs-lookup"><span data-stu-id="d8bff-275">2.1 TimeStamp</span></span>  
 <span data-ttu-id="d8bff-276">La presenza di timestamp è controllata tramite la proprietà <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> della classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="d8bff-276">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="d8bff-277">WCF serializza sempre l'elemento wsse: timestamp con wsse: creati e wsse: scade i campi.</span><span class="sxs-lookup"><span data-stu-id="d8bff-277">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="d8bff-278">Se si usa il meccanismo di firma, l'elemento wsse:TimeStamp viene sempre firmato.</span><span class="sxs-lookup"><span data-stu-id="d8bff-278">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="d8bff-279">2.2 Ordine di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8bff-279">2.2 Protection Order</span></span>  
 <span data-ttu-id="d8bff-280">WCF supporta l'ordine di sicurezza messaggio "Accesso prima di crittografare" e "Encrypt Before Sign" (specifica Security Policy 1.1).</span><span class="sxs-lookup"><span data-stu-id="d8bff-280">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="d8bff-281">"Sign Before Encrypt" è consigliato anche per i motivi seguenti: i messaggi protetti con Encrypt Before Sign sono vulnerabili agli attacchi basati sulla sostituzione delle firme a meno che non venga utilizzato il meccanismo della specifica WS-Security 1.1 SignatureConfirmation e una firma su contenuto crittografato rende le operazioni di controllo più difficili.</span><span class="sxs-lookup"><span data-stu-id="d8bff-281">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="d8bff-282">2.3 Protezione tramite firma</span><span class="sxs-lookup"><span data-stu-id="d8bff-282">2.3 Signature Protection</span></span>  
 <span data-ttu-id="d8bff-283">Quando si usa l'opzione "EncryptBeforeSign" è consigliabile proteggere la firma per impedire attacchi di forza bruta basati sull'esecuzione di tentativi di individuazione del contenuto crittografato o della chiave di firma. Ciò vale specialmente quando un token di un client viene usato con materiali di chiave inadeguati.</span><span class="sxs-lookup"><span data-stu-id="d8bff-283">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="d8bff-284">Gruppo di algoritmi 2.4</span><span class="sxs-lookup"><span data-stu-id="d8bff-284">2.4 Algorithm Suite</span></span>  
 <span data-ttu-id="d8bff-285">WCF supporta tutte le suite di algoritmi elencate nella specifica Security Policy 1.1.</span><span class="sxs-lookup"><span data-stu-id="d8bff-285">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="d8bff-286">2.5 Derivazione della chiave</span><span class="sxs-lookup"><span data-stu-id="d8bff-286">2.5 Key Derivation</span></span>  
 <span data-ttu-id="d8bff-287">WCF Usa "Derivazione delle chiavi simmetriche" come descritto in WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="d8bff-287">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="d8bff-288">2.6 Conferma della firma</span><span class="sxs-lookup"><span data-stu-id="d8bff-288">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="d8bff-289">La conferma della firma può costituire una protezione del set di firme dagli attacchi di tipo middle-man.</span><span class="sxs-lookup"><span data-stu-id="d8bff-289">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="d8bff-290">2.7 Layout di intestazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8bff-290">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="d8bff-291">Ogni modalità di autenticazione descrive un determinato layout per l'intestazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d8bff-291">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="d8bff-292">Gli elementi all'interno dell'intestazione di sicurezza sono parzialmente ordinati.</span><span class="sxs-lookup"><span data-stu-id="d8bff-292">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="d8bff-293">Per definire l'ordine degli elementi figlio dell'intestazione di sicurezza, la specifica WS-Security Policy definisce le modalità di layout di intestazione di sicurezza seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-293">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8bff-294">Strict</span><span class="sxs-lookup"><span data-stu-id="d8bff-294">Strict</span></span>|<span data-ttu-id="d8bff-295">Gli elementi vengono aggiunti all'intestazione di sicurezza in conformità alle regole di numerazione di layout descritte nella sezione 7.7.1 della specifica Security Policy basate sul principio generale secondo cui gli elementi vengono prima dichiarati e poi usati.</span><span class="sxs-lookup"><span data-stu-id="d8bff-295">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="d8bff-296">Lax</span><span class="sxs-lookup"><span data-stu-id="d8bff-296">Lax</span></span>|<span data-ttu-id="d8bff-297">Gli elementi vengono aggiunti all'intestazione di sicurezza in qualsiasi ordine conforme alla specifica WSS: SOAP Message Security.</span><span class="sxs-lookup"><span data-stu-id="d8bff-297">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="d8bff-298">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="d8bff-298">LaxTimestampFirst</span></span>|<span data-ttu-id="d8bff-299">Come Lax, con la differenza che il primo elemento dell'intestazione di sicurezza deve essere un elemento wsse:Timestamp.</span><span class="sxs-lookup"><span data-stu-id="d8bff-299">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="d8bff-300">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="d8bff-300">LaxTimestampLast</span></span>|<span data-ttu-id="d8bff-301">Come Lax, con la differenza che l'ultimo elemento dell'intestazione di sicurezza deve essere un elemento wsse:Timestamp.</span><span class="sxs-lookup"><span data-stu-id="d8bff-301">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="d8bff-302">WCF supporta tutte le quattro modalità per il layout di intestazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d8bff-302">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="d8bff-303">La struttura di intestazione di sicurezza e gli esempi di messaggio delle modalità di autenticazione seguenti usano la modalità "Strict".</span><span class="sxs-lookup"><span data-stu-id="d8bff-303">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="d8bff-304">2. Parametri comuni di sicurezza a livello di messaggio</span><span class="sxs-lookup"><span data-stu-id="d8bff-304">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="d8bff-305">Oltre a fornire criteri di esempio per ogni modalità di autenticazione, questa sezione contiene esempi che mostrano la struttura di intestazione di sicurezza nei messaggi scambiati tra client e servizio.</span><span class="sxs-lookup"><span data-stu-id="d8bff-305">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="d8bff-306">6.1 Protezione a livello di trasporto</span><span class="sxs-lookup"><span data-stu-id="d8bff-306">6.1 Transport Protection</span></span>  
 <span data-ttu-id="d8bff-307">WCF fornisce cinque modalità di autenticazione che usano un trasporto protetto per proteggere i messaggi. UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport e SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="d8bff-307">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="d8bff-308">Queste modalità di autenticazione sono costruite usando l'associazione di trasporto descritta nella specifica SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="d8bff-308">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="d8bff-309">Nella modalità di autenticazione UserNameOverTransport l'elemento UsernameToken viene considerato come un token firmato di supporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-309">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="d8bff-310">Nelle altre modalità di autenticazione il token viene considerato come un token firmato di cui è stata verificata l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="d8bff-310">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="d8bff-311">Il layout di intestazione di sicurezza viene descritto in modo dettagliato nelle appendici C.1.2 e C.1.3 della specifica SecurityPolicy.</span><span class="sxs-lookup"><span data-stu-id="d8bff-311">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="d8bff-312">Negli esempi seguenti di intestazioni di sicurezza viene mostrato il layout Strict per una data modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d8bff-312">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="d8bff-313">Il valore della proprietà "DerivedKeys" dei token è "false" in tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="d8bff-313">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="d8bff-314">I valori delle varie proprietà dell'associazione di trasporto sono:</span><span class="sxs-lookup"><span data-stu-id="d8bff-314">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="d8bff-315">Timestamp: true</span><span class="sxs-lookup"><span data-stu-id="d8bff-315">Timestamp: true</span></span>  
  
 <span data-ttu-id="d8bff-316">Layout di intestazione di sicurezza: Strict</span><span class="sxs-lookup"><span data-stu-id="d8bff-316">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="d8bff-317">Suite di algoritmi: Basic256</span><span class="sxs-lookup"><span data-stu-id="d8bff-317">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="d8bff-318">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-318">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="d8bff-319">In questa modalità di autenticazione il client viene autenticato mediante un elemento UsernameToken che a livello SOAP viene considerato come un token firmato di supporto che viene sempre inviato dall'iniziatore al destinatario.</span><span class="sxs-lookup"><span data-stu-id="d8bff-319">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="d8bff-320">Il servizio viene autenticato tramite un certificato X.509 a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-320">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="d8bff-321">L'associazione usata è un'associazione di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-321">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="d8bff-322">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-322">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />   
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="d8bff-323">Layout di intestazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8bff-323">Security Header Layout</span></span>  
  
 <span data-ttu-id="d8bff-324">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-324">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken ... >  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-325">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-325">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="d8bff-326">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-326">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="d8bff-327">In questa modalità di autenticazione il client viene autenticato mediante un certificato X.509 che a livello SOAP viene considerato come un token di supporto di cui è stata verificata l'autenticità e che viene sempre inviato dall'iniziatore al destinatario.</span><span class="sxs-lookup"><span data-stu-id="d8bff-327">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="d8bff-328">Il servizio viene autenticato tramite un certificato X.509 a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-328">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="d8bff-329">L'associazione usata è un'associazione di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-329">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="d8bff-330">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-330">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />   
              <sp:WssX509V3Token10 />   
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="d8bff-331">Layout di intestazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8bff-331">Security Header Layout</span></span>  
  
 <span data-ttu-id="d8bff-332">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-332">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-333">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-333">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="d8bff-334">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-334">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="d8bff-335">In questa modalità di autenticazione il client, anziché autenticarsi presso il servizio, presenta un token emesso da un servizio token di sicurezza (STS, Security Token Service) e fornisce una prova di possesso di una chiave condivisa.</span><span class="sxs-lookup"><span data-stu-id="d8bff-335">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="d8bff-336">Il token emesso viene considerato a livello SOAP come un token di supporto di cui è stata verificata l'autenticità e che viene sempre inviato dall'iniziatore al destinatario.</span><span class="sxs-lookup"><span data-stu-id="d8bff-336">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="d8bff-337">Il servizio viene autenticato tramite un certificato X.509 a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="d8bff-338">L'associazione è un'associazione di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-338">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="d8bff-339">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-339">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>   
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />   
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="d8bff-340">Layout di intestazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8bff-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="d8bff-341">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-341">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion ...>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-342">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="d8bff-343">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-343">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="d8bff-344">In questa modalità di autenticazione il servizio autentica il client mediante un ticket Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d8bff-344">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="d8bff-345">Il token Kerberos viene considerato a livello SOAP come un token di supporto di cui è stata verificata l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="d8bff-345">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="d8bff-346">Il servizio viene autenticato tramite un certificato X.509 a livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-346">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="d8bff-347">L'associazione è un'associazione di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-347">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="d8bff-348">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-348">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />   
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="d8bff-349">Layout di intestazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8bff-349">Security Header Layout</span></span>  
  
 <span data-ttu-id="d8bff-350">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-350">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-351">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-351">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="d8bff-352">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="d8bff-352">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="d8bff-353">Questa modalità prevede l'uso di un protocollo di negoziazione per eseguire l'autenticazione di client e server.</span><span class="sxs-lookup"><span data-stu-id="d8bff-353">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="d8bff-354">Se possibile, viene usato il protocollo Kerberos. In caso contrario, viene usato il protocollo NTLM.</span><span class="sxs-lookup"><span data-stu-id="d8bff-354">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="d8bff-355">Il token del protocollo SCT così ottenuto viene considerato a livello SOAP come un token di supporto di cui è stata verificata l'autenticità e che viene sempre inviato dall'iniziatore al destinatario.</span><span class="sxs-lookup"><span data-stu-id="d8bff-355">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="d8bff-356">Il servizio viene autenticato ulteriormente a livello di trasporto tramite un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d8bff-356">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="d8bff-357">L'associazione usata è un'associazione di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-357">The binding used is a transport binding.</span></span> <span data-ttu-id="d8bff-358">Il protocollo "SPNEGO" (con negoziazione) descrive il modo WCF Usa il protocollo di negoziazione binaria SSPI con WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="d8bff-358">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="d8bff-359">Gli esempi di intestazione di sicurezza contenuti in questa sezione sono riportati dopo il codice che descrive come il protocollo SCT viene stabilito tramite l'handshake del protocollo SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="d8bff-359">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="d8bff-360">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-360">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />   
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="d8bff-361">Esempi di intestazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d8bff-361">Security Header Examples</span></span>  
 <span data-ttu-id="d8bff-362">Dopo che il protocollo SCT è stato stabilito tramite l'handshake del protocollo SPNEGO usando la negoziazione binaria di WS-Trust, i messaggi dell'applicazione presentano intestazioni di sicurezza aventi la struttura seguente.</span><span class="sxs-lookup"><span data-stu-id="d8bff-362">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="d8bff-363">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-363">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-364">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-364">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="d8bff-365">6.2 Autenticazione del servizio tramite l'uso di certificati X.509</span><span class="sxs-lookup"><span data-stu-id="d8bff-365">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="d8bff-366">Questa sezione descrive le modalità di autenticazione seguenti: MutualCertificate WSS1.0, MutualCertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate e IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="d8bff-366">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="d8bff-367">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="d8bff-367">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="d8bff-368">In questa modalità l'autenticazione del client viene eseguita tramite un certificato X.509 che viene considerato a livello SOAP come token dell'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="d8bff-368">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="d8bff-369">Anche il servizio viene autenticato tramite l'uso di un certificato X.509</span><span class="sxs-lookup"><span data-stu-id="d8bff-369">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="d8bff-370">L'associazione usata è un'associazione asimmetrica con i valori di proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-370">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="d8bff-371">Token dell'iniziatore: certificato X.509 del client, con la modalità di inclusione impostata su ".../IncludeToken/AlwaysToRecipient"</span><span class="sxs-lookup"><span data-stu-id="d8bff-371">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="d8bff-372">Token del destinatario: certificato X.509 del server, con la modalità di inclusione impostata su ".../IncludeToken/Never"</span><span class="sxs-lookup"><span data-stu-id="d8bff-372">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="d8bff-373">Protezione del token: False</span><span class="sxs-lookup"><span data-stu-id="d8bff-373">Token Protection: False</span></span>  
  
 <span data-ttu-id="d8bff-374">Firme di integrità di intestazione e corpo: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-374">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d8bff-375">Ordine di sicurezza: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d8bff-375">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d8bff-376">Crittografia firma: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-376">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d8bff-377">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-377">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-378">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-378">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-379">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-379">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-380">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-380">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-381">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-381">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="d8bff-382">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-382">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-383">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-383">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="d8bff-384">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="d8bff-384">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="d8bff-385">In questa modalità l'autenticazione del client viene eseguita tramite un certificato X.509 che viene considerato a livello SOAP come token dell'iniziatore.</span><span class="sxs-lookup"><span data-stu-id="d8bff-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="d8bff-386">Anche il servizio viene autenticato tramite l'uso di un certificato X.509</span><span class="sxs-lookup"><span data-stu-id="d8bff-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="d8bff-387">L'associazione usata è un'associazione asimmetrica con i valori di proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="d8bff-388">Token dell'iniziatore: certificato X.509 del client, con la modalità di inclusione impostata su ".../IncludeToken/AlwaysToRecipient"</span><span class="sxs-lookup"><span data-stu-id="d8bff-388">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="d8bff-389">Token del destinatario: certificato X.509 del server, con la modalità di inclusione impostata su ".../IncludeToken/AlwaysToInitiator"</span><span class="sxs-lookup"><span data-stu-id="d8bff-389">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="d8bff-390">Protezione del token: False</span><span class="sxs-lookup"><span data-stu-id="d8bff-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="d8bff-391">Firme di integrità di intestazione e corpo: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d8bff-392">Ordine di sicurezza: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d8bff-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d8bff-393">Crittografia firma: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d8bff-394">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-394">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-395">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-396">Richiesta e risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-396">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-397">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-397">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-398">Richiesta e risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-398">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="d8bff-399">6.2.3 Uso di SymmetricBinding con l'autenticazione del servizio tramite un certificato X.509</span><span class="sxs-lookup"><span data-stu-id="d8bff-399">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="d8bff-400">La specifica "WSS10" fornisce un supporto limitato per gli scenari che prevedono token X509.</span><span class="sxs-lookup"><span data-stu-id="d8bff-400">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="d8bff-401">Ad esempio, non esiste alcun modo per proteggere i messaggi tramite un meccanismo di firma o di crittografia usando soltanto un token X509 di servizio.</span><span class="sxs-lookup"><span data-stu-id="d8bff-401">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="d8bff-402">La specifica "WSS11" introduce l'utilizzo di EncryptedKey come token simmetrico.</span><span class="sxs-lookup"><span data-stu-id="d8bff-402">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="d8bff-403">Questa specifica prevede la possibilità di usare una chiave temporanea crittografata relativa al certificato X.509 del servizio che consente di proteggere sia i messaggi di richiesta sia quelli di risposta.</span><span class="sxs-lookup"><span data-stu-id="d8bff-403">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="d8bff-404">Le modalità di autenticazione descritte nella sezione 6.4 di questo argomento usano questo modello.</span><span class="sxs-lookup"><span data-stu-id="d8bff-404">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="d8bff-405">La specifica WS-SecurityPolicy descrive questo modello usando l'associazione SymmetricBinding avente come token di protezione il token X509 di servizio.</span><span class="sxs-lookup"><span data-stu-id="d8bff-405">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="d8bff-406">Le modalità di autenticazione AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 e IssuedTokenForCertificate usano tutte un'istanza simile di sp:SymmetricBinding con i valori di proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-406">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="d8bff-407">Token di protezione: certificato X.509 del server, con la modalità di inclusione impostata su ".../IncludeToken/Never"</span><span class="sxs-lookup"><span data-stu-id="d8bff-407">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="d8bff-408">Protezione del token: False</span><span class="sxs-lookup"><span data-stu-id="d8bff-408">Token Protection: False</span></span>  
  
 <span data-ttu-id="d8bff-409">Firme di integrità di intestazione e corpo: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-409">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d8bff-410">Ordine di sicurezza: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d8bff-410">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d8bff-411">Crittografia firma: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-411">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d8bff-412">Le suddette modalità di autenticazione differiscono fra loro solo per il token di supporto usato.</span><span class="sxs-lookup"><span data-stu-id="d8bff-412">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="d8bff-413">AnonymousForCertificate non prevede alcun token di supporto. MutualCertificate WSS 1.1 prevede il certificato X509 del client come token di supporto di cui è stata verificata l'autenticità. UserNameForCertificate prevede un elemento UserNameToken come token firmato di supporto e IssuedTokenForCertificate prevede il token emesso come token di supporto di cui è stata verificata l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="d8bff-413">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="d8bff-414">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-414">Policy</span></span>  
  
 <span data-ttu-id="d8bff-415">Associazione SymmetricBinding</span><span class="sxs-lookup"><span data-stu-id="d8bff-415">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireThumbprintReference />   
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
          <sp:RequireSignatureConfirmation />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="d8bff-416">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="d8bff-416">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="d8bff-417">In questa modalità di autenticazione il client è anonimo e il servizio viene autenticato usando un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d8bff-417">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d8bff-418">L'associazione usata è un'istanza di associazione simmetrica, come descritto nella sezione 6.4.2.</span><span class="sxs-lookup"><span data-stu-id="d8bff-418">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="d8bff-419">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-419">Policy</span></span>  
  
 <span data-ttu-id="d8bff-420">Per informazioni dettagliate sull'associazione, vedere il paragrafo "Criterio" della sezione 6.2.3 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8bff-420">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-421">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-422">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-422">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-423">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-423">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-424">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-424">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-425">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-425">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-426">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-426">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="d8bff-427">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="d8bff-427">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="d8bff-428">In questa modalità il servizio autentica il client mediante un UsernameToken che a livello SOAP viene considerato come un token firmato di supporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-428">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="d8bff-429">Il client autentica il servizio tramite un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d8bff-429">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="d8bff-430">L'associazione usata è un'associazione simmetrica in cui il token di protezione è una chiave generata dal client e crittografata tramite la chiave pubblica del servizio.</span><span class="sxs-lookup"><span data-stu-id="d8bff-430">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="d8bff-431">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-431">Policy</span></span>  
  
 <span data-ttu-id="d8bff-432">Per informazioni dettagliate sull'associazione, vedere il paragrafo "Criterio" della sezione 6.2.3 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8bff-432">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="d8bff-433">Token firmato di supporto</span><span class="sxs-lookup"><span data-stu-id="d8bff-433">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-434">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-434">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-435">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-435">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-436">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-436">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-437">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-437">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-438">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-438">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-439">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-439">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="d8bff-440">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="d8bff-440">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="d8bff-441">In questa modalità l'autenticazione del client viene eseguita tramite un certificato X.509 che viene considerato a livello SOAP come un token di supporto di cui è stata verificata l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="d8bff-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="d8bff-442">Anche il servizio viene autenticato tramite l'uso di un certificato X.509</span><span class="sxs-lookup"><span data-stu-id="d8bff-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d8bff-443">L'associazione usata è un'associazione simmetrica in cui il token di protezione è una chiave generata dal client e crittografata tramite la chiave pubblica del servizio.</span><span class="sxs-lookup"><span data-stu-id="d8bff-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="d8bff-444">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-444">Policy</span></span>  
  
 <span data-ttu-id="d8bff-445">Per informazioni dettagliate sull'associazione, vedere il paragrafo "Criterio" della sezione 6.2.3 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8bff-445">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="d8bff-446">Token di supporto di cui è stata verificata l'autenticità</span><span class="sxs-lookup"><span data-stu-id="d8bff-446">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-447">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-447">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-448">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-448">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-449">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-449">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-450">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-450">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-451">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-451">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-452">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-452">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="d8bff-453">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="d8bff-453">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="d8bff-454">In questa modalità di autenticazione il client, anziché autenticarsi presso il servizio, presenta un token emesso da un servizio STS e fornisce una prova di possesso di una chiave condivisa.</span><span class="sxs-lookup"><span data-stu-id="d8bff-454">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="d8bff-455">Il token emesso viene considerato a livello SOAP come un token di supporto di cui è stata verificata l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="d8bff-455">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="d8bff-456">Il client autentica il servizio tramite un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d8bff-456">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="d8bff-457">L'associazione usata è un'associazione simmetrica in cui il token di protezione è una chiave generata dal client e crittografata tramite la chiave pubblica del servizio.</span><span class="sxs-lookup"><span data-stu-id="d8bff-457">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="d8bff-458">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-458">Policy</span></span>  
  
 <span data-ttu-id="d8bff-459">Per informazioni dettagliate sull'associazione, vedere il paragrafo "Criterio" della sezione 6.2.3 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8bff-459">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="d8bff-460">Token di supporto di cui è stata verificata l'autenticità</span><span class="sxs-lookup"><span data-stu-id="d8bff-460">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />   
       <sp:RequireInternalReference />   
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-461">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-461">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-462">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-462">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-463">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-463">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-464">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-464">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-465">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-465">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-466">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-466">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="d8bff-467">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="d8bff-467">6.3 Kerberos</span></span>  
 <span data-ttu-id="d8bff-468">In questa modalità di autenticazione il servizio autentica il client mediante un ticket Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d8bff-468">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="d8bff-469">Questo stesso ticket viene inoltre usato per autenticare il server.</span><span class="sxs-lookup"><span data-stu-id="d8bff-469">That same ticket also provides server authentication.</span></span> <span data-ttu-id="d8bff-470">L'associazione usata è un'associazione simmetrica avente le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-470">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="d8bff-471">Token di protezione: ticket Kerberos, con la modalità di inclusione impostata su ".../IncludeToken/Once"</span><span class="sxs-lookup"><span data-stu-id="d8bff-471">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="d8bff-472">Protezione del token: False</span><span class="sxs-lookup"><span data-stu-id="d8bff-472">Token Protection: False</span></span>  
  
 <span data-ttu-id="d8bff-473">Firme di integrità di intestazione e corpo: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-473">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d8bff-474">Ordine di sicurezza: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d8bff-474">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d8bff-475">Crittografia firma: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-475">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d8bff-476">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-476">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:WssGssKerberosV5ApReqToken11 />   
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-477">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-477">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-478">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-478">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-479">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-479">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-480">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-480">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-481">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-481">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-482">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-482">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="d8bff-483">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="d8bff-483">6.4 IssuedToken</span></span>  
 <span data-ttu-id="d8bff-484">In questa modalità di autenticazione il client, anziché autenticarsi presso il servizio, presenta un token emesso da un servizio STS e fornisce una prova di possesso di una chiave condivisa.</span><span class="sxs-lookup"><span data-stu-id="d8bff-484">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="d8bff-485">Inoltre, anziché prevedere l'autenticazione del servizio presso il client, questa modalità ricorre al meccanismo seguente: il servizio STS esegue la crittografia della chiave condivisa come parte del token emesso in modo che solo il servizio possa decifrare la chiave.</span><span class="sxs-lookup"><span data-stu-id="d8bff-485">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="d8bff-486">L'associazione usata è un'associazione simmetrica avente le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-486">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="d8bff-487">Token di protezione: token emesso, con la modalità di inclusione impostata su ".../IncludeToken/AlwaysToRecipient"</span><span class="sxs-lookup"><span data-stu-id="d8bff-487">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="d8bff-488">Protezione del token: False</span><span class="sxs-lookup"><span data-stu-id="d8bff-488">Token Protection: False</span></span>  
  
 <span data-ttu-id="d8bff-489">Firme di integrità di intestazione e corpo: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-489">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d8bff-490">Ordine di sicurezza: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d8bff-490">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d8bff-491">Crittografia firma: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-491">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d8bff-492">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-492">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>   
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireInternalReference />   
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-493">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-493">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-494">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-494">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-495">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-495">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-496">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-496">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-497">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-497">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-498">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-498">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="d8bff-499">6.5 Autenticazione del servizio tramite SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-499">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="d8bff-500">Questa sezione descrive un gruppo di modalità di autenticazione che usano un'associazione simmetrica in cui il token di protezione è un token del protocollo SCT conforme alla specifica WS-SC (WS-SecureConversation) il cui valore di chiave viene negoziato eseguendo il protocollo TLS su messaggi di RST/RSTR di WS-T (WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="d8bff-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="d8bff-501">I dettagli relativi all'implementazione dell'handshake del protocollo TLS basato su WS-T sono descritti nella specifica TLSNEGO.</span><span class="sxs-lookup"><span data-stu-id="d8bff-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="d8bff-502">Negli esempi di messaggio seguenti si presuppone che il protocollo SCT e un contesto di sicurezza associato siano già stati stabiliti tramite un handshake.</span><span class="sxs-lookup"><span data-stu-id="d8bff-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="d8bff-503">L'associazione usata è un'associazione simmetrica avente le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="d8bff-504">Token di protezione: SslContextToken, con la modalità di inclusione impostata su ".../IncludeToken/Never"</span><span class="sxs-lookup"><span data-stu-id="d8bff-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="d8bff-505">Protezione del token: False</span><span class="sxs-lookup"><span data-stu-id="d8bff-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="d8bff-506">Firme di integrità di intestazione e corpo: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d8bff-507">Ordine di sicurezza: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d8bff-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d8bff-508">Crittografia firma: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-508">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="d8bff-509">6.5.1 Criterio dell'autenticazione del servizio tramite SslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-509">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="d8bff-510">Tutte le modalità di autenticazione descritte in questa sezione presentano criteri simili che differiscono solo per il tipo specifico di token usato, che può essere un token firmato di supporto oppure un token firmato di cui è stata verificata l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="d8bff-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' />  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>   
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="d8bff-511">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-511">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="d8bff-512">In questa modalità di autenticazione il client è anonimo e il servizio viene autenticato usando un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d8bff-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d8bff-513">L'associazione usata è un'istanza di associazione simmetrica, come descritto nella sezione 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="d8bff-513">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="d8bff-514">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-514">Policy</span></span>  
  
 <span data-ttu-id="d8bff-515">Per informazioni dettagliate sull'associazione, vedere il paragrafo "Criterio" della sezione 6.5.1 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8bff-515">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-516">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-516">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-517">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-517">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-518">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-518">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-519">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-519">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-520">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-520">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-521">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-521">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="d8bff-522">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-522">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="d8bff-523">In questa modalità il client viene autenticato mediante un UsernameToken che a livello SOAP viene considerato come un token firmato di supporto.</span><span class="sxs-lookup"><span data-stu-id="d8bff-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="d8bff-524">Il servizio viene autenticato tramite l'uso di un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d8bff-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d8bff-525">L'associazione usata è un'istanza di associazione simmetrica, come descritto nella sezione 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="d8bff-525">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="d8bff-526">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-526">Policy</span></span>  
  
 <span data-ttu-id="d8bff-527">Per informazioni dettagliate sull'associazione, vedere la sezione 6.5.1 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8bff-527">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="d8bff-528">Token firmato di supporto</span><span class="sxs-lookup"><span data-stu-id="d8bff-528">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-529">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-529">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-530">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-530">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-531">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-531">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-532">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-532">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-533">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-533">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-534">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-534">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="d8bff-535">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-535">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="d8bff-536">In questa modalità di autenticazione il client, anziché autenticarsi presso il servizio, presenta un token emesso da un servizio STS e fornisce una prova di possesso di una chiave condivisa.</span><span class="sxs-lookup"><span data-stu-id="d8bff-536">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="d8bff-537">Il token emesso viene considerato a livello SOAP come un token di supporto di cui è stata verificata l'autenticità.</span><span class="sxs-lookup"><span data-stu-id="d8bff-537">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="d8bff-538">Il servizio viene autenticato tramite l'uso di un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d8bff-538">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="d8bff-539">L'associazione usata è un'istanza di associazione simmetrica, come descritto nella sezione 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="d8bff-539">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="d8bff-540">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-540">Policy</span></span>  
  
 <span data-ttu-id="d8bff-541">Per informazioni dettagliate sull'associazione, vedere la sezione 6.5.1 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8bff-541">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="d8bff-542">Token di supporto di cui è stata verificata l'autenticità</span><span class="sxs-lookup"><span data-stu-id="d8bff-542">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>   
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />   
        <sp:RequireInternalReference />   
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-543">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-543">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-544">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-544">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-545">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-545">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-546">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-546">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-547">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-547">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-548">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-548">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="d8bff-549">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-549">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="d8bff-550">In questa modalità l'autenticazione del client e del servizio si basa sull'utilizzo di certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="d8bff-550">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="d8bff-551">L'associazione usata è un'istanza di associazione simmetrica, come descritto nella sezione 6.5.1.</span><span class="sxs-lookup"><span data-stu-id="d8bff-551">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="d8bff-552">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-552">Policy</span></span>  
  
 <span data-ttu-id="d8bff-553">Per informazioni dettagliate sull'associazione, vedere la sezione 6.5.1 di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d8bff-553">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="d8bff-554">Token di supporto di cui è stata verificata l'autenticità</span><span class="sxs-lookup"><span data-stu-id="d8bff-554">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-555">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-555">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-556">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-556">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-557">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-557">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-558">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-558">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-559">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-559">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-560">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-560">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="d8bff-561">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="d8bff-561">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="d8bff-562">Questa modalità di autenticazione prevede l'uso di un protocollo di negoziazione per eseguire l'autenticazione di client e server.</span><span class="sxs-lookup"><span data-stu-id="d8bff-562">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="d8bff-563">Se possibile, viene usato il protocollo Kerberos. In caso contrario, viene usato il protocollo NTLM.</span><span class="sxs-lookup"><span data-stu-id="d8bff-563">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="d8bff-564">L'associazione usata è un'associazione simmetrica avente le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8bff-564">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="d8bff-565">Token di protezione: SpnegoContextToken, con la modalità di inclusione impostata su ".../IncludeToken/AlwaysToRecipient"</span><span class="sxs-lookup"><span data-stu-id="d8bff-565">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="d8bff-566">Protezione del token: False</span><span class="sxs-lookup"><span data-stu-id="d8bff-566">Token Protection: False</span></span>  
  
 <span data-ttu-id="d8bff-567">Firme di integrità di intestazione e corpo: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-567">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="d8bff-568">Ordine di sicurezza: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="d8bff-568">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="d8bff-569">Crittografia firma: True</span><span class="sxs-lookup"><span data-stu-id="d8bff-569">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="d8bff-570">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-570">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-571">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-571">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-572">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-572">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-573">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-573">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-574">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-574">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-575">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-575">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-576">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-576">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="d8bff-577">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="d8bff-577">6.7 SecureConversation</span></span>  
 <span data-ttu-id="d8bff-578">L'associazione usata è un'associazione simmetrica in cui il token di protezione è un token del protocollo SCT conforme alla specifica WS-SC (WS-SecureConversation).</span><span class="sxs-lookup"><span data-stu-id="d8bff-578">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="d8bff-579">Il protocollo SCT viene negoziato tramite WS-T oppure WS-SC in base a un'associazione annidata, la quale è essa stessa un'associazione simmetrica che usa un protocollo di negoziazione.</span><span class="sxs-lookup"><span data-stu-id="d8bff-579">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="d8bff-580">Il protocollo di negoziazione si basa su Kerberos per eseguire l'autenticazione di client e server, se possibile.</span><span class="sxs-lookup"><span data-stu-id="d8bff-580">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="d8bff-581">In caso contrario, ricorre al protocollo NTLM.</span><span class="sxs-lookup"><span data-stu-id="d8bff-581">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="d8bff-582">criteri</span><span class="sxs-lookup"><span data-stu-id="d8bff-582">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />   
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />   
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />   
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />   
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />   
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />   
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />   
                          <sp:EncryptSignature />   
                          <sp:OnlySignEntireHeadersAndBody />   
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />   
                          <sp:MustSupportRefIssuerSerial />   
                          <sp:MustSupportRefThumbprint />   
                          <sp:MustSupportRefEncryptedKey />   
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />   
                          <sp:RequireClientEntropy />   
                          <sp:RequireServerEntropy />   
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="d8bff-583">Esempi di intestazione di sicurezza: SignBeforeEncrypt e EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="d8bff-583">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="d8bff-584">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-584">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-585">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-585">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="d8bff-586">Esempi di intestazione di sicurezza: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="d8bff-586">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="d8bff-587">Richiesta</span><span class="sxs-lookup"><span data-stu-id="d8bff-587">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="d8bff-588">Risposta</span><span class="sxs-lookup"><span data-stu-id="d8bff-588">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
