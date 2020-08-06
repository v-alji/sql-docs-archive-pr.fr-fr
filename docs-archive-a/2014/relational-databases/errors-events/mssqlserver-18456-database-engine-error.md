---
title: MSSQLSERVER_18456 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
ms.assetid: c417631d-be1f-42e0-8844-9f92c77e11f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5addb6bfb9d056d9f1796749ae629d4150102a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699695"
---
# <a name="mssqlserver_18456"></a><span data-ttu-id="78767-102">MSSQLSERVER_18456</span><span class="sxs-lookup"><span data-stu-id="78767-102">MSSQLSERVER_18456</span></span>
    
## <a name="details"></a><span data-ttu-id="78767-103">Détails</span><span class="sxs-lookup"><span data-stu-id="78767-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78767-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="78767-104">Product Name</span></span>|<span data-ttu-id="78767-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="78767-105">SQL Server</span></span>|  
|<span data-ttu-id="78767-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="78767-106">Event ID</span></span>|<span data-ttu-id="78767-107">18456</span><span class="sxs-lookup"><span data-stu-id="78767-107">18456</span></span>|  
|<span data-ttu-id="78767-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="78767-108">Event Source</span></span>|<span data-ttu-id="78767-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="78767-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="78767-110">Composant</span><span class="sxs-lookup"><span data-stu-id="78767-110">Component</span></span>|<span data-ttu-id="78767-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="78767-111">SQLEngine</span></span>|  
|<span data-ttu-id="78767-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="78767-112">Symbolic Name</span></span>|<span data-ttu-id="78767-113">LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="78767-113">LOGON_FAILED</span></span>|  
|<span data-ttu-id="78767-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="78767-114">Message Text</span></span>|<span data-ttu-id="78767-115">Échec de la connexion pour l’utilisateur '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="78767-115">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="78767-116">Explication</span><span class="sxs-lookup"><span data-stu-id="78767-116">Explanation</span></span>  
 <span data-ttu-id="78767-117">Lorsqu'une tentative de connexion est refusée en raison d’un échec d’authentification dû à un mot de passe ou un nom d’utilisateur incorrect, un message semblable au suivant est retourné sur le client :  Échec de la connexion pour l'utilisateur '<nom_utilisateur>'.</span><span class="sxs-lookup"><span data-stu-id="78767-117">When a connection attempt is rejected because of an authentication failure that involves a bad password or user name, a message similar to the following is returned to the client:  "Login failed for user '<user_name>'.</span></span> <span data-ttu-id="78767-118">(Microsoft SQL Server, erreur : 18456)".</span><span class="sxs-lookup"><span data-stu-id="78767-118">(Microsoft SQL Server, Error: 18456)".</span></span>  
  
 <span data-ttu-id="78767-119">Le client reçoit également les informations supplémentaires suivantes :</span><span class="sxs-lookup"><span data-stu-id="78767-119">Additional information returned to the client includes the following:</span></span>  
  
 <span data-ttu-id="78767-120">Échec de la connexion pour l'utilisateur '<nom_utilisateur>'.</span><span class="sxs-lookup"><span data-stu-id="78767-120">"Login failed for user '<user_name>'.</span></span> <span data-ttu-id="78767-121">(.Net SqlClient Data Provider) »</span><span class="sxs-lookup"><span data-stu-id="78767-121">(.Net SqlClient Data Provider)"</span></span>  
  
 -----------------------------\-  
  
 <span data-ttu-id="78767-122">« Nom du serveur : <nom_ordinateur> »</span><span class="sxs-lookup"><span data-stu-id="78767-122">"Server Name: <computer_name>"</span></span>  
  
 <span data-ttu-id="78767-123">« Numéro d’erreur : 18456 »</span><span class="sxs-lookup"><span data-stu-id="78767-123">"Error Number: 18456"</span></span>  
  
 <span data-ttu-id="78767-124">« Gravité : 14 »</span><span class="sxs-lookup"><span data-stu-id="78767-124">"Severity: 14"</span></span>  
  
 <span data-ttu-id="78767-125">« État : 1 »</span><span class="sxs-lookup"><span data-stu-id="78767-125">"State: 1"</span></span>  
  
 <span data-ttu-id="78767-126">« Numéro de ligne : 65536 »</span><span class="sxs-lookup"><span data-stu-id="78767-126">"Line Number: 65536"</span></span>  
  
 <span data-ttu-id="78767-127">Le message suivant peut également être retourné :</span><span class="sxs-lookup"><span data-stu-id="78767-127">The following message might also be returned:</span></span>  
  
 <span data-ttu-id="78767-128">« Message 18456, niveau 14, état 1, serveur <nom_ordinateur>, ligne 1 »</span><span class="sxs-lookup"><span data-stu-id="78767-128">"Msg 18456, Level 14, State 1, Server <computer_name>, Line 1"</span></span>  
  
 <span data-ttu-id="78767-129">« Échec de la connexion pour l'utilisateur '<nom_utilisateur>'. »</span><span class="sxs-lookup"><span data-stu-id="78767-129">"Login failed for user '<user_name>'."</span></span>  
  
