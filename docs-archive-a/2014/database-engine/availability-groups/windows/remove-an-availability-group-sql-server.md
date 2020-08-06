---
title: Supprimer un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.deleteag.f1
helpviewer_keywords:
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], dropping
ms.assetid: 4b7f7f62-43a3-49db-a72e-22d4d7c2ddbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c17b7d5b362d8b4030d66ebf7ba0e425495410e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603048"
---
# <a name="remove-an-availability-group-sql-server"></a><span data-ttu-id="ddd2b-102">Supprimer un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ddd2b-102">Remove an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="ddd2b-103">Cette rubrique explique comment supprimer un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddd2b-103">This topic describes how to delete (drop) an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="ddd2b-104">Si une instance de serveur qui héberge l'un des réplicas de disponibilité est hors connexion lorsque vous supprimez un groupe de disponibilité, une fois de nouveau en ligne, l'instance de serveur supprimera le réplica de disponibilité local.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-104">If a server instance that hosts one of the availability replicas is offline when you delete an availability group, after coming online, the server instance will drop the local availability replica.</span></span> <span data-ttu-id="ddd2b-105">La suppression d'un groupe de disponibilité supprime tout écouteur du groupe de disponibilité associé.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-105">Dropping an availability group deletes any associated availability group listener.</span></span>  
  
 <span data-ttu-id="ddd2b-106">Notez qu'en cas de besoin, vous pouvez supprimer un groupe de disponibilité de tout nœud de clustering de basculement Windows Server (WSFC) qui possède les informations d'identification de sécurité correctes pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-106">Note that, if necessary, you can drop an availability group from any Windows Server Failover Clustering (WSFC) node that possesses the correct security credentials for the availability group.</span></span> <span data-ttu-id="ddd2b-107">Cela vous permet de supprimer un groupe de disponibilité lorsqu'il ne reste aucun de ses réplicas de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-107">This enables you to delete an availability group when none of its availability replicas remain.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ddd2b-108">si cela est possible, supprimez le groupe de disponibilité uniquement lorsque vous êtes connecté à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-108">If possible, remove the availability group only while connected to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="ddd2b-109">Si le groupe de disponibilité est supprimé du réplica principal, les modifications sont autorisées dans les bases de données primaires précédentes (sans protection haute disponibilité).</span><span class="sxs-lookup"><span data-stu-id="ddd2b-109">When the availability group is dropped from the primary replica, changes are allowed in the former primary databases (without high availability protection).</span></span> <span data-ttu-id="ddd2b-110">Le fait de supprimer un groupe de disponibilité d'un réplica secondaire conserve le réplica principal dans l'état RESTORING, et les modifications ne sont pas autorisées sur les bases de données.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-110">Deleting an availability group from a secondary replica leaves the primary replica in the RESTORING state, and changes are not allowed on the databases.</span></span>  
  
