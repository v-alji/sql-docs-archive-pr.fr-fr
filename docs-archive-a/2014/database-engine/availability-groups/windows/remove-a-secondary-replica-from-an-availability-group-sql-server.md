---
title: Supprimer un réplica secondaire d’un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removesecondaryar.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 35ddc8b6-3e7c-4417-9a0a-d4987a09ddf7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e3f2b35ec9cf27f2f7b23714a41665f2709837a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603050"
---
# <a name="remove-a-secondary-replica-from-an-availability-group-sql-server"></a><span data-ttu-id="03ee5-102">Supprimer un réplica secondaire d'un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="03ee5-102">Remove a Secondary Replica from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="03ee5-103">Cette rubrique explique comment supprimer un réplica secondaire d'un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03ee5-103">This topic describes how to remove a secondary replica from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="03ee5-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="03ee5-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="03ee5-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="03ee5-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="03ee5-106">Composants requis</span><span class="sxs-lookup"><span data-stu-id="03ee5-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="03ee5-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="03ee5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="03ee5-108">**Pour supprimer un réplica secondaire, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="03ee5-108">**To remove a secondary replica, using:**</span></span>  
  
     [<span data-ttu-id="03ee5-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03ee5-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="03ee5-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03ee5-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="03ee5-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="03ee5-111">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="03ee5-112">**Suivi :**  [Après avoir supprimé un réplica secondaire](#PostBestPractices)</span><span class="sxs-lookup"><span data-stu-id="03ee5-112">**Follow Up:**  [After Removing a Secondary Replica](#PostBestPractices)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03ee5-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="03ee5-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="03ee5-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="03ee5-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="03ee5-115">Cette tâche est prise en charge uniquement sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="03ee5-115">This task is supported only on the primary replica.</span></span>  
  
-   <span data-ttu-id="03ee5-116">Seul un réplica secondaire peut être supprimé d'un groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="03ee5-116">Only a secondary replica can be removed from an availability group.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="03ee5-117">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="03ee5-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="03ee5-118">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="03ee5-118">You must be connected to the server instance that hosts the primary replica of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03ee5-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="03ee5-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03ee5-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="03ee5-120">Permissions</span></span>  
 <span data-ttu-id="03ee5-121">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="03ee5-121">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03ee5-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03ee5-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="03ee5-123">**Pour supprimer un réplica secondaire**</span><span class="sxs-lookup"><span data-stu-id="03ee5-123">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="03ee5-124">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="03ee5-124">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="03ee5-125">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="03ee5-125">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="03ee5-126">Sélectionnez le groupe de disponibilité, puis développez le nœud **Réplicas de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="03ee5-126">Select the availability group, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="03ee5-127">Cette étape varie selon que vous souhaitez supprimer un seul ou plusieurs réplicas, comme suit :</span><span class="sxs-lookup"><span data-stu-id="03ee5-127">This step depends on whether you want to remove multiple replicas or only one replica, as follows:</span></span>  
  
    -   <span data-ttu-id="03ee5-128">Pour supprimer plusieurs réplicas, utilisez le volet **Détails de l'Explorateur d'objets** pour afficher et sélectionner tous les réplicas à supprimer.</span><span class="sxs-lookup"><span data-stu-id="03ee5-128">To remove multiple replicas, use the **Object Explorer Details** pane to view and select all the replicas that you want to remove.</span></span> <span data-ttu-id="03ee5-129">Pour plus d’informations, consultez [Utiliser les détails de l’Explorateur d’objets pour surveiller les groupes de disponibilité &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="03ee5-129">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="03ee5-130">Pour supprimer un seul réplica, sélectionnez-le dans le volet **Explorateur d'objets** ou le volet **Détails de l'Explorateur d'objets** .</span><span class="sxs-lookup"><span data-stu-id="03ee5-130">To remove a single replica, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="03ee5-131">Cliquez avec le bouton droit sur le réplica ou les réplicas secondaires sélectionnés, puis sélectionnez **Supprimer du groupe de disponibilité** dans le menu de commande.</span><span class="sxs-lookup"><span data-stu-id="03ee5-131">Right-click the selected secondary replica or replicas, and select **Remove from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="03ee5-132">Dans la boîte de dialogue **Supprimer les réplicas secondaires du groupe de disponibilité** , pour supprimer tous les réplicas secondaires répertoriés, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="03ee5-132">In the **Remove Secondary Replicas from Availability Group** dialog box, to remove all the listed secondary replicas, click **OK**.</span></span> <span data-ttu-id="03ee5-133">Si vous ne souhaitez pas supprimer tous les réplicas répertoriés, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="03ee5-133">If you do not want to remove all the listed replicas, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="03ee5-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="03ee5-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="03ee5-135">**Pour supprimer un réplica secondaire**</span><span class="sxs-lookup"><span data-stu-id="03ee5-135">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="03ee5-136">Connectez-vous à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="03ee5-136">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="03ee5-137">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="03ee5-137">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="03ee5-138">ALTER AVAILABILITY GROUP *nom_groupe* REMOVE REPLICA ON '*nom_instance*' [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="03ee5-138">ALTER AVAILABILITY GROUP *group_name* REMOVE REPLICA ON '*instance_name*' [,...*n*]</span></span>  
  
     <span data-ttu-id="03ee5-139">où *nom_groupe* est le nom du groupe de disponibilité et *nom_instance* est l'instance de serveur où se trouve le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="03ee5-139">where *group_name* is the name of the availability group and *instance_name* is the server instance where the secondary replica is located.</span></span>  
  
     <span data-ttu-id="03ee5-140">L’exemple suivant supprime un réplica secondaire du groupe de disponibilité *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="03ee5-140">The following example removes a secondary replica from the *MyAG* availability group.</span></span> <span data-ttu-id="03ee5-141">Le réplica secondaire cible se trouve sur une instance de serveur nommée *HADR_INSTANCE* sur un ordinateur nommé *COMPUTER02*.</span><span class="sxs-lookup"><span data-stu-id="03ee5-141">The target secondary replica is located on a server instance named *HADR_INSTANCE* on a computer named *COMPUTER02*.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE REPLICA ON 'COMPUTER02\HADR_INSTANCE';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="03ee5-142">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="03ee5-142">Using PowerShell</span></span>  
 <span data-ttu-id="03ee5-143">**Pour supprimer un réplica secondaire**</span><span class="sxs-lookup"><span data-stu-id="03ee5-143">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="03ee5-144">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="03ee5-144">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="03ee5-145">Utilisez l’applet de commande **Remove-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="03ee5-145">Use the **Remove-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="03ee5-146">Par exemple, la commande suivante supprime le réplica de disponibilité sur le serveur `MyReplica` du groupe de disponibilité nommé `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="03ee5-146">For example, the following command removes the availability replica on the server `MyReplica` from the availability group named `MyAg`.</span></span>  <span data-ttu-id="03ee5-147">Cette commande doit être exécutée sur l'instance de serveur qui héberge le réplica principal du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="03ee5-147">This command must be run on the server instance that hosts the primary replica of the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityReplica -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="03ee5-148">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03ee5-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="03ee5-149">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="03ee5-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="03ee5-150">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="03ee5-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="03ee5-151">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="03ee5-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-replica"></a><a name="PostBestPractices"></a> <span data-ttu-id="03ee5-152">Suivi : Après avoir supprimé un réplica secondaire</span><span class="sxs-lookup"><span data-stu-id="03ee5-152">Follow Up: After Removing a Secondary Replica</span></span>  
 <span data-ttu-id="03ee5-153">Si vous spécifiez un réplica qui n'est pas disponible actuellement, lorsque le réplica est mis en ligne, on découvre qu'il a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="03ee5-153">If you specify a replica that is currently unavailable, when the replica comes online, it will discover that it has been removed.</span></span>  
  
 <span data-ttu-id="03ee5-154">La suppression d'un réplica provoque l'arrêt de la réception des données.</span><span class="sxs-lookup"><span data-stu-id="03ee5-154">Removing a replica causes it to stop receiving data.</span></span> <span data-ttu-id="03ee5-155">Après qu'un réplica secondaire a confirmé qu'il a été supprimé du magasin global, le réplica supprime les paramètres de groupe de disponibilité de ses bases de données, lesquelles demeurent sur l'instance de serveur locale dans l'état RECOVERING.</span><span class="sxs-lookup"><span data-stu-id="03ee5-155">After a secondary replica confirms that it has been removed from the global store, the replica removes the availability group settings from its databases, which remain on the local server instance in the RECOVERING state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ee5-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03ee5-156">See Also</span></span>  
 <span data-ttu-id="03ee5-157">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="03ee5-157">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="03ee5-158">[Ajoutez un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="03ee5-158">[Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span></span>  
 [<span data-ttu-id="03ee5-159">Supprimer un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="03ee5-159">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