## <a name="additional-error-information"></a><span data-ttu-id="78767-130">Informations supplémentaires sur l'erreur</span><span class="sxs-lookup"><span data-stu-id="78767-130">Additional Error Information</span></span>  
 <span data-ttu-id="78767-131">Pour des raisons de sécurité, le message d'erreur retourné au client masque délibérément la nature de l'erreur d'authentification.</span><span class="sxs-lookup"><span data-stu-id="78767-131">To increase security, the error message that is returned to the client deliberately hides the nature of the authentication error.</span></span> <span data-ttu-id="78767-132">Toutefois, dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], une erreur correspondante contient un état d'erreur mappé à une condition d'échec d'authentification.</span><span class="sxs-lookup"><span data-stu-id="78767-132">However, in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a corresponding error contains an error state that maps to an authentication failure condition.</span></span> <span data-ttu-id="78767-133">Comparez l'état d'erreur à la liste suivante afin de déterminer la raison de l'échec de connexion.</span><span class="sxs-lookup"><span data-stu-id="78767-133">Compare the error state to the following list to determine the reason for the login failure.</span></span>  
  
|<span data-ttu-id="78767-134">State</span><span class="sxs-lookup"><span data-stu-id="78767-134">State</span></span>|<span data-ttu-id="78767-135">Description</span><span class="sxs-lookup"><span data-stu-id="78767-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78767-136">1</span><span class="sxs-lookup"><span data-stu-id="78767-136">1</span></span>|<span data-ttu-id="78767-137">Aucune information sur l'erreur n'est disponible.</span><span class="sxs-lookup"><span data-stu-id="78767-137">Error information is not available.</span></span> <span data-ttu-id="78767-138">Cet état signifie généralement que vous n'avez pas l'autorisation de recevoir les informations d'erreur.</span><span class="sxs-lookup"><span data-stu-id="78767-138">This state usually means you do not have permission to receive the error details.</span></span> <span data-ttu-id="78767-139">Contactez votre administrateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="78767-139">Contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator for more information.</span></span>|  
|<span data-ttu-id="78767-140">2</span><span class="sxs-lookup"><span data-stu-id="78767-140">2</span></span>|<span data-ttu-id="78767-141">ID utilisateur non valide.</span><span class="sxs-lookup"><span data-stu-id="78767-141">User ID is not valid.</span></span>|  
|<span data-ttu-id="78767-142">5</span><span class="sxs-lookup"><span data-stu-id="78767-142">5</span></span>|<span data-ttu-id="78767-143">ID utilisateur non valide.</span><span class="sxs-lookup"><span data-stu-id="78767-143">User ID is not valid.</span></span>|  
|<span data-ttu-id="78767-144">6</span><span class="sxs-lookup"><span data-stu-id="78767-144">6</span></span>|<span data-ttu-id="78767-145">Tentative d'utilisation d'un nom de connexion Windows avec l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="78767-145">An attempt was made to use a Windows login name with SQL Server Authentication.</span></span>|  
|<span data-ttu-id="78767-146">7</span><span class="sxs-lookup"><span data-stu-id="78767-146">7</span></span>|<span data-ttu-id="78767-147">La connexion est désactivée et le mot de passe est incorrect.</span><span class="sxs-lookup"><span data-stu-id="78767-147">Login is disabled, and the password is incorrect.</span></span>|  
|<span data-ttu-id="78767-148">8</span><span class="sxs-lookup"><span data-stu-id="78767-148">8</span></span>|<span data-ttu-id="78767-149">Le mot de passe est incorrect.</span><span class="sxs-lookup"><span data-stu-id="78767-149">The password is incorrect.</span></span>|  
|<span data-ttu-id="78767-150">9</span><span class="sxs-lookup"><span data-stu-id="78767-150">9</span></span>|<span data-ttu-id="78767-151">Mot de passe non valide.</span><span class="sxs-lookup"><span data-stu-id="78767-151">Password is not valid.</span></span>|  
|<span data-ttu-id="78767-152">11</span><span class="sxs-lookup"><span data-stu-id="78767-152">11</span></span>|<span data-ttu-id="78767-153">La connexion est valide mais l'accès au serveur a échoué.</span><span class="sxs-lookup"><span data-stu-id="78767-153">Login is valid, but server access failed.</span></span> <span data-ttu-id="78767-154">Cette erreur peut se produire lorsque l'utilisateur Windows a accès à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en tant que membre du groupe des administrateurs locaux, mais que Windows ne fournit pas d'informations d'identification d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="78767-154">One possible cause of this error is when the Windows user has access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a member of the local administrators group, but Windows is not providing administrator credentials.</span></span> <span data-ttu-id="78767-155">Pour vous connecter, démarrez le programme de connexion à l’aide de l’option **Exécuter en tant qu’administrateur**, puis ajoutez l’utilisateur Windows à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en tant que connexion spécifique.</span><span class="sxs-lookup"><span data-stu-id="78767-155">To connect, start the connecting program using the **Run as administrator** option, and then add the Windows user to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a specific login.</span></span>|  
|<span data-ttu-id="78767-156">12</span><span class="sxs-lookup"><span data-stu-id="78767-156">12</span></span>|<span data-ttu-id="78767-157">La connexion est valide mais l'accès au serveur a échoué.</span><span class="sxs-lookup"><span data-stu-id="78767-157">Login is valid login, but server access failed.</span></span>|  
|<span data-ttu-id="78767-158">18</span><span class="sxs-lookup"><span data-stu-id="78767-158">18</span></span>|<span data-ttu-id="78767-159">Le mot de passe doit être modifié.</span><span class="sxs-lookup"><span data-stu-id="78767-159">Password must be changed.</span></span>|  
  
 <span data-ttu-id="78767-160">Il existe d'autres états d'erreurs qui signifient une erreur de traitement interne inattendue.</span><span class="sxs-lookup"><span data-stu-id="78767-160">Other error states exist and signify an unexpected internal processing error.</span></span>  
  
 <span data-ttu-id="78767-161">**Une autre cause inhabituelle possible**</span><span class="sxs-lookup"><span data-stu-id="78767-161">**An additional unusual possible cause**</span></span>  
  
 <span data-ttu-id="78767-162">Motif de l'erreur **Échec d'une tentative de connexion à l'aide de l'authentification SQL Server. Le serveur est configuré pour l’authentification Windows uniquement.**</span><span class="sxs-lookup"><span data-stu-id="78767-162">The error reason **An attempt to login using SQL authentication failed. Server is configured for Windows authentication only.**</span></span> <span data-ttu-id="78767-163">Ce message peut être retourné dans les situations suivantes.</span><span class="sxs-lookup"><span data-stu-id="78767-163">can be returned in the following situations.</span></span>  
  
