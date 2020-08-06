---
title: Supprimer la mise en miroir de bases de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- removing database mirroring [SQL Server]
ms.assetid: bbc4d7f7-3bc7-40d6-a822-af195fe7f8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19c1d0449fa1c7434aeaf9c51e3b2dc7bc6b68c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701801"
---
# <a name="remove-database-mirroring-sql-server"></a><span data-ttu-id="2b8cb-102">Supprimer la mise en miroir des bases de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2b8cb-102">Remove Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="2b8cb-103">Cette rubrique explique comment supprimer la mise en miroir de bases de données depuis une base de données de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b8cb-103">This topic describes how to remove database mirroring from a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  <span data-ttu-id="2b8cb-104">À tout moment, le propriétaire d'une base de données peut arrêter manuellement une session de mise en miroir de bases de données en supprimant la mise en miroir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-104">At any time, the database owner can manually stop a database mirroring session by removing mirroring from the database.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2b8cb-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2b8cb-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2b8cb-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2b8cb-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2b8cb-107">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2b8cb-107">Permissions</span></span>  
 <span data-ttu-id="2b8cb-108">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-108">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2b8cb-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2b8cb-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="2b8cb-110">Pour supprimer une mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="2b8cb-110">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="2b8cb-111">Lors d'une session de mise en miroir de bases de données, connectez-vous à l'instance du serveur principal, puis, dans l'Explorateur d'objets, cliquez sur le nom du serveur pour développer l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-111">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="2b8cb-112">Développez le nœud **Bases de données**et sélectionnez la base de données.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-112">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="2b8cb-113">Cliquez avec le bouton droit sur la base de données, sélectionnez **Tâches**, puis cliquez sur **Miroir**.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-113">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="2b8cb-114">La page **Mise en miroir** de la boîte de dialogue **Propriétés de la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-114">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="2b8cb-115">Dans le volet **Sélectionner une page** , cliquez sur **Mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-115">In the **Select a Page** pane, click **Mirroring**.</span></span>  
  
5.  <span data-ttu-id="2b8cb-116">Pour supprimer une mise en miroir, cliquez sur **Supprimer la mise en miroir**.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-116">To remove mirroring, click **Remove Mirroring**.</span></span> <span data-ttu-id="2b8cb-117">Vous êtes invité à confirmer l'opération.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-117">A prompt asks for confirmation.</span></span> <span data-ttu-id="2b8cb-118">Si vous cliquez sur **Oui**, la session s'arrête et la mise en miroir est supprimée de la base de données.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-118">If you click **Yes**, the session is stopped and mirroring is removed from the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2b8cb-119">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2b8cb-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="2b8cb-120">Pour supprimer une mise en miroir de bases de données, utilisez la page **Propriétés de la base de données**.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-120">To remove database mirroring, use the **Database Properties**.</span></span> <span data-ttu-id="2b8cb-121">Utilisez la page **Mise en miroir** de la boîte de dialogue **Propriétés de la base de données** .</span><span class="sxs-lookup"><span data-stu-id="2b8cb-121">use the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="2b8cb-122">Pour supprimer une mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="2b8cb-122">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="2b8cb-123">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)] de l'un des partenaires de mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] of either mirroring partner.</span></span>  
  
2.  <span data-ttu-id="2b8cb-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2b8cb-125">Soumettez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="2b8cb-125">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    ALTER DATABASE database_name SET PARTNER OFF  
    ```  
  
     <span data-ttu-id="2b8cb-126">où *nom_base_de_données* représente la base de données en miroir dont vous voulez supprimer la session.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-126">where *database_name* is the mirrored database whose session you want to remove.</span></span>  
  
     <span data-ttu-id="2b8cb-127">L'exemple suivant supprime la mise en miroir de bases de données de l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b8cb-127">The following example removes database mirroring from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER OFF;  
    ```  
  
##  <a name="follow-up-removing-database-mirroring"></a><a name="FollowUp"></a> <span data-ttu-id="2b8cb-128">Suivi : Suppression d'une mise en miroir des bases de données</span><span class="sxs-lookup"><span data-stu-id="2b8cb-128">Follow Up: Removing Database Mirroring</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b8cb-129">Pour plus d’informations sur l’impact de la suppression d’une mise en miroir de bases de données, consultez [Suppression d’une mise en miroir des bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2b8cb-129">For information about the impact of removing mirroring, see [Removing Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="2b8cb-130">**Si vous envisagez de redémarrer la mise en miroir sur la base de données**</span><span class="sxs-lookup"><span data-stu-id="2b8cb-130">**If you intend to restart mirroring on the database**</span></span>  
  
     <span data-ttu-id="2b8cb-131">Toutes les sauvegardes du journal effectuées sur la base de données principale après la suppression de la mise en miroir doivent être toutes appliquées à la base de données miroir avant de pouvoir redémarrer la mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-131">Any log backups taken on the principal database after mirroring was removed must all be applied to the mirror database before you can restart mirroring.</span></span>  
  
-   <span data-ttu-id="2b8cb-132">**Si vous n'envisagez pas de redémarrer la mise en miroir**</span><span class="sxs-lookup"><span data-stu-id="2b8cb-132">**If you do not intent to restart mirroring**</span></span>  
  
     <span data-ttu-id="2b8cb-133">Vous avez la possibilité de récupérer la base de données miroir initiale.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-133">Optionally, you can recover the former mirror database.</span></span> <span data-ttu-id="2b8cb-134">Sur l'instance de serveur qui était le serveur miroir, vous pouvez utiliser l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="2b8cb-134">On the server instance that was the mirror server, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    RESTORE DATABASE database_name WITH RECOVERY;  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="2b8cb-135">Si vous récupérez cette base de données, deux bases de données divergentes portant le même nom se trouvent alors en ligne.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-135">If you recover this database, two divergent databases with the same name are online.</span></span> <span data-ttu-id="2b8cb-136">Vous devez par conséquent vérifier que les clients ne peuvent accéder qu’à une seule d’entre elles, en général la base de données principale la plus récente.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-136">Therefore, you need to ensure that clients can access only one of them-typically the most recent principal database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2b8cb-137">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="2b8cb-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2b8cb-138">Suspendre ou reprendre une session de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2b8cb-138">Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;</span></span>](pause-or-resume-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="2b8cb-139">Supprimer le témoin d’une session de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2b8cb-139">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="2b8cb-140">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2b8cb-140">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="2b8cb-141">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b8cb-141">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="2b8cb-142">Exemple : Configuration de la mise en miroir de bases de données à l’aide de certificats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b8cb-142">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b8cb-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b8cb-143">See Also</span></span>  
 <span data-ttu-id="2b8cb-144">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2b8cb-144">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="2b8cb-145">[Configuration de la mise en miroir d’une base de données &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2b8cb-145">[Setting Up Database Mirroring &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="2b8cb-146">Groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2b8cb-146">AlwaysOn Availability Groups (SQL Server)</span></span>](../availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
