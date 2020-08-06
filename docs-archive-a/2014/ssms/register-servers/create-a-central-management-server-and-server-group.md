---
title: Créer un groupe et un serveur de gestion centralisée
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- configuration server
ms.assetid: da265482-3953-440a-ac23-0ab7e42a55eb
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f53b75966a14dbc6fd6cdc9bea0929ccac7780c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695208"
---
# <a name="create-a-central-management-server-and-server-group-sql-server-management-studio"></a><span data-ttu-id="f5b08-102">Créer un serveur d'administration centralisée et un groupe de serveurs (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f5b08-102">Create a Central Management Server and Server Group (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f5b08-103">Cette rubrique explique comment désigner une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comme serveur de gestion centralisée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5b08-103">This topic describes how to designate an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a central management server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f5b08-104">Les serveurs d'administration centralisée stockent une liste d'instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Cette liste est organisée en un ou plusieurs groupes de serveurs d'administration centralisée.</span><span class="sxs-lookup"><span data-stu-id="f5b08-104">Central management servers store a list of instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is organized into one or more central management server groups.</span></span> <span data-ttu-id="f5b08-105">Les actions prises en utilisant un groupe de serveurs d'administration centralisée s'appliquent à tous les serveurs du groupe.</span><span class="sxs-lookup"><span data-stu-id="f5b08-105">Actions that are taken by using a central management server group act on all servers in the server group.</span></span> <span data-ttu-id="f5b08-106">Cela inclut la connexion aux serveurs à l'aide de l'Explorateur d'objets et l'exécution d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] et de stratégies de la Gestion basée sur des stratégies sur plusieurs serveurs simultanément.</span><span class="sxs-lookup"><span data-stu-id="f5b08-106">This includes connecting to servers by using Object Explorer and executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and Policy-Based Management policies on multiple servers at the same time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5b08-107">Les versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieures à [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ne peuvent pas être désignées en tant que serveur d'administration centralisée.</span><span class="sxs-lookup"><span data-stu-id="f5b08-107">Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] cannot be designated as a central management server.</span></span>  
  
 <span data-ttu-id="f5b08-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f5b08-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f5b08-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f5b08-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f5b08-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f5b08-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f5b08-111">**Pour créer un serveur de gestion centralisée et un groupe de serveurs à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="f5b08-111">**To create a Central Management Server and Server Group, using:**</span></span>  
  
     [<span data-ttu-id="f5b08-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f5b08-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f5b08-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f5b08-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f5b08-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f5b08-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f5b08-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f5b08-115">Permissions</span></span>  
 <span data-ttu-id="f5b08-116">Dans la base de données msdb, deux rôles de base de données accordent l'accès aux serveurs d'administration centralisée.</span><span class="sxs-lookup"><span data-stu-id="f5b08-116">Two database roles in the msdb database grant access to central management servers.</span></span> <span data-ttu-id="f5b08-117">Seuls les membres du rôle ServerGroupAdministratorRole peuvent gérer le serveur d'administration centralisée.</span><span class="sxs-lookup"><span data-stu-id="f5b08-117">Only members of the ServerGroupAdministratorRole role can manage the central management server.</span></span> <span data-ttu-id="f5b08-118">L'appartenance au rôle ServerGroupReaderRole est requise pour se connecter à un serveur d'administration centralisée.</span><span class="sxs-lookup"><span data-stu-id="f5b08-118">Membership in the ServerGroupReaderRole role is required to connect to a central management server.</span></span>  
  
 <span data-ttu-id="f5b08-119">Dans la mesure où les connexions gérées par un serveur d'administration centralisée s'exécutent dans le contexte de l'utilisateur, avec l'authentification Windows, les autorisations effectives sur les serveurs inscrits peuvent varier.</span><span class="sxs-lookup"><span data-stu-id="f5b08-119">Because the connections that are maintained by a central management server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="f5b08-120">Par exemple, l'utilisateur peut être membre du rôle serveur fixe sysadmin sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, mais disposer d'autorisations limitées sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span><span class="sxs-lookup"><span data-stu-id="f5b08-120">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f5b08-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f5b08-121">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f5b08-122">Les procédures suivantes expliquent comment effectuer les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="f5b08-122">The following procedures describe how to perform the following steps.</span></span>  
  
1.  <span data-ttu-id="f5b08-123">Créez un serveur d'administration centralisée.</span><span class="sxs-lookup"><span data-stu-id="f5b08-123">Create a central management server.</span></span>  
  
2.  <span data-ttu-id="f5b08-124">Ajoutez un ou plusieurs groupes de serveurs au serveur de gestion centralisée et ajoutez un ou plusieurs serveurs inscrits dans les groupes.</span><span class="sxs-lookup"><span data-stu-id="f5b08-124">Add one or more server groups to the central management server and add one or more registered servers to the server groups.</span></span>  
  
#### <a name="create-a-central-management-server"></a><span data-ttu-id="f5b08-125">Créer un serveur d'administration centralisée</span><span class="sxs-lookup"><span data-stu-id="f5b08-125">Create a central management server</span></span>  
  
1.  <span data-ttu-id="f5b08-126">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans le menu **Affichage** , cliquez sur **Serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="f5b08-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="f5b08-127">Dans Serveurs inscrits, développez **Moteur de base de données**, cliquez avec le bouton droit sur **Serveurs de gestion centralisée**, puis cliquez sur **Inscrire le serveur de gestion centralisée**.</span><span class="sxs-lookup"><span data-stu-id="f5b08-127">In Registered Servers, expand **Database Engine**, right-click **Central Management Servers**, and then  click **Register Central Management Server**.</span></span>  
  
3.  <span data-ttu-id="f5b08-128">Dans la boîte de dialogue **Nouvelle inscription de serveur** , sélectionnez l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous souhaitez désigner en tant que serveur d’administration centralisée dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f5b08-128">In the **New Server Registration** dialog box, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to become the central management server from the drop-down list of servers.</span></span> <span data-ttu-id="f5b08-129">Vous devez utiliser l'authentification Windows pour le serveur d'administration centralisée.</span><span class="sxs-lookup"><span data-stu-id="f5b08-129">You must use Windows Authentication for the central management server.</span></span>  
  
4.  <span data-ttu-id="f5b08-130">Dans **Serveur inscrit**, entrez un nom de serveur et une description facultative.</span><span class="sxs-lookup"><span data-stu-id="f5b08-130">In **Registered Server**, enter a server name and optional description.</span></span>  
  
5.  <span data-ttu-id="f5b08-131">Dans l'onglet **Propriétés de connexion** , consultez ou modifiez les propriétés réseau et de connexion.</span><span class="sxs-lookup"><span data-stu-id="f5b08-131">From the **Connection Properties** tab, review or modifiy the network  and connection properties.</span></span> <span data-ttu-id="f5b08-132">Pour plus d’informations, consultez [Se connecter au serveur &#40;page Propriétés de connexion&#41; — Moteur de base de données](../f1-help/connect-to-server-connection-properties-page-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="f5b08-132">For more information, see [Connect to Server &#40;Connection Properties Page&#41; Database Engine](../f1-help/connect-to-server-connection-properties-page-database-engine.md)</span></span>  
  
6.  <span data-ttu-id="f5b08-133">Cliquez sur **Tester**pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="f5b08-133">Click **Test**, to test the connection.</span></span>  
  
7.  <span data-ttu-id="f5b08-134">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f5b08-134">Click **Save**.</span></span> <span data-ttu-id="f5b08-135">L'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] apparaît sous le dossier **Serveurs de gestion centralisée** .</span><span class="sxs-lookup"><span data-stu-id="f5b08-135">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will appear under the **Central Management Servers** folder.</span></span>  
  
#### <a name="create-a-new-server-group-and-add-servers-to-the-group"></a><span data-ttu-id="f5b08-136">Créer un nouveau groupe de serveurs et ajouter des serveurs au groupe</span><span class="sxs-lookup"><span data-stu-id="f5b08-136">Create a new server group and add servers to the group</span></span>  
  
1.  <span data-ttu-id="f5b08-137">Dans **Serveurs inscrits**, développez **Serveurs de gestion centralisée**.</span><span class="sxs-lookup"><span data-stu-id="f5b08-137">From **Registered Servers**, expand **Central Management Servers**.</span></span> <span data-ttu-id="f5b08-138">Cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ajoutée dans la procédure ci-dessus et sélectionnez **Nouveau groupe de serveurs**.</span><span class="sxs-lookup"><span data-stu-id="f5b08-138">Right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] added in the procedure above and select **New Server Group**.</span></span>  
  