-   <span data-ttu-id="78767-164">Lorsque le serveur est configuré pour une authentification en mode mixte et qu'une connexion ODBC utilise le protocole TCP, la connexion ne spécifie pas de manière explicite que la connexion doit utiliser une connexion approuvée.</span><span class="sxs-lookup"><span data-stu-id="78767-164">When the server is configured for mixed mode authentication, and an ODBC connection uses the TCP protocol, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
-   <span data-ttu-id="78767-165">Lorsque le serveur est configuré pour l'authentification en mode mixte et qu'une connexion ODBC utilise des canaux nommés, les informations d'identification utilisées par le client pour ouvrir le canal nommé servent à emprunter automatiquement l'identité de l'utilisateur et la connexion ne spécifie pas de manière explicite que la connexion doit utiliser une connexion approuvée.</span><span class="sxs-lookup"><span data-stu-id="78767-165">When the server is configured for mixed mode authentication, and an ODBC connection uses named pipes, and the credentials the client used to open the named pipe are used to automatically impersonate the user, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
 <span data-ttu-id="78767-166">Pour résoudre ce problème, incluez `TRUSTED_CONNECTION = TRUE` dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="78767-166">To resolve this issue, include `TRUSTED_CONNECTION = TRUE` in the connection string.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="78767-167">Exemples</span><span class="sxs-lookup"><span data-stu-id="78767-167">Examples</span></span>  
 <span data-ttu-id="78767-168">Dans cet exemple, l'état d'erreur d'authentification est 8.</span><span class="sxs-lookup"><span data-stu-id="78767-168">In this example, the authentication error state is 8.</span></span> <span data-ttu-id="78767-169">Cela indique que le mot de passe est incorrect.</span><span class="sxs-lookup"><span data-stu-id="78767-169">This indicates that the password is incorrect.</span></span>  
  