-   <span data-ttu-id="ddd2b-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ddd2b-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ddd2b-112">Recommandations et limitations</span><span class="sxs-lookup"><span data-stu-id="ddd2b-112">Limitations and Recommendations</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ddd2b-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ddd2b-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ddd2b-114">**Pour supprimer un groupe de disponibilité, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="ddd2b-114">**To delete an availability group, using:**</span></span>  
  
     [<span data-ttu-id="ddd2b-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ddd2b-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ddd2b-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ddd2b-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="ddd2b-117">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddd2b-117">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="ddd2b-118">Contenu connexe</span><span class="sxs-lookup"><span data-stu-id="ddd2b-118">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ddd2b-119">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ddd2b-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-recommendations"></a><a name="Restrictions"></a><span data-ttu-id="ddd2b-120">Limitations et recommandations</span><span class="sxs-lookup"><span data-stu-id="ddd2b-120">Limitations and Recommendations</span></span>  
  
-   <span data-ttu-id="ddd2b-121">Si le groupe de disponibilité est en ligne, sa suppression d'un réplica secondaire entraîne le passage du réplica principal à l'état RESTORING.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-121">When the availability group is online, deleting it from a secondary replica causes the primary replica to transition to the RESTORING state.</span></span> <span data-ttu-id="ddd2b-122">Par conséquent, et si cela est possible, ne supprimez le groupe de disponibilité que de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-122">Therefore, if possible, remove the availability group only from the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="ddd2b-123">Si vous supprimez un groupe de disponibilité d'un ordinateur qui a été supprimé ou évincé du cluster de basculement WSFC, le groupe de disponibilité est supprimé uniquement localement.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-123">If you delete an availability group from a computer that has been removed or evicted from the WSFC failover cluster, the availability group is only deleted locally.</span></span>  
  
-   <span data-ttu-id="ddd2b-124">Évitez de supprimer un groupe de disponibilité lorsque le cluster de clustering de basculement Windows Server (WSFC) n'a aucun quorum.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-124">Avoid dropping an availability group when the Windows Server Failover Clustering (WSFC) cluster has no quorum.</span></span> <span data-ttu-id="ddd2b-125">Si vous devez supprimer un groupe de disponibilité lorsque le cluster ne dispose pas de quorum, les métadonnées du groupe de disponibilité stockées dans le cluster nesont pas supprimées.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-125">If you must drop an availability group while the cluster lacks quorum, the metadata availability group that is stored in the cluster is not removed.</span></span> <span data-ttu-id="ddd2b-126">Après que le cluster a regagné le quorum, vous devez supprimer à nouveau le groupe de disponibilité pour le supprimer du cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-126">After the cluster regains quorum, you will need to drop the availability group again to remove it from the WSFC cluster.</span></span>  
  
-   <span data-ttu-id="ddd2b-127">Sur un réplica secondaire, DROP AVAILABILITY GROUP ne doit être utilisé qu'en cas d'urgence.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-127">On a secondary replica, DROP AVAILABILITY GROUP should only be used only for emergency purposes.</span></span> <span data-ttu-id="ddd2b-128">Cela est dû au fait que la suppression d'un groupe de disponibilité met le groupe de disponibilité hors connexion.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-128">This is because dropping an availability group takes the availability group offline.</span></span> <span data-ttu-id="ddd2b-129">Si vous supprimez le groupe de disponibilité d'un réplica secondaire, le réplica principal ne peut pas déterminer si l'état OFFLINE se produit en raison de la perte de quorum, d'un basculement forcé ou d'une commande DROP AVAILABILITY GROUP.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-129">If you drop the availability group from a secondary replica, the primary replica cannot determine whether the OFFLINE state occurred because of quorum loss, a forced failover, or a DROP AVAILABILITY GROUP command.</span></span> <span data-ttu-id="ddd2b-130">Le réplica principal passe à l'état RESTORING pour éviter un fractionnement possible des partitions.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-130">The primary replica transitions to the RESTORING state to prevent a possible split-brain situation.</span></span> <span data-ttu-id="ddd2b-131">Pour plus d’informations, consultez [Fonctionnement : comportements de DROP AVAILABILITY GROUP](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (blog des ingénieurs du Service clientèle et du Support technique de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="ddd2b-131">For more information, see [How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ddd2b-132">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ddd2b-132">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ddd2b-133">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ddd2b-133">Permissions</span></span>  
 <span data-ttu-id="ddd2b-134">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-134">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span> <span data-ttu-id="ddd2b-135">Pour supprimer un groupe de disponibilité qui n'est pas hébergé par l'instance de serveur local, vous avez besoin de l'autorisation CONTROL SERVER ou CONTROL sur ce groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-135">To drop an availability group that is not hosted by the local server instance you need CONTROL SERVER permission or CONTROL permission on that Availability Group.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ddd2b-136">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ddd2b-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ddd2b-137">**Pour supprimer un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="ddd2b-137">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="ddd2b-138">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal, si possible, ou connectez-vous à une autre instance de serveur qui est activée pour les groupes de disponibilité AlwaysOn sur un nœud WSFC comportant les informations d'identification de sécurité appropriées pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-138">In Object Explorer, connect to the server instance that hosts primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span> <span data-ttu-id="ddd2b-139">Développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-139">Expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ddd2b-140">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="ddd2b-140">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="ddd2b-141">Cette étape varie selon que vous souhaitez supprimer plusieurs groupes de disponibilité ou un seul, comme suit :</span><span class="sxs-lookup"><span data-stu-id="ddd2b-141">This step depends on whether you want to delete multiple availability groups or only one availability group, as follows:</span></span>  
  
    -   <span data-ttu-id="ddd2b-142">Pour supprimer plusieurs groupes de disponibilité (dont les réplicas principaux figurent sur l’instance de serveur connectée), utilisez le volet **Détails de l’Explorateur d’objets** pour afficher et sélectionner tous les groupes de disponibilité à supprimer.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-142">To delete multiple availability groups (whose primary replicas are on the connected server instance), use the **Object Explorer Details** pane to view and select all the availability groups that you want to delete.</span></span> <span data-ttu-id="ddd2b-143">Pour plus d’informations, consultez [Utiliser les détails de l’Explorateur d’objets pour surveiller les groupes de disponibilité &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ddd2b-143">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="ddd2b-144">Pour supprimer un seul groupe de disponibilité, sélectionnez-le dans le volet **Explorateur d'objets** ou le volet **Détails de l'Explorateur d'objets** .</span><span class="sxs-lookup"><span data-stu-id="ddd2b-144">To delete a single availability group, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
4.  <span data-ttu-id="ddd2b-145">Cliquez avec le bouton droit sur le ou les groupes de disponibilité sélectionnés, puis sélectionnez la commande **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="ddd2b-145">Right-click the selected availability group or groups, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="ddd2b-146">Dans la boîte de dialogue **Supprimer le groupe de disponibilité** , pour supprimer tous les groupes de disponibilité répertoriés, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-146">In the **Remove Availability Group** dialog box, to delete all the listed availability groups, click **OK**.</span></span> <span data-ttu-id="ddd2b-147">Si vous ne souhaitez pas supprimer tous les groupes de disponibilité répertoriés, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-147">If you do not want to remove all the listed availability groups, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ddd2b-148">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ddd2b-148">Using Transact-SQL</span></span>  
 <span data-ttu-id="ddd2b-149">**Pour supprimer un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="ddd2b-149">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="ddd2b-150">Connectez-vous à l'instance de serveur qui héberge le réplica principal, si possible, ou connectez-vous à une autre instance de serveur qui est activée pour les groupes de disponibilité AlwaysOn sur un nœud WSFC comportant les informations d'identification de sécurité appropriées pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-150">Connect to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="ddd2b-151">Utilisez l'instruction [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="ddd2b-151">Use the [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) statement, as follows</span></span>  
  
     <span data-ttu-id="ddd2b-152">DROP AVAILABILITY GROUP *nom_groupe*</span><span class="sxs-lookup"><span data-stu-id="ddd2b-152">DROP AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="ddd2b-153">où *nom_groupe* est le nom du groupe de disponibilité à supprimer.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-153">where *group_name* is the name of the availability group to be dropped.</span></span>  
  
     <span data-ttu-id="ddd2b-154">L'exemple suivant supprime le groupe de disponibilité `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="ddd2b-154">The following example deletes the `MyAG` availability group.</span></span>  
  
    ```sql
    DROP AVAILABILITY GROUP MyAG;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="ddd2b-155">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddd2b-155">Using PowerShell</span></span>  
 <span data-ttu-id="ddd2b-156">**Pour supprimer un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="ddd2b-156">**To delete an availability group**</span></span>  
  
 <span data-ttu-id="ddd2b-157">Dans le fournisseur PowerShell [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ddd2b-157">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="ddd2b-158">Remplacez le répertoire (`cd`) par celui de l'instance de serveur qui héberge le réplica principal, si possible, ou connectez-vous à une autre instance de serveur qui est activée pour les groupes de disponibilité AlwaysOn sur un nœud WSFC comportant les informations d'identification de sécurité appropriées pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-158">Change directory (`cd`) to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="ddd2b-159">Utilisez l’applet de commande **Remove-SqlAvailabilityGroup** .</span><span class="sxs-lookup"><span data-stu-id="ddd2b-159">Use the **Remove-SqlAvailabilityGroup** cmdlet.</span></span>  
  
     <span data-ttu-id="ddd2b-160">Par exemple, la commande suivante supprime le groupe de disponibilité nommé `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-160">For example, the following command removes the availability group named `MyAg`.</span></span> <span data-ttu-id="ddd2b-161">Cette commande peut être exécutée sur n'importe quelle instance de serveur qui héberge un réplica de disponibilité pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-161">This command can be executed on any server instance that hosts an availability replica for the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ddd2b-162">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ddd2b-162">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="ddd2b-163">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ddd2b-163">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="ddd2b-164">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ddd2b-164">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="ddd2b-165">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddd2b-165">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="ddd2b-166">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="ddd2b-166">Related Content</span></span>  
  
-   <span data-ttu-id="ddd2b-167">[Fonctionnement : comportements de DROP AVAILABILITY GROUP](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (blog des ingénieurs du Service clientèle et du Support technique de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ddd2b-167">[How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd2b-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ddd2b-168">See Also</span></span>  
 <span data-ttu-id="ddd2b-169">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ddd2b-169">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="ddd2b-170">Création et configuration des groupes de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ddd2b-170">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