2.  <span data-ttu-id="f5b08-139">Dans **Propriétés du nouveau groupe de serveurs**, entrez un nom de groupe et une description facultative.</span><span class="sxs-lookup"><span data-stu-id="f5b08-139">In **New Server Group Properties**, enter a group name and optional description.</span></span>  
  
3.  <span data-ttu-id="f5b08-140">Dans **Serveurs inscrits**, cliquez avec le bouton droit sur le groupe de serveurs, puis cliquez sur **Nouvelle inscription de serveur**.</span><span class="sxs-lookup"><span data-stu-id="f5b08-140">From **Registered Servers**, right-click the server group and click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="f5b08-141">Dans Nouvelle inscription de serveur, sélectionnez une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5b08-141">From New Server Registration, select an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f5b08-142">Pour plus d’informations, consultez [Créer un serveur inscrit &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="f5b08-142">For more information, see [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span></span> <span data-ttu-id="f5b08-143">Ajoutez davantage de serveurs le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="f5b08-143">Add more servers as appropriate.</span></span>  
  
#### <a name="to-execute-queries-against-several-configuration-targets-at-the-same-time"></a><span data-ttu-id="f5b08-144">Pour exécuter des requêtes sur plusieurs cibles de configuration en même temps</span><span class="sxs-lookup"><span data-stu-id="f5b08-144">To execute queries against several configuration targets at the same time</span></span>  
  
-   <span data-ttu-id="f5b08-145">Après avoir créé un serveur d'administration centralisée, un ou plusieurs groupes de serveurs et un ou plusieurs serveurs inscrits, vous pouvez exécuter des requêtes simultanément sur l'ensemble d'un groupe.</span><span class="sxs-lookup"><span data-stu-id="f5b08-145">After you create a central management server, one or more server groups, and one or more registered servers, you can execute queries against a whole group at the same time.</span></span> <span data-ttu-id="f5b08-146">Pour plus d’informations sur l’exécution simultanée d’instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] sur les serveurs d’un groupe de serveurs, consultez [Exécuter des instructions sur plusieurs serveurs simultanément &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span><span class="sxs-lookup"><span data-stu-id="f5b08-146">For more information about how to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on the servers in a server group at the same time, see [Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b08-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5b08-147">See Also</span></span>  
 [<span data-ttu-id="f5b08-148">Administrer plusieurs serveurs à l’aide de serveurs de gestion centralisée</span><span class="sxs-lookup"><span data-stu-id="f5b08-148">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
