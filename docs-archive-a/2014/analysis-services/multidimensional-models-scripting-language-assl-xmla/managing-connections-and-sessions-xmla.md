---
title: Gestion des connexions et des sessions (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- statefulness [XML for Analysis]
- statelessness [XML for Analysis]
- XML for Analysis, sessions
- states [XML for Analysis]
- XMLA, sessions
- sessions [XML for Analysis]
ms.assetid: b83bb3ff-09be-4fda-9d1d-6248e04ffb21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bfe876f6874193fd0885f16d91caa9f6fe8b172
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604218"
---
# <a name="managing-connections-and-sessions-xmla"></a><span data-ttu-id="7583e-102">Gestion des connexions et des sessions (XMLA)</span><span class="sxs-lookup"><span data-stu-id="7583e-102">Managing Connections and Sessions (XMLA)</span></span>
  <span data-ttu-id="7583e-103">*Conservation* est une condition au cours de laquelle le serveur conserve l’identité et le contexte d’un client entre les appels de méthode.</span><span class="sxs-lookup"><span data-stu-id="7583e-103">*Statefulness* is a condition during which the server preserves the identity and context of a client between method calls.</span></span> <span data-ttu-id="7583e-104">*Abandon* est une condition au cours de laquelle le serveur ne se souvient pas de l’identité et du contexte d’un client après la fin d’un appel de méthode.</span><span class="sxs-lookup"><span data-stu-id="7583e-104">*Statelessness* is a condition during which the server does not remember the identity and context of a client after a method call finishes.</span></span>  
  
 <span data-ttu-id="7583e-105">Pour fournir à conservation, XML for Analysis (XMLA) prend en charge des *sessions* qui autorisent l’exécution conjointe d’une série d’instructions.</span><span class="sxs-lookup"><span data-stu-id="7583e-105">To provide statefulness, XML for Analysis (XMLA) supports *sessions* that allow a series of statements to be performed together.</span></span> <span data-ttu-id="7583e-106">À titre d'exemple, une telle série d'instructions pourrait servir à créer le membre calculé à utiliser dans des requêtes ultérieures.</span><span class="sxs-lookup"><span data-stu-id="7583e-106">An example of such a series of statements would be the creation of a calculated member that is to be used in subsequent queries.</span></span>  
  
 <span data-ttu-id="7583e-107">En général, les sessions XMLA suivent le comportement suivant énoncé par la spécification OLE DB 2.6 :</span><span class="sxs-lookup"><span data-stu-id="7583e-107">In general, sessions in XMLA follow the following behavior outlined by the OLE DB 2.6 specification:</span></span>  
  
-   <span data-ttu-id="7583e-108">Les sessions définissent l'étendue contextuelle des transactions et des commandes.</span><span class="sxs-lookup"><span data-stu-id="7583e-108">Sessions define transaction and command context scope.</span></span>  
  
-   <span data-ttu-id="7583e-109">Plusieurs commandes peuvent être exécutées dans le contexte d'une seule session.</span><span class="sxs-lookup"><span data-stu-id="7583e-109">Multiple commands can be run in the context of a single session.</span></span>  
  
-   <span data-ttu-id="7583e-110">La prise en charge des transactions dans le contexte XMLA s’effectue via des commandes spécifiques au fournisseur envoyées avec la méthode [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="7583e-110">Support for transactions in the XMLA context is through provider-specific commands sent with the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
 <span data-ttu-id="7583e-111">XMLA définit une méthode de prise en charge des sessions dans un environnement Web selon un mode comparable à la méthode employée par le protocole DAV (Distributed Authoring and Versioning) pour implémenter le verrouillage dans un environnement faiblement couplé.</span><span class="sxs-lookup"><span data-stu-id="7583e-111">XMLA defines a way to support sessions in a Web environment in a mode similar to the approach used by the Distributed Authoring and Versioning (DAV) protocol to implement locking in a loosely coupled environment.</span></span> <span data-ttu-id="7583e-112">Cette implémentation va de pair avec DAV en ce sens que le fournisseur est autorisé à faire expirer les sessions pour divers motifs (par exemple, dépassement de délai ou erreur de connexion).</span><span class="sxs-lookup"><span data-stu-id="7583e-112">This implementation parallels DAV in that the provider is allowed to expire sessions for various reasons (for example, a timeout or connection error).</span></span> <span data-ttu-id="7583e-113">Lorsque les sessions sont prises en charge, les services Web doivent être en mesure de gérer des jeux de commandes interrompus qui doivent être redémarrés.</span><span class="sxs-lookup"><span data-stu-id="7583e-113">When sessions are supported, Web services must be aware and ready to handle interrupted sets of commands that must be restarted.</span></span>  
  
 <span data-ttu-id="7583e-114">La spécification SOAP (Simple Object Access Protocol) du W3C (World Wide Web Consortium) recommande d'utiliser des en-têtes SOAP pour développer de nouveaux protocoles sur les messages SOAP.</span><span class="sxs-lookup"><span data-stu-id="7583e-114">The World Wide Web Consortium (W3C) Simple Object Access Protocol (SOAP) specification recommends using SOAP headers for building up new protocols on top of SOAP messages.</span></span> <span data-ttu-id="7583e-115">Le tableau suivant énumère les éléments et les attributs d'en-tête SOAP que XMLA définit pour initialiser, maintenir et fermer une session.</span><span class="sxs-lookup"><span data-stu-id="7583e-115">The following table lists the SOAP header elements and attributes that XMLA defines for initiating, maintaining, and closing a session.</span></span>  
  
|<span data-ttu-id="7583e-116">En-tête SOAP</span><span class="sxs-lookup"><span data-stu-id="7583e-116">SOAP header</span></span>|<span data-ttu-id="7583e-117">Description</span><span class="sxs-lookup"><span data-stu-id="7583e-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7583e-118">BeginSession</span><span class="sxs-lookup"><span data-stu-id="7583e-118">BeginSession</span></span>|<span data-ttu-id="7583e-119">Cet en-tête demande au fournisseur de créer une nouvelle session.</span><span class="sxs-lookup"><span data-stu-id="7583e-119">This header requests the provider to create a new session.</span></span> <span data-ttu-id="7583e-120">Le fournisseur doit répondre en construisant une nouvelle session et en retournant l'ID de session dans l'en-tête Session de la réponse SOAP.</span><span class="sxs-lookup"><span data-stu-id="7583e-120">The provider should respond by constructing a new session and returning the session ID as part of the Session header in the SOAP response.</span></span>|  
|<span data-ttu-id="7583e-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="7583e-121">SessionId</span></span>|<span data-ttu-id="7583e-122">La zone des valeurs contient l'ID de session qui doit être utilisé dans chaque appel de méthode pour le reste de la session.</span><span class="sxs-lookup"><span data-stu-id="7583e-122">The value area contains the session ID that must be used in each method call for the rest of the session.</span></span> <span data-ttu-id="7583e-123">Le fournisseur spécifié dans la réponse SOAP envoie cette balise et le client doit également envoyer cet attribut avec chaque élément d'en-tête Session.</span><span class="sxs-lookup"><span data-stu-id="7583e-123">The provider in the SOAP response sends this tag and the client must also send this attribute with each Session header element.</span></span>|  
|<span data-ttu-id="7583e-124">session</span><span class="sxs-lookup"><span data-stu-id="7583e-124">Session</span></span>|<span data-ttu-id="7583e-125">Pour chaque appel de méthode qui se produit dans la session, cet en-tête doit être utilisé, et l'ID de session doit être inclus dans la zone des valeurs de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="7583e-125">For every method call that occurs in the session, this header must be used, and the session ID must be included in the value area of the header.</span></span>|  
|<span data-ttu-id="7583e-126">EndSession</span><span class="sxs-lookup"><span data-stu-id="7583e-126">EndSession</span></span>|<span data-ttu-id="7583e-127">Pour mettre fin à la session, utilisez cet en-tête.</span><span class="sxs-lookup"><span data-stu-id="7583e-127">To terminate the session, use this header.</span></span> <span data-ttu-id="7583e-128">L'ID de session doit être inclus avec la zone des valeurs.</span><span class="sxs-lookup"><span data-stu-id="7583e-128">The session ID must be included with the value area.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="7583e-129">Un ID de session ne garantit pas qu'une session reste valide.</span><span class="sxs-lookup"><span data-stu-id="7583e-129">A session ID does not guarantee that a session stays valid.</span></span> <span data-ttu-id="7583e-130">Si la session expire (par exemple, en cas de dépassement de délai ou de perte de la connexion), le fournisseur peut choisir de terminer et d'annuler les actions de cette session.</span><span class="sxs-lookup"><span data-stu-id="7583e-130">If the session expires (for example, if it times out or the connection is lost), the provider can choose to end and roll back that session's actions.</span></span> <span data-ttu-id="7583e-131">En conséquence, tous les appels de méthode suivants émanant du client sur un ID de session échouent avec une erreur signalant la non validité d'une session.</span><span class="sxs-lookup"><span data-stu-id="7583e-131">As a result, all subsequent method calls from the client on a session ID fail with an error signaling a session that is not valid.</span></span> <span data-ttu-id="7583e-132">Un client doit gérer cette condition et être en mesure de renvoyer les appels de méthode de session depuis le début.</span><span class="sxs-lookup"><span data-stu-id="7583e-132">A client should handle this condition and be prepared to resend the session method calls from the beginning.</span></span>  
  
## <a name="legacy-code-example"></a><span data-ttu-id="7583e-133">Exemple de code existant</span><span class="sxs-lookup"><span data-stu-id="7583e-133">Legacy Code Example</span></span>  
 <span data-ttu-id="7583e-134">L'exemple suivant illustre la façon dont les sessions sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="7583e-134">The following example shows how sessions are supported.</span></span>  
  
1.  <span data-ttu-id="7583e-135">Pour commencer la session, ajoutez un en-tête SOAP BeginSession à l'appel de méthode XMLA sortant du client.</span><span class="sxs-lookup"><span data-stu-id="7583e-135">To begin the session, add a BeginSession header in SOAP to the outbound XMLA method call from the client.</span></span> <span data-ttu-id="7583e-136">Au départ, l'ID de session n'étant pas encore connu, la zone des valeurs est vide.</span><span class="sxs-lookup"><span data-stu-id="7583e-136">The value area is initially blank because the session ID is not yet known.</span></span>  
  
    ```  
    <SOAP-ENV:Envelope  
       xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
       SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
       <SOAP-ENV:Header>  
          <XA:BeginSession  
             xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
             xsi:type="xsd:int"  
             mustUnderstand="1"/>  
       </SOAP-ENV:Header>  
       <SOAP-ENV:Body>  
          ...<!-- Discover or Execute call goes here.-->  
       </SOAP-ENV:Body>  
    </SOAP-ENV:Envelope>  
    ```  
  
2.  <span data-ttu-id="7583e-137">Le message de réponse SOAP du fournisseur comprend l’ID de session dans la zone d’en-tête de retour, à l’aide de la balise d’en-tête XMLA \<SessionId> .</span><span class="sxs-lookup"><span data-stu-id="7583e-137">The SOAP response message from the provider includes the session ID in the return header area, using the XMLA header tag \<SessionId>.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
3.  <span data-ttu-id="7583e-138">Pour chaque appel de méthode intervenant au cours de la session, l'en-tête Session doit être ajouté et contenir l'ID de session retourné par le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="7583e-138">For each method call in the session, the Session header must be added, containing the session ID returned from the provider.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
4.  <span data-ttu-id="7583e-139">Une fois la session terminée, la \<EndSession> balise est utilisée, contenant la valeur d’ID de session associée.</span><span class="sxs-lookup"><span data-stu-id="7583e-139">When the session is complete, the \<EndSession> tag is used, containing the related session ID value.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:EndSession  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          xsi:type="xsd:int"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7583e-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7583e-140">See Also</span></span>  
 [<span data-ttu-id="7583e-141">Développement avec XMLA dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7583e-141">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
