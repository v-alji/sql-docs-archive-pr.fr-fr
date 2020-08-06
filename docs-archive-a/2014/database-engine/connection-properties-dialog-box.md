---
title: Propriétés de connexion, boîte de dialogue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connectionproperties.f1
helpviewer_keywords:
- Connection Properties dialog box
ms.assetid: 6df812ad-4d80-4503-8a23-47719ce85624
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db2817ebaf3f1655f146c060fcb79d550ad0cc8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707807"
---
# <a name="connection-properties-dialog-box"></a><span data-ttu-id="efcea-102">Propriétés de connexion (boîte de dialogue)</span><span class="sxs-lookup"><span data-stu-id="efcea-102">Connection Properties Dialog Box</span></span>
  <span data-ttu-id="efcea-103">Cette boîte de dialogue vous permet d'afficher les propriétés de la connexion en cours.</span><span class="sxs-lookup"><span data-stu-id="efcea-103">Use this dialog box to view the current connection properties.</span></span> <span data-ttu-id="efcea-104">Cette boîte de dialogue est disponible lorsque vous cliquez sur **Afficher les propriétés de connexion** dans les différentes boîtes de dialogue de l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="efcea-104">This dialog box is available when you click **View connection properties** in various Object Explorer dialog boxes.</span></span> <span data-ttu-id="efcea-105">Les propriétés affichées dans cette page sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="efcea-105">The properties displayed on this page are read-only.</span></span>  
  
 <span data-ttu-id="efcea-106">Pour modifier des propriétés telles que **Base de données**, connectez-vous à la base de données de votre choix à l'aide de l'Explorateur d'objets, avant d'ouvrir la boîte de dialogue **Propriétés de connexion** .</span><span class="sxs-lookup"><span data-stu-id="efcea-106">To change properties such as **Database**, connect to the desired database with Object Explorer before opening the **Connection Properties** dialog box.</span></span>  
  
 <span data-ttu-id="efcea-107">Notez que le délai d'attente de requête pour SQL Azure est de 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="efcea-107">Note that the query time-out period for SQL Azure is 30 minutes.</span></span>  
  
## <a name="authentication"></a><span data-ttu-id="efcea-108">Authentification</span><span class="sxs-lookup"><span data-stu-id="efcea-108">Authentication</span></span>  
 <span data-ttu-id="efcea-109">Permet d'afficher les propriétés d'authentification pour la connexion en cours.</span><span class="sxs-lookup"><span data-stu-id="efcea-109">View authentication properties for the current connection.</span></span> <span data-ttu-id="efcea-110">Les propriétés d'authentification correspondent au nom d'accès et à la méthode d'authentification utilisés une fois la connexion établie.</span><span class="sxs-lookup"><span data-stu-id="efcea-110">Authentication properties are the login and authentication method when the connection was established.</span></span> <span data-ttu-id="efcea-111">Pour modifier les propriétés d’authentification, déconnectez [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -vous, puis reconnectez l’Explorateur d’objets au serveur, à l’aide des options de connexion souhaitées.</span><span class="sxs-lookup"><span data-stu-id="efcea-111">To change the authentication properties, disconnect from [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then connect Object Explorer to the server again, using the desired connection options.</span></span>  
  
 <span data-ttu-id="efcea-112">**Méthode d’authentification**</span><span class="sxs-lookup"><span data-stu-id="efcea-112">**Authentication Method**</span></span>  
 <span data-ttu-id="efcea-113">Méthode d'authentification utilisée pour la connexion en cours.</span><span class="sxs-lookup"><span data-stu-id="efcea-113">The authentication method used for the current connection.</span></span>  
  
 <span data-ttu-id="efcea-114">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="efcea-114">**User Name**</span></span>  
 <span data-ttu-id="efcea-115">Nom de l'utilisateur de connexion utilisé pour l'authentification de la connexion.</span><span class="sxs-lookup"><span data-stu-id="efcea-115">The name of the user of login used for the connection authentication.</span></span>  
  