|<span data-ttu-id="78767-170">Date</span><span class="sxs-lookup"><span data-stu-id="78767-170">Date</span></span>|<span data-ttu-id="78767-171">Source</span><span class="sxs-lookup"><span data-stu-id="78767-171">Source</span></span>|<span data-ttu-id="78767-172">Message</span><span class="sxs-lookup"><span data-stu-id="78767-172">Message</span></span>|  
|----------|------------|-------------|  
|<span data-ttu-id="78767-173">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="78767-173">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="78767-174">Connexion</span><span class="sxs-lookup"><span data-stu-id="78767-174">Logon</span></span>|<span data-ttu-id="78767-175">Erreur : 18456, Gravité : 14, État : 8.</span><span class="sxs-lookup"><span data-stu-id="78767-175">Error: 18456, Severity: 14, State: 8.</span></span>|  
|<span data-ttu-id="78767-176">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="78767-176">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="78767-177">Connexion</span><span class="sxs-lookup"><span data-stu-id="78767-177">Logon</span></span>|<span data-ttu-id="78767-178">Échec de la connexion pour l'utilisateur '<nom_utilisateur>'.</span><span class="sxs-lookup"><span data-stu-id="78767-178">Login failed for user '<user_name>'.</span></span> <span data-ttu-id="78767-179">[CLIENT : \<ip address>]</span><span class="sxs-lookup"><span data-stu-id="78767-179">[CLIENT: \<ip address>]</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="78767-180">Quand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est installé avec le mode d’authentification Windows et modifié ultérieurement pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec le mode d’authentification Windows, la connexion **sa** est initialement désactivée.</span><span class="sxs-lookup"><span data-stu-id="78767-180">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed using Windows Authentication mode and is later changed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows Authentication mode, the **sa** login is initially disabled.</span></span> <span data-ttu-id="78767-181">Cela provoque l’erreur d’état 7 : « Échec de la connexion de l’utilisateur 'sa'. » Pour activer la connexion **sa**, consultez [Modifier le mode d’authentification du serveur](../../database-engine/configure-windows/change-server-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="78767-181">This causes the state 7 error: "Login failed for user 'sa'." To enable the **sa** login, see [Change Server Authentication Mode](../../database-engine/configure-windows/change-server-authentication-mode.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="78767-182">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="78767-182">User Action</span></span>  
 <span data-ttu-id="78767-183">Si vous essayez de vous connecter à l'aide de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vérifiez que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configuré en mode Authentification mixte.</span><span class="sxs-lookup"><span data-stu-id="78767-183">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="78767-184">Si vous essayez de vous connecter à l'aide de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vérifiez que la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] existe et que vous l'avez orthographiée correctement.</span><span class="sxs-lookup"><span data-stu-id="78767-184">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists and that you have spelled it properly.</span></span>  
  
 <span data-ttu-id="78767-185">Si vous essayez de vous connecter à l'aide de l'authentification Windows, vérifiez que vous êtes correctement connecté au domaine approprié.</span><span class="sxs-lookup"><span data-stu-id="78767-185">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
 <span data-ttu-id="78767-186">Si votre erreur indique l'état 1, contactez votre administrateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78767-186">If your error indicates state 1, contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="78767-187">Si vous essayez de vous connecter avec vos informations d’identification d’administrateur, démarrez votre application à l’aide de l’option **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="78767-187">If you are trying to connect using your administrator credentials, start you application by using the **Run as Administrator** option.</span></span> <span data-ttu-id="78767-188">Une fois connecté, ajoutez votre utilisateur Windows en tant que connexion individuelle.</span><span class="sxs-lookup"><span data-stu-id="78767-188">When connected, add your Windows user as an individual login.</span></span>  
  
 <span data-ttu-id="78767-189">Si le [!INCLUDE[ssDE](../../includes/ssde-md.md)] prend en charge les bases de données autonomes, vérifiez que la connexion n’a pas été supprimée suite à la migration vers un utilisateur de base de données autonome.</span><span class="sxs-lookup"><span data-stu-id="78767-189">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] supports contained databases, confirm that the login was not deleted after migration to a contained database user.</span></span>  
  
 <span data-ttu-id="78767-190">Lors de la connexion locale à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les connexions d’autres services qui s’exécutent également sous **NT AUTHORITY\NETWORK SERVICE** doivent s’authentifier à l’aide du nom de domaine complet des ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="78767-190">When connecting locally to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connections from services running under **NT AUTHORITY\NETWORK SERVICE** must authenticate using the computers fully qualified domain name.</span></span> <span data-ttu-id="78767-191">Pour plus d’informations, consultez [Guide pratique pour Utiliser le compte de service réseau pour accéder à des ressources dans ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span><span class="sxs-lookup"><span data-stu-id="78767-191">For more information, see [How To: Use the Network Service Account to Access Resources in ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span></span>  
  
  
