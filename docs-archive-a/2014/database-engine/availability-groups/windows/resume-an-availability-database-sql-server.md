---
title: Reprendre une base de données de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.resumedatamove.f1
helpviewer_keywords:
- Availability Groups [SQL Server], resuming a database
- secondary databases [SQL Server], in availability group
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], databases
ms.assetid: 20e9147b-e985-4caa-910e-fc4b38dbf9a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a2279940c2502a310e9dac4448bd6029b6e13dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707896"
---
# <a name="resume-an-availability-database-sql-server"></a><span data-ttu-id="8f178-102">Reprendre une base de données de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8f178-102">Resume an Availability Database (SQL Server)</span></span>
  <span data-ttu-id="8f178-103">Vous pouvez reprendre une base de données de disponibilité interrompue dans [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f178-103">You can resume a suspended availability database in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="8f178-104">La reprise d'une base de données interrompue met la base de données dans l'état SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="8f178-104">Resuming a suspended database puts the database into the SYNCHRONIZING state.</span></span> <span data-ttu-id="8f178-105">La reprise de la base de données primaire rétablit également toutes ses bases de données secondaires qui ont été interrompues suite à l'interruption de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="8f178-105">Resuming the primary database also resumes any of its secondary databases that were suspended as the result of suspending the primary database.</span></span> <span data-ttu-id="8f178-106">Si une base de données secondaire a été interrompue localement, depuis l'instance de serveur qui héberge le réplica secondaire, cette base de données secondaire doit être reprise localement.</span><span class="sxs-lookup"><span data-stu-id="8f178-106">If any secondary database was suspended locally, from the server instance that hosts the secondary replica, that secondary database must be resumed locally.</span></span> <span data-ttu-id="8f178-107">Une fois qu'une base de données secondaire particulière et que la base de données principale correspondante sont dans l'état SYNCHRONIZING, la synchronisation des données reprend sur la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="8f178-107">Once a given secondary database and the corresponding primary database are in the SYNCHRONIZING state, data synchronization resumes on the secondary database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f178-108">La suspension et la reprise d'une base de données secondaire AlwaysOn n'affectent pas directement la disponibilité de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="8f178-108">Suspending and resuming an AlwaysOn secondary database does not directly affect the availability of the primary database.</span></span> <span data-ttu-id="8f178-109">Toutefois, l'interruption d'une base de données secondaire peut avoir un impact sur la redondance et les fonctions de basculement de la base de données primaire, jusqu'à ce que la base de données secondaire interrompue reprenne.</span><span class="sxs-lookup"><span data-stu-id="8f178-109">However, suspending a secondary database can impact redundancy and failover capabilities for the primary database, until the suspended secondary database is resumed.</span></span> <span data-ttu-id="8f178-110">Ce comportement diffère de la mise en miroir de bases de données dans laquelle l'état de mise en miroir est interrompu à la fois sur la base de données miroir et la base de données principale tant que la mise en miroir n'a pas repris.</span><span class="sxs-lookup"><span data-stu-id="8f178-110">This is in contrast to database mirroring, where the mirroring state is suspended on both the mirror database and the principal database until mirroring is resumed.</span></span> <span data-ttu-id="8f178-111">L'interruption d'une base de données principale AlwaysOn interrompt le déplacement des données sur toutes les bases de données secondaires correspondantes, et les capacités de redondance et de basculement cessent pour cette base de données tant que la base de données principale n'a pas repris.</span><span class="sxs-lookup"><span data-stu-id="8f178-111">Suspending an AlwaysOn primary database suspends data movement on all the corresponding secondary databases, and redundancy and failover capabilities cease for that database until the primary database is resumed.</span></span>  
  
-   <span data-ttu-id="8f178-112">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="8f178-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8f178-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8f178-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8f178-114">Composants requis</span><span class="sxs-lookup"><span data-stu-id="8f178-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="8f178-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8f178-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8f178-116">**Pour reprendre une base de données secondaire, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="8f178-116">**To resume a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="8f178-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f178-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8f178-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8f178-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="8f178-119">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f178-119">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="8f178-120">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="8f178-120">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8f178-121">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8f178-121">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8f178-122">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8f178-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8f178-123">Une commande RESUME retourne dès qu'elle est acceptée par le réplica qui héberge la base de données cible, mais en réalité, la reprise de la base de données se produit de façon asynchrone.</span><span class="sxs-lookup"><span data-stu-id="8f178-123">A RESUME command returns as soon as it has been accepted by the replica that hosts the target database, but actually resuming the database occurs asynchronously.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="8f178-124">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="8f178-124">Prerequisites</span></span>  
  
-   <span data-ttu-id="8f178-125">Vous devez être connecté à l'instance de serveur qui héberge la base de données à reprendre.</span><span class="sxs-lookup"><span data-stu-id="8f178-125">You must be connected to the server instance that hosts the database to be resumed.</span></span>  
  
-   <span data-ttu-id="8f178-126">Le groupe de disponibilité doit être en ligne.</span><span class="sxs-lookup"><span data-stu-id="8f178-126">The availability group must be online.</span></span>  
  
-   <span data-ttu-id="8f178-127">La base de données primaire doit être en ligne et disponible.</span><span class="sxs-lookup"><span data-stu-id="8f178-127">The primary database must be online and available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8f178-128">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8f178-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8f178-129">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8f178-129">Permissions</span></span>  
 <span data-ttu-id="8f178-130">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="8f178-130">Requires ALTER permission on the database.</span></span>  
  
 <span data-ttu-id="8f178-131">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="8f178-131">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8f178-132">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f178-132">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8f178-133">**Pour reprendre une base de données secondaire**</span><span class="sxs-lookup"><span data-stu-id="8f178-133">**To resume a secondary database**</span></span>  
  
1.  <span data-ttu-id="8f178-134">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica de disponibilité sur lequel vous souhaitez reprendre une base de données et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="8f178-134">In Object Explorer, connect to the server instance that hosts the availability replica on which you want to resume a database, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="8f178-135">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="8f178-135">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="8f178-136">Développez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="8f178-136">Expand the availability group.</span></span>  
  
4.  <span data-ttu-id="8f178-137">Développez le nœud **Bases de données de disponibilité** , cliquez avec le bouton droit sur la base de données, puis sélectionnez **Reprendre le déplacement des données**.</span><span class="sxs-lookup"><span data-stu-id="8f178-137">Expand the **Availability Databases** node, right-click the database, and click **Resume Data Movement**.</span></span>  
  
5.  <span data-ttu-id="8f178-138">Dans la boîte de dialogue **Reprendre le déplacement des données** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f178-138">In the **Resume Data Movement** dialog box, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f178-139">Pour reprendre des bases de données supplémentaires sur cet emplacement de réplica, répétez les étapes 4 et 5 pour chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="8f178-139">To resume additional databases on this replica location, repeat steps 4 and 5 for each database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8f178-140">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8f178-140">Using Transact-SQL</span></span>  
 <span data-ttu-id="8f178-141">**Pour reprendre une base de données secondaire qui a été suspendue localement**</span><span class="sxs-lookup"><span data-stu-id="8f178-141">**To resume a secondary database that was suspended locally**</span></span>  
  
1.  <span data-ttu-id="8f178-142">Connectez-vous à l'instance de serveur qui héberge le réplica secondaire dont vous souhaitez reprendre la base de données.</span><span class="sxs-lookup"><span data-stu-id="8f178-142">Connect to the server instance that hosts the secondary replica whose database you want to resume.</span></span>  
  
2.  <span data-ttu-id="8f178-143">Reprenez la base de données secondaire à l’aide de l’instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)suivante :</span><span class="sxs-lookup"><span data-stu-id="8f178-143">Resume the secondary database by using the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr)statement:</span></span>  
  
     <span data-ttu-id="8f178-144">Instruction ALTER DATABASE *database_name* Set Hadr Resume</span><span class="sxs-lookup"><span data-stu-id="8f178-144">ALTER DATABASE *database_name* SET HADR RESUME</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="8f178-145">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f178-145">Using PowerShell</span></span>  

