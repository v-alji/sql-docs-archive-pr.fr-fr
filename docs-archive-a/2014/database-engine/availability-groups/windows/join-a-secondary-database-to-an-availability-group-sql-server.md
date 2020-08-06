---
title: Joindre une base de données secondaire à un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joindbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: fd7efe79-c1f9-497d-bfe7-b2a2b2321cf5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0d79325bcde33d13688003de079a42a9601cc41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604718"
---
# <a name="join-a-secondary-database-to-an-availability-group-sql-server"></a><span data-ttu-id="9868c-102">Joindre une base de données secondaire à un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9868c-102">Join a Secondary Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="9868c-103">Cette rubrique explique comment joindre une base de données secondaire à un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9868c-103">This topic explains how to join a secondary database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="9868c-104">Après avoir préparé une base de données secondaire pour un réplica secondaire, vous devez joindre la base de données au groupe de disponibilité dès que possible.</span><span class="sxs-lookup"><span data-stu-id="9868c-104">After you prepare a secondary database for a secondary replica, you need to join the database to the availability group as soon as possible.</span></span> <span data-ttu-id="9868c-105">Cette opération lance le déplacement des données entre la base de données primaire correspondante et la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="9868c-105">This will start data movement from the corresponding primary database to the secondary database.</span></span>  
  
-   <span data-ttu-id="9868c-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="9868c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9868c-107">Composants requis</span><span class="sxs-lookup"><span data-stu-id="9868c-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="9868c-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9868c-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9868c-109">**Pour préparer une base de données secondaire, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="9868c-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="9868c-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9868c-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9868c-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9868c-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="9868c-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9868c-112">PowerShell</span></span>](#PowerShellProcedure)  
  
> [!NOTE]  
>  <span data-ttu-id="9868c-113">Pour plus d’informations sur ce qui se produit après qu’une base de données secondaire a rejoint le groupe, consultez [vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9868c-113">For information about what happens after a secondary database joins the group, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9868c-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="9868c-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9868c-115">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="9868c-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="9868c-116">Vous devez être connecté à l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="9868c-116">You must be connected to the server instance that hosts the secondary replica.</span></span>  
  
-   <span data-ttu-id="9868c-117">Le réplica secondaire doit déjà être joint au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9868c-117">The secondary replica must already be joined to the availability group.</span></span> <span data-ttu-id="9868c-118">Pour plus d’informations, consultez [Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9868c-118">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
-   <span data-ttu-id="9868c-119">La base de données secondaire doit avoir été préparée récemment.</span><span class="sxs-lookup"><span data-stu-id="9868c-119">The secondary database must have been prepared recently.</span></span> <span data-ttu-id="9868c-120">Pour plus d’informations, consultez [Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9868c-120">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9868c-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9868c-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9868c-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="9868c-122">Permissions</span></span>  
 <span data-ttu-id="9868c-123">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="9868c-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9868c-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9868c-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9868c-125">**Pour joindre une base de données secondaire à un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9868c-125">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="9868c-126">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica secondaire et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="9868c-126">In Object Explorer, connect to the server instance that hosts the secondary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9868c-127">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="9868c-127">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="9868c-128">Développez le groupe de disponibilité que vous souhaitez modifier, puis développez le nœud **Bases de données de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="9868c-128">Expand the availability group that you want to change, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="9868c-129">Cliquez avec le bouton droit sur la base de données, puis cliquez sur **Joindre au groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="9868c-129">Right-click the database, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="9868c-130">Cette opération ouvre la boîte de dialogue **Joindre les bases de données au groupe de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="9868c-130">This opens the **Join Databases to Availability Group** dialog box.</span></span> <span data-ttu-id="9868c-131">Vérifiez le nom du groupe de disponibilité affiché dans la barre de titre, ainsi que le nom de la ou des bases de données affichées dans la grille, puis cliquez sur **OK**, ou cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="9868c-131">Verify the availability group name, which is displayed on the title bar, and database name or names displayed in the grid, and click **OK**, or click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9868c-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9868c-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="9868c-133">**Pour joindre une base de données secondaire à un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9868c-133">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="9868c-134">Connectez-vous à l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="9868c-134">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="9868c-135">Utilisez la [clause SET HADR de l'instruction ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) comme suit :</span><span class="sxs-lookup"><span data-stu-id="9868c-135">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="9868c-136">ALTER DATABASE *nom_base_de_données* SET HADR AVAILABILITY GROUP = *nom_groupe*</span><span class="sxs-lookup"><span data-stu-id="9868c-136">ALTER DATABASE *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>  
  
     <span data-ttu-id="9868c-137">où *nom_base_de_données* est le nom d’une base de données à joindre et *nom_groupe* est le nom du groupe de disponibilité .</span><span class="sxs-lookup"><span data-stu-id="9868c-137">where *database_name* is the name of a database to be joined and *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="9868c-138">L'exemple suivant joint la base de données secondaire, `Db1`, au réplica secondaire local du groupe de disponibilité `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="9868c-138">The following example joins the secondary database, `Db1`, to the local secondary replica of the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER DATABASE Db1 SET HADR AVAILABILITY GROUP = MyAG;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="9868c-139">Pour consulter cette instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] utilisée en contexte, consultez [Créer un groupe de disponibilité &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9868c-139">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9868c-140">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="9868c-140">Using PowerShell</span></span>  
 <span data-ttu-id="9868c-141">**Pour joindre une base de données secondaire à un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9868c-141">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="9868c-142">Remplacez le répertoire (`cd`) par l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="9868c-142">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="9868c-143">Utilisez l'applet de commande `Add-SqlAvailabilityDatabase` pour joindre une ou plusieurs bases de données secondaires au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9868c-143">Use the `Add-SqlAvailabilityDatabase` cmdlet to join one or more secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="9868c-144">Par exemple, la commande suivante joint une base de données secondaire, `Db1`, au groupe de disponibilité `MyAG` sur l'une des instances de serveur qui héberge un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="9868c-144">For example, the following command joins a secondary database, `Db1`, to the availability group `MyAG` on one of the server instances that hosts a secondary replica.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase -Path SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAG -Database "Db1"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="9868c-145">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9868c-145">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="9868c-146">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9868c-146">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="9868c-147">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9868c-147">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="9868c-148">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="9868c-148">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9868c-149">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9868c-149">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9868c-150">Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9868c-150">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="9868c-151">Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9868c-151">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="9868c-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9868c-152">See Also</span></span>  
 <span data-ttu-id="9868c-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9868c-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="9868c-154">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9868c-154">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="9868c-155">Résoudre les problèmes de configuration de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;supprimé</span><span class="sxs-lookup"><span data-stu-id="9868c-155">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
