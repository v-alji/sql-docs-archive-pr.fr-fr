---
title: Éditeur du gestionnaire de connexions HTTP (page proxy) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.proxy.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: e831a830-49a3-49c5-8a31-9731fc4fd12e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f8269dbbeb226ffa3f56c226e1a416d99c1e3f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601578"
---
# <a name="http-connection-manager-editor-proxy-page"></a><span data-ttu-id="bdad3-102">Éditeur du gestionnaire de connexions HTTP (page Proxy)</span><span class="sxs-lookup"><span data-stu-id="bdad3-102">HTTP Connection Manager Editor (Proxy Page)</span></span>
  <span data-ttu-id="bdad3-103">Utilisez l'onglet **Proxy** de la boîte de dialogue **Éditeur du gestionnaire de connexions HTTP** pour configurer le gestionnaire de connexions HTTP afin d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="bdad3-103">Use the **Proxy** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager to use a proxy server.</span></span> <span data-ttu-id="bdad3-104">Une connexion HTTP permet à un package d'accéder à un serveur Web via HTTP pour l'envoi et la réception de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bdad3-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span>  
  
 <span data-ttu-id="bdad3-105">Pour en savoir plus sur le gestionnaire de connexions HTTP, consultez [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="bdad3-105">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="bdad3-106">Pour en savoir plus sur un scénario d'utilisation courante pour le gestionnaire de connexions HTTP, consultez [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="bdad3-106">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bdad3-107">Options</span><span class="sxs-lookup"><span data-stu-id="bdad3-107">Options</span></span>  
 <span data-ttu-id="bdad3-108">**Utiliser le proxy**</span><span class="sxs-lookup"><span data-stu-id="bdad3-108">**Use proxy**</span></span>  
 <span data-ttu-id="bdad3-109">Indiquez si vous voulez que le gestionnaire de connexions HTTP se connecte via un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="bdad3-109">Specify whether you want the HTTP Connection Manager to connect through a proxy server.</span></span>  
  
 <span data-ttu-id="bdad3-110">**URL du proxy**</span><span class="sxs-lookup"><span data-stu-id="bdad3-110">**Proxy URL**</span></span>  
 <span data-ttu-id="bdad3-111">Tapez l'URL du serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="bdad3-111">Type the URL for the proxy server.</span></span>  
  
 <span data-ttu-id="bdad3-112">**Ne pas utiliser de proxy en local**</span><span class="sxs-lookup"><span data-stu-id="bdad3-112">**Bypass proxy on local**</span></span>  
 <span data-ttu-id="bdad3-113">Indiquez si vous voulez que le gestionnaire de connexions HTTP contourne le serveur proxy pour les adresses locales.</span><span class="sxs-lookup"><span data-stu-id="bdad3-113">Specify whether you want the HTTP Connection Manager to bypass the proxy server for local addresses.</span></span>  
  
 <span data-ttu-id="bdad3-114">**Utiliser les informations d'identification**</span><span class="sxs-lookup"><span data-stu-id="bdad3-114">**Use credentials**</span></span>  
 <span data-ttu-id="bdad3-115">Indiquez si vous voulez que le gestionnaire de connexions HTTP utilise les informations d'identification de sécurité pour le serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="bdad3-115">Specify whether you want the HTTP Connection Manager to use security credentials for the proxy server.</span></span>  
  
 <span data-ttu-id="bdad3-116">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="bdad3-116">**User name**</span></span>  
 <span data-ttu-id="bdad3-117">Si le gestionnaire de connexions HTTP utilise des informations d'identification, vous devez spécifier un nom d'utilisateur, un mot de passe et un domaine.</span><span class="sxs-lookup"><span data-stu-id="bdad3-117">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="bdad3-118">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="bdad3-118">**Password**</span></span>  
 <span data-ttu-id="bdad3-119">Si le gestionnaire de connexions HTTP utilise des informations d'identification, vous devez spécifier un nom d'utilisateur, un mot de passe et un domaine.</span><span class="sxs-lookup"><span data-stu-id="bdad3-119">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="bdad3-120">**Domaine**</span><span class="sxs-lookup"><span data-stu-id="bdad3-120">**Domain**</span></span>  
 <span data-ttu-id="bdad3-121">Si le gestionnaire de connexions HTTP utilise des informations d'identification, vous devez spécifier un nom d'utilisateur, un mot de passe et un domaine.</span><span class="sxs-lookup"><span data-stu-id="bdad3-121">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="bdad3-122">**Liste de contournement proxy**</span><span class="sxs-lookup"><span data-stu-id="bdad3-122">**Proxy bypass list**</span></span>  
 <span data-ttu-id="bdad3-123">Liste d'adresses pour lesquelles vous ne souhaitez pas utiliser le serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="bdad3-123">The list of addresses for which  you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="bdad3-124">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="bdad3-124">**Add**</span></span>  
 <span data-ttu-id="bdad3-125">Tapez une adresse pour laquelle vous souhaitez que le gestionnaire de connexions HTTP n'utilise pas le serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="bdad3-125">Type an address for which you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="bdad3-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="bdad3-126">**Remove**</span></span>  
 <span data-ttu-id="bdad3-127">Sélectionnez une adresse, puis supprimez-la en cliquant sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="bdad3-127">Select an address, and then remove it by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdad3-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bdad3-128">See Also</span></span>  
 <span data-ttu-id="bdad3-129">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bdad3-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="bdad3-130">Éditeur du gestionnaire de connexions HTTP &#40;page Serveur&#41;</span><span class="sxs-lookup"><span data-stu-id="bdad3-130">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-server-page.md)  
  
  