## <a name="connection-category"></a><span data-ttu-id="efcea-116">Catégorie de connexion</span><span class="sxs-lookup"><span data-stu-id="efcea-116">Connection Category</span></span>  
 <span data-ttu-id="efcea-117">Permet d'afficher les propriétés de la connexion en cours.</span><span class="sxs-lookup"><span data-stu-id="efcea-117">View connection properties for the current connection.</span></span> <span data-ttu-id="efcea-118">La plupart des propriétés de connexion ont été sélectionnées sous l'onglet **Propriétés de connexion** de la boîte de dialogue **Se connecter au serveur** au cours du processus de connexion.</span><span class="sxs-lookup"><span data-stu-id="efcea-118">Most connection properties were selected on the **Connection Properties** tab of the **Connect to server** dialog box during the connection process.</span></span>  
  
 <span data-ttu-id="efcea-119">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="efcea-119">**Database**</span></span>  
 <span data-ttu-id="efcea-120">Nom de la base de données connectée.</span><span class="sxs-lookup"><span data-stu-id="efcea-120">The name of the database currently connected to.</span></span> <span data-ttu-id="efcea-121">Pour modifier cela, utilisez la barre d'outils Éditeur SQL.</span><span class="sxs-lookup"><span data-stu-id="efcea-121">To change this use, the SQL Editor toolbar.</span></span>  
  
 <span data-ttu-id="efcea-122">**SPID**</span><span class="sxs-lookup"><span data-stu-id="efcea-122">**SPID**</span></span>  
 <span data-ttu-id="efcea-123">Identificateur de processus système attribué par le serveur à la connexion.</span><span class="sxs-lookup"><span data-stu-id="efcea-123">The system process ID assigned by the server to the connection.</span></span> <span data-ttu-id="efcea-124">Il ne peut pas être changé pour cette connexion.</span><span class="sxs-lookup"><span data-stu-id="efcea-124">This cannot be changed for this connection.</span></span>  
  
 <span data-ttu-id="efcea-125">**Protocole réseau**</span><span class="sxs-lookup"><span data-stu-id="efcea-125">**Network Protocol**</span></span>  
 <span data-ttu-id="efcea-126">Protocole réseau de la connexion [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efcea-126">The network protocol of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] connection.</span></span> <span data-ttu-id="efcea-127">Pour modifier cela, connectez-vous de nouveau à l'aide des propriétés de connexion souhaitées.</span><span class="sxs-lookup"><span data-stu-id="efcea-127">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="efcea-128">**Taille du paquet réseau**</span><span class="sxs-lookup"><span data-stu-id="efcea-128">**Network Packet Size**</span></span>  
 <span data-ttu-id="efcea-129">Taille de paquet utilisée lors de la communication avec le serveur.</span><span class="sxs-lookup"><span data-stu-id="efcea-129">The packet size used when communicating with the server.</span></span> <span data-ttu-id="efcea-130">Pour modifier cela, connectez-vous de nouveau à l'aide des propriétés de connexion souhaitées.</span><span class="sxs-lookup"><span data-stu-id="efcea-130">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="efcea-131">**Délai de connexion**</span><span class="sxs-lookup"><span data-stu-id="efcea-131">**Connection Timeout**</span></span>  
 <span data-ttu-id="efcea-132">Durée en secondes à attendre lors de la connexion à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] avant l'expiration du délai et le renvoi à l'utilisateur d'une erreur de type Échec de connexion.</span><span class="sxs-lookup"><span data-stu-id="efcea-132">The amount of time is seconds to wait when connecting to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before timing out and returning a failure to connect error to the user.</span></span> <span data-ttu-id="efcea-133">Pour modifier cela, connectez-vous de nouveau à l'aide des propriétés de connexion souhaitées.</span><span class="sxs-lookup"><span data-stu-id="efcea-133">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="efcea-134">**Délai d’exécution**</span><span class="sxs-lookup"><span data-stu-id="efcea-134">**Execution Timeout**</span></span>  
 <span data-ttu-id="efcea-135">Durée en secondes à attendre avant que l'exécution d'une tâche se termine sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="efcea-135">The amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="efcea-136">Pour modifier cela, connectez-vous de nouveau à l'aide des propriétés de connexion souhaitées.</span><span class="sxs-lookup"><span data-stu-id="efcea-136">To change this, connect again with the desired connection properties.</span></span>  
  
 <span data-ttu-id="efcea-137">**Chiffré**</span><span class="sxs-lookup"><span data-stu-id="efcea-137">**Encrypted**</span></span>  
 <span data-ttu-id="efcea-138">Indique si la connexion en cours est chiffrée ou non.</span><span class="sxs-lookup"><span data-stu-id="efcea-138">Whether the current connection is encrypted.</span></span> <span data-ttu-id="efcea-139">Pour modifier cela, connectez-vous de nouveau à l'aide des propriétés de connexion souhaitées.</span><span class="sxs-lookup"><span data-stu-id="efcea-139">To change this, connect again with the desired connection properties.</span></span>  
  
