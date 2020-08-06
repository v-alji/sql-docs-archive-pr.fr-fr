---
title: Exécuter des instructions sur plusieurs serveurs simultanément
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- executing queries against multiple servers
- queries [SQL Server], multiserver
ms.assetid: 197760f3-0a06-43de-8162-69c27d3fbe56
author: markingmyname
ms.author: maghan
ms.openlocfilehash: b94775029a1501d3e894d84ef4a027fc1595dc10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702268"
---
# <a name="execute-statements-against-multiple-servers-simultaneously-sql-server-management-studio"></a><span data-ttu-id="f0080-102">Exécuter des instructions simultanément sur plusieurs serveurs (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f0080-102">Execute Statements Against Multiple Servers Simultaneously (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f0080-103">Cette rubrique explique comment interroger simultanément plusieurs serveurs dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]en créant un groupe de serveurs locaux, ou un serveur de gestion centralisée et un ou plusieurs groupes de serveurs, et un ou plusieurs serveurs inscrits dans les groupes, puis en interrogeant le groupe complet.</span><span class="sxs-lookup"><span data-stu-id="f0080-103">This topic describes how to query multiple servers at the same time in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], by creating a local server group, or a Central Management Server and one or more server groups, and one or more registered servers within the groups, and then querying the complete group.</span></span> <span data-ttu-id="f0080-104">Les résultats retournés par la requête peuvent être combinés dans un volet de résultats unique ou retournés dans des volets de résultats distincts.</span><span class="sxs-lookup"><span data-stu-id="f0080-104">The results that are returned by the query can be combined into a single results pane, or can be returned in separate results panes.</span></span> <span data-ttu-id="f0080-105">Le jeu de résultats peut inclure des colonnes supplémentaires pour le nom du serveur et la connexion utilisée par la requête sur chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="f0080-105">The results set can include additional columns for the server name and the login that is used by the query on each server.</span></span> <span data-ttu-id="f0080-106">Les serveurs de gestion centralisée et les serveurs subordonnés peuvent être inscrits uniquement à l'aide de l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="f0080-106">Central Management Servers and subordinate servers can be registered by using only Windows Authentication.</span></span> <span data-ttu-id="f0080-107">Les serveurs dans les groupes de serveurs locaux peuvent être inscrits à l'aide de l'authentification Windows ou de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0080-107">Servers in local server groups can be registered by using Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0080-108">Avant d'exécuter les procédures suivantes, créez un serveur de gestion centralisée et des groupes de serveurs.</span><span class="sxs-lookup"><span data-stu-id="f0080-108">Before you execute the following procedures, create a Central Management Server and server groups.</span></span> <span data-ttu-id="f0080-109">Pour plus d’informations, consultez [Créer un serveur d’administration centralisée et un groupe de serveurs &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="f0080-109">For more information, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span></span>  
  
 <span data-ttu-id="f0080-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f0080-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f0080-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f0080-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f0080-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0080-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f0080-113">**Pour exécuter des instructions sur plusieurs serveurs à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="f0080-113">**To execute statements against multiple servers, using:**</span></span>  
  
     [<span data-ttu-id="f0080-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0080-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0080-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f0080-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0080-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0080-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0080-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f0080-117">Permissions</span></span>  
 <span data-ttu-id="f0080-118">Dans la mesure où les connexions gérées par un serveur de gestion centralisée s'exécutent dans le contexte de l'utilisateur, avec l'authentification Windows, les autorisations effectives sur les serveurs inscrits peuvent varier.</span><span class="sxs-lookup"><span data-stu-id="f0080-118">Because the connections maintained by a Central Management Server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="f0080-119">Par exemple, l'utilisateur peut être membre du rôle serveur fixe sysadmin sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, mais disposer d'autorisations limitées sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span><span class="sxs-lookup"><span data-stu-id="f0080-119">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f0080-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0080-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-statements-against-multiple-configuration-targets-simultaneously"></a><span data-ttu-id="f0080-121">Pour exécuter des instructions contre plusieurs cibles de configuration simultanément</span><span class="sxs-lookup"><span data-stu-id="f0080-121">To execute statements against multiple configuration targets simultaneously</span></span>  
  
1.  <span data-ttu-id="f0080-122">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans le menu **Affichage** , cliquez sur **Serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="f0080-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="f0080-123">Développez un serveur de gestion centralisée, cliquez avec le bouton droit sur un groupe de serveurs, pointez sur **Se connecter**, puis cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f0080-123">Expand a Central Management Server, right-click a server group, point to **Connect**, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0080-124">Dans l'Éditeur de requête, tapez et exécutez une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] , telle que la suivante :</span><span class="sxs-lookup"><span data-stu-id="f0080-124">In Query Editor, type and execute a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as the following:</span></span>  
  
    ```  
    USE master  
    GO  
    SELECT * FROM sysdatabases;  
    GO  
    ```  
  
     <span data-ttu-id="f0080-125">Par défaut, le volet de résultats combine les résultats de la requête à partir de tous les serveurs appartenant au groupe de serveurs.</span><span class="sxs-lookup"><span data-stu-id="f0080-125">By default, the results pane will combine the query results from all the servers in the server group.</span></span>  
  
#### <a name="to-change-the-multiserver-results-options"></a><span data-ttu-id="f0080-126">Pour modifier les options de résultats multiserveurs</span><span class="sxs-lookup"><span data-stu-id="f0080-126">To change the multiserver results options</span></span>  
  
1.  <span data-ttu-id="f0080-127">Dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="f0080-127">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="f0080-128">Développez **Résultats de la requête**, **SQL Server**, puis cliquez sur **Résultats multiserveurs**.</span><span class="sxs-lookup"><span data-stu-id="f0080-128">Expand **Query Results**, expand **SQL Server**, and then click **Multiserver Results**.</span></span>  
  
3.  <span data-ttu-id="f0080-129">Dans la page **Résultats multiserveurs** , spécifiez les paramètres d'options souhaités, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0080-129">On the **Multiserver Results** page, specify the option settings that you want, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0080-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0080-130">See Also</span></span>  
 [<span data-ttu-id="f0080-131">Administrer plusieurs serveurs à l’aide de serveurs de gestion centralisée</span><span class="sxs-lookup"><span data-stu-id="f0080-131">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