### <a name="to-resume-a-secondary-database"></a><span data-ttu-id="8f178-146">Pour reprendre une base de données secondaire</span><span class="sxs-lookup"><span data-stu-id="8f178-146">To resume a secondary database</span></span>
  
1.  <span data-ttu-id="8f178-147">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica dont vous souhaitez reprendre la base de données.</span><span class="sxs-lookup"><span data-stu-id="8f178-147">Change directory (`cd`) to the server instance that hosts the replica whose database you want to resume.</span></span> <span data-ttu-id="8f178-148">Pour plus d'informations, consultez [Conditions préalables requises](#Prerequisites), plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="8f178-148">For more information, see [Prerequisites](#Prerequisites), earlier in this topic.</span></span>  
  
2.  <span data-ttu-id="8f178-149">Utilisez l’applet de commande **Resume-SqlAvailabilityDatabase** pour reprendre le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="8f178-149">Use the **Resume-SqlAvailabilityDatabase** cmdlet to resume the availability group.</span></span>  
  
     <span data-ttu-id="8f178-150">Par exemple, la commande suivante reprend la synchronisation des données pour la base de données de disponibilité `MyDb3` dans le groupe de disponibilité `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="8f178-150">For example, the following command resumes data synchronization for the availability database `MyDb3` in the availability group `MyAg`.</span></span>  
  
    ```powershell
    Resume-SqlAvailabilityDatabase -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\Databases\MyDb3  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f178-151">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f178-151">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="8f178-152">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="8f178-152">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="8f178-153">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8f178-153">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="8f178-154">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f178-154">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="8f178-155">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="8f178-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="8f178-156">Interrompre une base de données de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f178-156">Suspend an Availability Database &#40;SQL Server&#41;</span></span>](suspend-an-availability-database-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="8f178-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f178-157">See Also</span></span>  
 [<span data-ttu-id="8f178-158">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f178-158">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