## <a name="product-category"></a><span data-ttu-id="efcea-140">Catégorie de produit</span><span class="sxs-lookup"><span data-stu-id="efcea-140">Product Category</span></span>  
 <span data-ttu-id="efcea-141">Permet d'afficher les propriétés des produits pour la connexion en cours.</span><span class="sxs-lookup"><span data-stu-id="efcea-141">View product properties for the current connection.</span></span> <span data-ttu-id="efcea-142">Ces propriétés décrivent le produit, la version, le nom de l'instance et le classement du serveur.</span><span class="sxs-lookup"><span data-stu-id="efcea-142">These properties describe the server product, version, instance name, and collation.</span></span> <span data-ttu-id="efcea-143">Les propriétés sont définies au cours de l'installation de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efcea-143">The properties are set during [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="efcea-144">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="efcea-144">**Product Name**</span></span>  
 <span data-ttu-id="efcea-145">Nom du produit [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efcea-145">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product name.</span></span>  
  
 <span data-ttu-id="efcea-146">**Version du produit**</span><span class="sxs-lookup"><span data-stu-id="efcea-146">**Product Version**</span></span>  
 <span data-ttu-id="efcea-147">Version du produit [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efcea-147">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product version.</span></span>  
  
 <span data-ttu-id="efcea-148">**Nom de serveur**</span><span class="sxs-lookup"><span data-stu-id="efcea-148">**Server Name**</span></span>  
 <span data-ttu-id="efcea-149">Nom de l'ordinateur qui exécute [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efcea-149">The name of the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="efcea-150">**Nom de l’instance**</span><span class="sxs-lookup"><span data-stu-id="efcea-150">**Instance Name**</span></span>  
 <span data-ttu-id="efcea-151">Nom de l'instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="efcea-151">The instance name of the server.</span></span> <span data-ttu-id="efcea-152">L'instance par défaut est vide.</span><span class="sxs-lookup"><span data-stu-id="efcea-152">The default instance is blank.</span></span>  
  
 <span data-ttu-id="efcea-153">**Langage**</span><span class="sxs-lookup"><span data-stu-id="efcea-153">**Language**</span></span>  
 <span data-ttu-id="efcea-154">Version du langage du produit [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="efcea-154">The language version of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] product.</span></span>  
  
 <span data-ttu-id="efcea-155">**Classement**</span><span class="sxs-lookup"><span data-stu-id="efcea-155">**Collation**</span></span>  
 <span data-ttu-id="efcea-156">Classement du serveur.</span><span class="sxs-lookup"><span data-stu-id="efcea-156">The collation of the server.</span></span>  
  
## <a name="server-environment-category"></a><span data-ttu-id="efcea-157">Catégorie d'environnement de serveur</span><span class="sxs-lookup"><span data-stu-id="efcea-157">Server Environment Category</span></span>  
 <span data-ttu-id="efcea-158">Permet d'afficher les propriétés d'environnement de serveur de la connexion en cours en rapport avec le matériel et le système d'exploitation de serveur.</span><span class="sxs-lookup"><span data-stu-id="efcea-158">View server environment properties for the current connection related to the server hardware and operating system.</span></span> <span data-ttu-id="efcea-159">Les propriétés ne peuvent pas être configurées par [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efcea-159">The properties cannot be configured by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="efcea-160">**Nom de l’ordinateur**</span><span class="sxs-lookup"><span data-stu-id="efcea-160">**Computer Name**</span></span>  
 <span data-ttu-id="efcea-161">Nom de l'ordinateur serveur qui exécute [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efcea-161">The name of the server computer that is running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="efcea-162">**Plateforme**</span><span class="sxs-lookup"><span data-stu-id="efcea-162">**Platform**</span></span>  
 <span data-ttu-id="efcea-163">Nom du système d'exploitation, nom du fabricant et famille d'UC du serveur.</span><span class="sxs-lookup"><span data-stu-id="efcea-163">The operating system name, manufacturer name, and CPU family of the server.</span></span>  
  
 <span data-ttu-id="efcea-164">**Système d’exploitation**</span><span class="sxs-lookup"><span data-stu-id="efcea-164">**Operating System**</span></span>  
 <span data-ttu-id="efcea-165">Version de [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows installée sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="efcea-165">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows version installed on the server.</span></span>  
  
 <span data-ttu-id="efcea-166">**Processeurs**</span><span class="sxs-lookup"><span data-stu-id="efcea-166">**Processors**</span></span>  
 <span data-ttu-id="efcea-167">Nombre de processeurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="efcea-167">The number of processors on the server.</span></span>  
  
 <span data-ttu-id="efcea-168">**Operating System Memory**</span><span class="sxs-lookup"><span data-stu-id="efcea-168">**Operating System Memory**</span></span>  
 <span data-ttu-id="efcea-169">Quantité globale de mémoire physique sur le serveur, en mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="efcea-169">The total amount of physical memory on the server, in megabytes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efcea-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="efcea-170">See Also</span></span>  
 <span data-ttu-id="efcea-171">[Pages de propriétés dans SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="efcea-171">[Property Pages in SQL Server Management Studio](../ssms/property-pages-in-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="efcea-172">Se connecter au serveur &#40;page Connexion&#41; — Moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="efcea-172">Connect to Server &#40;Login Page&#41; Database Engine</span></span>](../ssms/f1-help/connect-to-server-login-page-database-engine.md)  
  
  
