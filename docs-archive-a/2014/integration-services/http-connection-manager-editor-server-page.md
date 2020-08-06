---
title: Éditeur du gestionnaire de connexions HTTP (page serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.server.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: 774778a0-ece6-4971-b93f-b121d8fc1fc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2349766b11b28ff258496dc966d554d49c7657b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601573"
---
# <a name="http-connection-manager-editor-server-page"></a><span data-ttu-id="ea75a-102">Éditeur du gestionnaire de connexions HTTP (page Serveur)</span><span class="sxs-lookup"><span data-stu-id="ea75a-102">HTTP Connection Manager Editor (Server Page)</span></span>
  <span data-ttu-id="ea75a-103">Utilisez l'onglet **Serveur** de la boîte de dialogue **Éditeur du gestionnaire de connexions HTTP** pour configurer le gestionnaire de connexions HTTP en spécifiant des propriétés telles que l'URL et les informations d'identification de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ea75a-103">Use the **Server** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager by specifying properties such as the URL and security credentials.</span></span> <span data-ttu-id="ea75a-104">Une connexion HTTP permet à un package d'accéder à un serveur Web via HTTP pour l'envoi et la réception de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ea75a-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="ea75a-105">Une fois le gestionnaire de connexions HTTP configuré, vous pouvez également tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="ea75a-105">After configuring the HTTP Connection Manager, you can also test the connection.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ea75a-106">Le gestionnaire de connexions HTTP prend en charge uniquement l'authentification anonyme et l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="ea75a-106">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="ea75a-107">Il ne prend pas en charge l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="ea75a-107">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="ea75a-108">Pour en savoir plus sur le gestionnaire de connexions HTTP, consultez [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ea75a-108">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="ea75a-109">Pour en savoir plus sur un scénario d'utilisation courante pour le gestionnaire de connexions HTTP, consultez [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="ea75a-109">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea75a-110">Options</span><span class="sxs-lookup"><span data-stu-id="ea75a-110">Options</span></span>  
 <span data-ttu-id="ea75a-111">**URL du serveur**</span><span class="sxs-lookup"><span data-stu-id="ea75a-111">**Server URL**</span></span>  
 <span data-ttu-id="ea75a-112">Tapez l'URL du serveur.</span><span class="sxs-lookup"><span data-stu-id="ea75a-112">Type the URL for the server.</span></span>  
  
 <span data-ttu-id="ea75a-113">Si vous projetez d'utiliser le bouton **Télécharger WSDL** de la page **Général** de l' **Éditeur de tâche de service Web** pour télécharger un fichier WSDL, tapez l'URL de ce fichier WSDL.</span><span class="sxs-lookup"><span data-stu-id="ea75a-113">If you plan to use the **Download WSDL** button on the **General** page of the **Web Service Task Editor** to download a WSDL file, type the URL for the WSDL file.</span></span> <span data-ttu-id="ea75a-114">Cette URL se termine par « ?wsdl ».</span><span class="sxs-lookup"><span data-stu-id="ea75a-114">This URL ends with "?wsdl".</span></span>  
  
 <span data-ttu-id="ea75a-115">**Utiliser les informations d'identification**</span><span class="sxs-lookup"><span data-stu-id="ea75a-115">**Use credentials**</span></span>  
 <span data-ttu-id="ea75a-116">Spécifiez si vous voulez que le gestionnaire de connexions HTTP utilise les informations d'identification de sécurité de l'utilisateur pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="ea75a-116">Specify whether you want the HTTP Connection Manager to use the user's security credentials for authentication.</span></span>  
  
 <span data-ttu-id="ea75a-117">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ea75a-117">**User name**</span></span>  
 <span data-ttu-id="ea75a-118">Si le gestionnaire de connexions HTTP utilise des informations d'identification, vous devez spécifier un nom d'utilisateur, un mot de passe et un domaine.</span><span class="sxs-lookup"><span data-stu-id="ea75a-118">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="ea75a-119">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="ea75a-119">**Password**</span></span>  
 <span data-ttu-id="ea75a-120">Si le gestionnaire de connexions HTTP utilise des informations d'identification, vous devez spécifier un nom d'utilisateur, un mot de passe et un domaine.</span><span class="sxs-lookup"><span data-stu-id="ea75a-120">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="ea75a-121">**Domaine**</span><span class="sxs-lookup"><span data-stu-id="ea75a-121">**Domain**</span></span>  
 <span data-ttu-id="ea75a-122">Si le gestionnaire de connexions HTTP utilise des informations d'identification, vous devez spécifier un nom d'utilisateur, un mot de passe et un domaine.</span><span class="sxs-lookup"><span data-stu-id="ea75a-122">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="ea75a-123">**Utiliser le certificat client**</span><span class="sxs-lookup"><span data-stu-id="ea75a-123">**Use client certificate**</span></span>  
 <span data-ttu-id="ea75a-124">Spécifiez si vous voulez que le gestionnaire de connexions HTTP utilise un certificat client pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="ea75a-124">Specify whether you want the HTTP Connection Manager to use a client certificate for authentication.</span></span>  
  
 <span data-ttu-id="ea75a-125">**Certificate**</span><span class="sxs-lookup"><span data-stu-id="ea75a-125">**Certificate**</span></span>  
 <span data-ttu-id="ea75a-126">Sélectionnez un certificat dans la liste via la boîte de dialogue **Sélectionner un certificat** .</span><span class="sxs-lookup"><span data-stu-id="ea75a-126">Select a certificate from the list by using the **Select Certificate** dialog box.</span></span> <span data-ttu-id="ea75a-127">La zone de texte affiche le nom associé au certificat.</span><span class="sxs-lookup"><span data-stu-id="ea75a-127">The text box displays the name associated with this certificate.</span></span>  
  
 <span data-ttu-id="ea75a-128">**Délai d'expiration (en secondes)**</span><span class="sxs-lookup"><span data-stu-id="ea75a-128">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="ea75a-129">Spécifiez un délai d'expiration pour la connexion au serveur Web.</span><span class="sxs-lookup"><span data-stu-id="ea75a-129">Provide a time-out for connecting to the Web server.</span></span> <span data-ttu-id="ea75a-130">La valeur par défaut de cette propriété est 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="ea75a-130">The default value of this property is 30 seconds.</span></span>  
  
 <span data-ttu-id="ea75a-131">**Taille de segment (en Ko)**</span><span class="sxs-lookup"><span data-stu-id="ea75a-131">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="ea75a-132">Spécifiez une taille de segment pour l'écriture des données.</span><span class="sxs-lookup"><span data-stu-id="ea75a-132">Provide a chunk size for writing data.</span></span>  
  
 <span data-ttu-id="ea75a-133">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="ea75a-133">**Test Connection**</span></span>  
 <span data-ttu-id="ea75a-134">Après avoir configuré le gestionnaire de connexions HTTP, vérifiez que la connexion est viable en cliquant sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="ea75a-134">After configuring the HTTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea75a-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea75a-135">See Also</span></span>  
 <span data-ttu-id="ea75a-136">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ea75a-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="ea75a-137">Éditeur du gestionnaire de connexions HTTP &#40;page Proxy&#41;</span><span class="sxs-lookup"><span data-stu-id="ea75a-137">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-proxy-page.md)  
  
  
