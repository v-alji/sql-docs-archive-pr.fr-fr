---
title: Supprimer une base de données primaire d’un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeprimarydb.f1
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 6d4ca31e-ddf0-44bf-be5e-a5da060bf096
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6fafaf6464431d68f8cfdf9dc9d8fa844a42a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603055"
---
# <a name="remove-a-primary-database-from-an-availability-group-sql-server"></a><span data-ttu-id="f9229-102">Supprimer une base de données primaire d'un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f9229-102">Remove a Primary Database from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="f9229-103">Cette rubrique décrit comment supprimer la base de données primaire et la ou les bases de données secondaires correspondantes d'un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9229-103">This topic describes how to remove both the primary database and the corresponding secondary database(s) from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="f9229-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f9229-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f9229-105">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="f9229-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="f9229-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f9229-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f9229-107">**Pour supprimer une base de données de disponibilité, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="f9229-107">**To remove an availability database, using:**</span></span>  
  
     [<span data-ttu-id="f9229-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9229-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f9229-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9229-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="f9229-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9229-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="f9229-111">**Suivi :**  [Après la suppression d'une base de données de disponibilité dans un groupe de disponibilité](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f9229-111">**Follow Up:**  [After Removing an Availability Database from an Availability Group](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f9229-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f9229-112">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="f9229-113">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="f9229-113">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="f9229-114">Cette tâche est prise en charge uniquement sur les réplicas principaux.</span><span class="sxs-lookup"><span data-stu-id="f9229-114">This task is supported only on primary replicas.</span></span> <span data-ttu-id="f9229-115">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f9229-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f9229-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f9229-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f9229-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f9229-117">Permissions</span></span>  
 <span data-ttu-id="f9229-118">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="f9229-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f9229-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9229-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f9229-120">**Pour supprimer une base de données de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="f9229-120">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="f9229-121">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal de la ou des bases de données à supprimer et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="f9229-121">In Object Explorer, connect to the server instance that hosts the primary replica of the database or databases to be removed, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f9229-122">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="f9229-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="f9229-123">Sélectionnez le groupe de disponibilité, puis développez le nœud **Bases de données de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="f9229-123">Select the availability group, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="f9229-124">Cette étape varie selon que vous souhaitez supprimer plusieurs groupes de bases de données ou une seule base de données, comme suit :</span><span class="sxs-lookup"><span data-stu-id="f9229-124">This step depends on whether you want to remove multiple databases groups or only one database, as follows:</span></span>  
  
    -   <span data-ttu-id="f9229-125">Pour supprimer plusieurs bases de données, utilisez le volet **Détails de l'Explorateur d'objets** pour afficher et sélectionner toutes les bases de données que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="f9229-125">To remove multiple databases, use the **Object Explorer Details** pane to view and select all the databases that you want to remove.</span></span> <span data-ttu-id="f9229-126">Pour plus d’informations, consultez [Utiliser les détails de l’Explorateur d’objets pour surveiller les groupes de disponibilité &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="f9229-126">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="f9229-127">Pour supprimer une seule base de données, sélectionnez-la dans le volet **Explorateur d'objets** ou le volet **Détails de l'Explorateur d'objets** .</span><span class="sxs-lookup"><span data-stu-id="f9229-127">To remove a single database, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="f9229-128">Cliquez avec le bouton droit sur la ou les bases de données sélectionnées, puis sélectionnez **Supprimer la base de données du groupe de disponibilité** dans le menu de commande.</span><span class="sxs-lookup"><span data-stu-id="f9229-128">Right-click the selected database or databases, and select **Remove Database from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="f9229-129">Dans la boîte de dialogue **Supprimer les bases de données du groupe de disponibilité** , pour supprimer toutes les bases de données répertoriées, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9229-129">In the **Remove Databases from Availability Group** dialog box, to remove all the listed databases, click **OK**.</span></span> <span data-ttu-id="f9229-130">Si vous ne souhaitez pas toutes les supprimer, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="f9229-130">If you do not want to remove all them, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f9229-131">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9229-131">Using Transact-SQL</span></span>  
 <span data-ttu-id="f9229-132">**Pour supprimer une base de données de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="f9229-132">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="f9229-133">Connectez-vous à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f9229-133">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="f9229-134">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="f9229-134">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="f9229-135">ALTER AVAILABILITY GROUP *nom_groupe* REMOVE DATABASE *nom_base_de_données_de_disponibilité*</span><span class="sxs-lookup"><span data-stu-id="f9229-135">ALTER AVAILABILITY GROUP *group_name* REMOVE DATABASE *availability_database_name*</span></span>  
  
     <span data-ttu-id="f9229-136">où *nom_groupe* est le nom du groupe de disponibilité et *nom_base_de_données* est le nom de la base de données à supprimer.</span><span class="sxs-lookup"><span data-stu-id="f9229-136">where *group_name* is the name of the availability group and *database_name* is the name of the database to be removed.</span></span>  
  
     <span data-ttu-id="f9229-137">L'exemple suivant supprime une bases de données nommée `Db6` du groupe de disponibilité `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="f9229-137">The following example removes a databases named `Db6` from the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE DATABASE Db6;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="f9229-138">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9229-138">Using PowerShell</span></span>  
 <span data-ttu-id="f9229-139">**Pour supprimer une base de données de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="f9229-139">**To remove an availability database**</span></span>  
  
1.  <span data-ttu-id="f9229-140">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f9229-140">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="f9229-141">Utilisez l'applet de commande `Remove-SqlAvailabilityDatabase`, en spécifiant le nom de la base de données de disponibilité à supprimer du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f9229-141">Use the `Remove-SqlAvailabilityDatabase` cmdlet, specifying the name of the availability database to be removed from the availability group.</span></span> <span data-ttu-id="f9229-142">Lorsque vous êtes connecté à l'instance de serveur qui héberge le réplica principal, la base de données primaire et ses bases de données secondaires correspondantes sont toutes supprimées du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f9229-142">When you are connected to the server instance that hosts the primary replica, the primary database and its corresponding secondary databases are all removed from the availability group.</span></span>  
  
     <span data-ttu-id="f9229-143">Par exemple, la commande suivante supprime la base de données de disponibilité `MyDb9` du groupe de disponibilité nommé `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="f9229-143">For example, the following command removes the availability database `MyDb9` from the availability group named `MyAg`.</span></span> <span data-ttu-id="f9229-144">Dans la mesure où la commande est exécutée sur l'instance de serveur qui héberge le réplica principal, la base de données primaire et toutes ses bases de données secondaires correspondantes sont supprimées du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f9229-144">Because the command is executed on the server instance that hosts the primary replica, the primary database and all its corresponding secondary databases are removed from the availability group.</span></span> <span data-ttu-id="f9229-145">La synchronisation de données ne se produira plus pour cette base de données sur aucun réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="f9229-145">Data synchronization will no longer occur for this database on any secondary replica.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\PrimaryComputer\InstanceName\AvailabilityGroups\MyAg\Databases\MyDb9  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f9229-146">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9229-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f9229-147">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f9229-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="f9229-148">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f9229-148">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="f9229-149">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9229-149">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-an-availability-database-from-an-availability-group"></a><a name="FollowUp"></a> <span data-ttu-id="f9229-150">Suivi : Après la suppression d'une base de données de disponibilité dans un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f9229-150">Follow Up: After Removing an Availability Database from an Availability Group</span></span>  
 <span data-ttu-id="f9229-151">La suppression d'une base de données de disponibilité de son groupe de disponibilité met fin à la synchronisation des données entre l'ancienne base de données primaire et les bases de données secondaires correspondantes.</span><span class="sxs-lookup"><span data-stu-id="f9229-151">Removing an availability database from its availability group ends data synchronization between the former primary database and the corresponding secondary databases.</span></span> <span data-ttu-id="f9229-152">L'ancienne base de données primaire reste en ligne.</span><span class="sxs-lookup"><span data-stu-id="f9229-152">The former primary database remains online.</span></span> <span data-ttu-id="f9229-153">Chaque base de données secondaire correspondante est placée dans l'état RESTORING.</span><span class="sxs-lookup"><span data-stu-id="f9229-153">Every corresponding secondary database is placed in the RESTORING state.</span></span>  
  
 <span data-ttu-id="f9229-154">À ce stade, il existe d'autres méthodes pour traiter une base de données secondaire supprimée :</span><span class="sxs-lookup"><span data-stu-id="f9229-154">At this point there are alternative ways of dealing with a removed secondary database:</span></span>  
  
-   <span data-ttu-id="f9229-155">Si vous n'avez plus besoin d'une base de données secondaire particulière, vous pouvez la supprimer.</span><span class="sxs-lookup"><span data-stu-id="f9229-155">If you no longer need a given secondary database, you can drop it.</span></span>  
  
     <span data-ttu-id="f9229-156">Pour plus d’informations, consultez [Supprimer une base de données](../../../relational-databases/databases/delete-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="f9229-156">For more information, see [Delete a Database](../../../relational-databases/databases/delete-a-database.md).</span></span>  
  
-   <span data-ttu-id="f9229-157">Si vous souhaitez accéder à une base de données secondaire supprimée après sa suppression du groupe de disponibilité, vous pouvez récupérer la base de données.</span><span class="sxs-lookup"><span data-stu-id="f9229-157">If you want to access a removed secondary database after it has been removed from the availability group, you can recover the database.</span></span> <span data-ttu-id="f9229-158">Toutefois, si vous récupérez une base de données secondaire supprimée, deux bases de données divergentes distinctes portant le même nom se trouvent alors en ligne.</span><span class="sxs-lookup"><span data-stu-id="f9229-158">However, if you recover a removed secondary database, two divergent, independent databases that have the same name are online.</span></span> <span data-ttu-id="f9229-159">Vous devez vous assurer que les clients ne peuvent accéder qu'à une seule d'entre elles, généralement la base de données primaire la plus récente.</span><span class="sxs-lookup"><span data-stu-id="f9229-159">You must make sure that clients can access only one of them, typically the most recent primary database.</span></span>  
  
     <span data-ttu-id="f9229-160">Pour plus d’informations, consultez [Récupérer une base de données sans restauration des données &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f9229-160">For more information, see [Recover a Database Without Restoring Data &#40;Transact-SQL&#41;](../../../relational-databases/backup-restore/recover-a-database-without-restoring-data-transact-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9229-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9229-161">See Also</span></span>  
 <span data-ttu-id="f9229-162">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f9229-162">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f9229-163">Supprimer une base de données secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f9229-163">Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
