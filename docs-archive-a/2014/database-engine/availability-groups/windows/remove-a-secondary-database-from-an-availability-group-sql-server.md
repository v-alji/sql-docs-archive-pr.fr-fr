---
title: Supprimer une base de données secondaire d’un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.unjoindb.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], databases
ms.assetid: 4e51a570-58d7-4f01-9390-4198f3602576
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1c3de0afd73b46ae5594d26d1763f5bd78483efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603053"
---
# <a name="remove-a-secondary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="b2b63-102">Supprimer une base de données secondaire d'un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b2b63-102">Remove a Secondary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="b2b63-103">Cette rubrique explique comment supprimer une base de données secondaire d'un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2b63-103">This topic describes how to remove a secondary database from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="b2b63-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b2b63-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b2b63-105">Composants requis</span><span class="sxs-lookup"><span data-stu-id="b2b63-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="b2b63-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b2b63-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b2b63-107">**Pour supprimer une base de données secondaire, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b2b63-107">**To remove a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="b2b63-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2b63-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b2b63-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2b63-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="b2b63-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2b63-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="b2b63-111">**Suivi :**  [Après la suppression d'une base de données secondaire dans un groupe de disponibilité](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="b2b63-111">**Follow Up:**  [After Removing a Secondary Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b2b63-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b2b63-112">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>   
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="b2b63-113">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="b2b63-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="b2b63-114">Cette tâche est prise en charge sur les réplicas secondaires uniquement.</span><span class="sxs-lookup"><span data-stu-id="b2b63-114">This task is supported only on secondary replicas.</span></span> <span data-ttu-id="b2b63-115">Vous devez être connecté à l'instance de serveur qui héberge le réplica secondaire duquel la base de données doit être supprimée.</span><span class="sxs-lookup"><span data-stu-id="b2b63-115">You must be connected to the server instance that hosts the secondary replica from which the database is to be removed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b2b63-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b2b63-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b2b63-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b2b63-117">Permissions</span></span>  
 <span data-ttu-id="b2b63-118">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="b2b63-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b2b63-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2b63-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b2b63-120">**Pour supprimer une base de données secondaire dans un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="b2b63-120">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="b2b63-121">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica secondaire dont vous souhaitez supprimer une ou plusieurs bases de données secondaires, et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="b2b63-121">In Object Explorer, connect to the server instance that hosts the secondary replica from which you want to remove one or more secondary databases, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b2b63-122">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="b2b63-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="b2b63-123">Sélectionnez le groupe de disponibilité, puis développez le nœud **Bases de données de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="b2b63-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="b2b63-124">Cette étape varie selon que vous souhaitez supprimer plusieurs groupes de bases de données ou une seule base de données, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b2b63-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="b2b63-125">Pour supprimer plusieurs bases de données, utilisez le volet **Détails de l'Explorateur d'objets** pour afficher et sélectionner toutes les bases de données que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="b2b63-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="b2b63-126">Pour plus d’informations, consultez [Utiliser les détails de l’Explorateur d’objets pour surveiller les groupes de disponibilité &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b2b63-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="b2b63-127">Pour supprimer une seule base de données, sélectionnez-la dans le volet **Explorateur d'objets** ou le volet **Détails de l'Explorateur d'objets** .</span><span class="sxs-lookup"><span data-stu-id="b2b63-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="b2b63-128">Cliquez avec le bouton droit sur les bases de données sélectionnées, puis sélectionnez **Supprimer la base de données secondaire** dans le menu de commande.</span><span class="sxs-lookup"><span data-stu-id="b2b63-128">Right-click the selected database or databases, and select **Remove Secondary Database** in the command menu.</span></span>  
  
6.  <span data-ttu-id="b2b63-129">Dans la boîte de dialogue **Supprimer la base de données du groupe de disponibilité** , pour supprimer toutes les bases de données répertoriées, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2b63-129">In the **Remove Database from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="b2b63-130">Si vous ne souhaitez pas supprimer toutes les bases de données répertoriées, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="b2b63-130">If you do not want to remove all the listed databases, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b2b63-131">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2b63-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="b2b63-132">**Pour supprimer une base de données secondaire dans un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="b2b63-132">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="b2b63-133">Connectez-vous à l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="b2b63-133">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="b2b63-134">Utilisez la [clause SET HADR de l'instruction ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) comme suit :</span><span class="sxs-lookup"><span data-stu-id="b2b63-134">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="b2b63-135">ALTER DATABASE *nom_base_de_données* SET HADR OFF</span><span class="sxs-lookup"><span data-stu-id="b2b63-135">ALTER DATABASE *database_name* SET HADR OFF</span></span>  
  
     <span data-ttu-id="b2b63-136">où *nom_base_de_données* est le nom d’une base de données secondaire à supprimer du groupe de disponibilité auquel elle appartient.</span><span class="sxs-lookup"><span data-stu-id="b2b63-136">where *database_name* is the name of a secondary database to be removed from the availability group to which it belongs.</span></span>  
  
     <span data-ttu-id="b2b63-137">L’exemple suivant supprime la base de données secondaire locale *MyDb2* de son groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="b2b63-137">The following example removes the local secondary database *MyDb2* from its availability group.</span></span>  
  
    ```sql
    ALTER DATABASE MyDb2 SET HADR OFF;  
    GO  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="b2b63-138">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2b63-138">Using PowerShell</span></span>  
 <span data-ttu-id="b2b63-139">**Pour supprimer une base de données secondaire dans un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="b2b63-139">**To remove a secondary database from an availability group**</span></span>  
  
1.  <span data-ttu-id="b2b63-140">Remplacez le répertoire (`cd`) par l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="b2b63-140">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="b2b63-141">Utilisez l’applet de commande **Remove-SqlAvailabilityDatabase** , en spécifiant le nom de la base de données de disponibilité à supprimer du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="b2b63-141">Use the **Remove-SqlAvailabilityDatabase** cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="b2b63-142">Lorsque vous êtes connecté à une instance de serveur qui héberge un réplica secondaire, seule la base de données secondaire locale est supprimée du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="b2b63-142">When you are connected to a server instance that hosts a secondary replica, only the local secondary database is removed from the availability group.</span></span>  
  
     <span data-ttu-id="b2b63-143">Par exemple, la commande suivante supprime la base de données secondaire `MyDb8` du réplica secondaire hébergé par l’instance de serveur nommée `SecondaryComputer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="b2b63-143">For example, the following command removes the secondary database `MyDb8` from the secondary replica hosted by the server instance named `SecondaryComputer\Instance`.</span></span> <span data-ttu-id="b2b63-144">La synchronisation de données avec les bases de données secondaires supprimées s'arrête.</span><span class="sxs-lookup"><span data-stu-id="b2b63-144">Data synchronization to the removed secondary databases ceases.</span></span> <span data-ttu-id="b2b63-145">Cette commande n'affecte pas la base de données primaire ni aucune autre base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="b2b63-145">This command does not affect the primary database or any other secondary databases.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\SecondaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb8  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="b2b63-146">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2b63-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="b2b63-147">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b2b63-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="b2b63-148">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b2b63-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="b2b63-149">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2b63-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-database-from-an-availability-group"></a><a name="FollowUp"></a> <span data-ttu-id="b2b63-150">Suivi : Après la suppression d'une base de données secondaire dans un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="b2b63-150">Follow Up: After Removing a Secondary Database from an Availability Group</span></span>  
 <span data-ttu-id="b2b63-151">Lorsqu'une base de données secondaire est supprimée, elle n'est plus jointe au groupe de disponibilité et toutes les informations relatives à la base de données secondaire supprimée sont ignorées par le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="b2b63-151">When a secondary database is removed, it is no longer joined to the availability group and all information about the removed secondary database is discarded by the availability group.</span></span> <span data-ttu-id="b2b63-152">La base de données secondaire supprimée est placée dans l'état RESTORING.</span><span class="sxs-lookup"><span data-stu-id="b2b63-152">The removed secondary database is placed in the RESTORING state.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="b2b63-153">Pendant une courte période après la suppression d'une base de données secondaire, vous pouvez redémarrer la synchronisation des données AlwaysOn sur la base de données en la rejoignant au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="b2b63-153">For a short time after removing a secondary database, you might be able to restart AlwaysOn data synchronization on the database by re-joining it to the availability group.</span></span> <span data-ttu-id="b2b63-154">Pour plus d’informations, consultez [Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2b63-154">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
 <span data-ttu-id="b2b63-155">À ce stade, il existe d'autres méthodes pour traiter une base de données secondaire supprimée :</span><span class="sxs-lookup"><span data-stu-id="b2b63-155">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="b2b63-156">Si vous n'avez plus besoin de la base de données secondaire, vous pouvez la supprimer.</span><span class="sxs-lookup"><span data-stu-id="b2b63-156">If you no longer need the secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="b2b63-157">Pour plus d’informations, consultez [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) ou [Supprimer une base de données](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="b2b63-157">For more information, see [DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) or [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="b2b63-158">Si vous souhaitez accéder à une base de données secondaire supprimée après sa suppression du groupe de disponibilité, vous pouvez récupérer la base de données.</span><span class="sxs-lookup"><span data-stu-id="b2b63-158">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="b2b63-159">Toutefois, si vous récupérez une base de données secondaire supprimée, deux bases de données divergentes distinctes portant le même nom se trouvent alors en ligne.</span><span class="sxs-lookup"><span data-stu-id="b2b63-159">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="b2b63-160">Vous devez vous assurer que les clients ne peuvent accéder qu'à la base de données primaire actuelle.</span><span class="sxs-lookup"><span data-stu-id="b2b63-160">You must make sure that clients can access only the current primary database.</span></span>  
  
     <span data-ttu-id="b2b63-161">Pour plus d’informations, consultez [Récupérer une base de données sans restauration des données &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b2b63-161">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b63-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2b63-162">See Also</span></span>  
 <span data-ttu-id="b2b63-163">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b2b63-163">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="b2b63-164">Supprimer une base de données primaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b2b63-164">Remove a Primary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-primary-database-from-an-availability-group-sql-server.md)  
