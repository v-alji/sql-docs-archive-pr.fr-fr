---
title: Utiliser le tableau de bord AlwaysOn (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
- Availability Groups [SQL Server], dashboard
ms.assetid: c9ba2589-139e-42bc-99e1-94546717c64d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4ce0072bcd6642dcb4f3ac63e04c98786bd550e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603043"
---
# <a name="use-the-alwayson-dashboard-sql-server-management-studio"></a><span data-ttu-id="aed7c-102">Utiliser le tableau de bord AlwaysOn (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="aed7c-102">Use the AlwaysOn Dashboard (SQL Server Management Studio)</span></span>
  <span data-ttu-id="aed7c-103">Les administrateurs de base de données utilisent le tableau de bord AlwaysOn pour afficher l'intégrité d'un groupe de disponibilité AlwaysOn et de ses réplicas de disponibilité et bases de données dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aed7c-103">Database administrators use the AlwaysOn Dashboard to obtains an at-a-glance view the health of an AlwaysOn availability group and its availability replicas and databases in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="aed7c-104">Parmi les utilisations courantes du tableau de bord AlwaysOn, citons :</span><span class="sxs-lookup"><span data-stu-id="aed7c-104">Some of the typical uses for the AlwaysOn Dashboard are:</span></span>  
  
-   <span data-ttu-id="aed7c-105">Choix d'un réplica pour un basculement manuel.</span><span class="sxs-lookup"><span data-stu-id="aed7c-105">Choosing a replica for a manual failover.</span></span>  
  
-   <span data-ttu-id="aed7c-106">Estimation de la perte de données en cas de basculement forcé.</span><span class="sxs-lookup"><span data-stu-id="aed7c-106">Estimating data loss if you force failover.</span></span>  
  
-   <span data-ttu-id="aed7c-107">Évaluation des performances de synchronisation des données.</span><span class="sxs-lookup"><span data-stu-id="aed7c-107">Evaluating data-synchronization performance.</span></span>  
  
-   <span data-ttu-id="aed7c-108">Évaluation de l'impact sur les performances d'un réplica secondaire avec validation synchrone</span><span class="sxs-lookup"><span data-stu-id="aed7c-108">Evaluating the performance impact of a synchronous-commit secondary replica</span></span>  
  
 <span data-ttu-id="aed7c-109">Le tableau de bord AlwaysOn fournit les états principaux et les indicateurs de performance du groupe de disponibilité et vous permet ainsi de prendre facilement des décisions opérationnelles en matière de haute disponibilité sur la base des types d'informations suivants.</span><span class="sxs-lookup"><span data-stu-id="aed7c-109">The AlwaysOn Dashboard provides key availability group states and performance indicators allowing you to easily make high availability operational decisions using the following types of information.</span></span>  
  
-   <span data-ttu-id="aed7c-110">État de restauration de réplica</span><span class="sxs-lookup"><span data-stu-id="aed7c-110">Replica roll-up state</span></span>  
  
-   <span data-ttu-id="aed7c-111">Mode et état de synchronisation</span><span class="sxs-lookup"><span data-stu-id="aed7c-111">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="aed7c-112">Estimer la perte de données</span><span class="sxs-lookup"><span data-stu-id="aed7c-112">Estimate Data Loss</span></span>  
  
-   <span data-ttu-id="aed7c-113">Durée estimée de récupération (rattrapage de la phase de restauration par progression)</span><span class="sxs-lookup"><span data-stu-id="aed7c-113">Estimated Recovery Time (redo catch up)</span></span>  
  
-   <span data-ttu-id="aed7c-114">Détails du réplica de base de données</span><span class="sxs-lookup"><span data-stu-id="aed7c-114">Database Replica details</span></span>  
  
-   <span data-ttu-id="aed7c-115">Mode et état de synchronisation</span><span class="sxs-lookup"><span data-stu-id="aed7c-115">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="aed7c-116">Durée de restauration du journal</span><span class="sxs-lookup"><span data-stu-id="aed7c-116">Time to restore log</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aed7c-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="aed7c-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="aed7c-118">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="aed7c-118">Prerequisites</span></span>  
 <span data-ttu-id="aed7c-119">Vous devez être connecté à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (instance de serveur) qui héberge soit le réplica principal, soit un réplica secondaire d'un groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aed7c-119">You must be connected to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (server instance) that hosts either the primary replica or a secondary replica of an availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aed7c-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="aed7c-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aed7c-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="aed7c-121">Permissions</span></span>  
 <span data-ttu-id="aed7c-122">Requiert les autorisations CONNECT, VIEW SERVER STATE et VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="aed7c-122">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="to-start-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="aed7c-123">Pour démarrer le tableau de bord AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="aed7c-123">To start the AlwaysOn Dashboard</span></span>  
  
1.  <span data-ttu-id="aed7c-124">Dans l'Explorateur d'objets, connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur laquelle vous souhaitez exécuter le tableau de bord AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="aed7c-124">In Object Explorer, connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on which you want to run the AlwaysOn Dashboard.</span></span>  
  
2.  <span data-ttu-id="aed7c-125">Développez le nœud **Haute disponibilité AlwaysOn** , cliquez avec le bouton droit sur le nœud **Groupes de disponibilité** , puis sélectionnez **Afficher le tableau de bord**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-125">Expand the **AlwaysOn High Availability** node, right-click the **Availability Groups** node, and then click **Show Dashboard**.</span></span>  
  
###  <a name="to-change-alwayson-dashboard-options"></a><a name="DashboardOptions"></a><span data-ttu-id="aed7c-126">Pour modifier les options du tableau de bord AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="aed7c-126">To Change AlwaysOn Dashboard Options</span></span>  
 <span data-ttu-id="aed7c-127">Vous pouvez utiliser la boîte de dialogue **Options** de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] pour configurer le comportement du tableau de bord [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn en ce qui concerne l’actualisation automatique et l’activation d’une stratégie AlwaysOn définie automatiquement.</span><span class="sxs-lookup"><span data-stu-id="aed7c-127">You can use the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Options** dialog box to configure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn Dashboard behavior for automatic refreshing and enabling an auto-defined AlwaysOn policy.</span></span>  
  
1.  <span data-ttu-id="aed7c-128">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-128">From the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="aed7c-129">Pour actualiser automatiquement le tableau de bord, dans la boîte de dialogue **Options** , sélectionnez **Activer l'actualisation automatique**, entrez l'intervalle d'actualisation en secondes, puis entrez le nombre de fois où vous souhaitez réessayer la connexion.</span><span class="sxs-lookup"><span data-stu-id="aed7c-129">To automatically refresh the dashboard, in the **Options** dialog box, select **Turn on automatic refresh**, enter the refresh interval in seconds, and then enter the number of times you want to retry the connection.</span></span>  
  
3.  <span data-ttu-id="aed7c-130">Pour activer une stratégie définie par l'utilisateur, sélectionnez **Activer la stratégie AlwaysOn définie par l'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-130">To enable a user-defined policy, select **Enable user-defined AlwaysOn policy**.</span></span>  
  
##  <a name="availability-group-summary"></a><a name="AvGroupsView"></a> <span data-ttu-id="aed7c-131">Résumé des groupes de disponibilité</span><span class="sxs-lookup"><span data-stu-id="aed7c-131">Availability Group Summary</span></span>  
 <span data-ttu-id="aed7c-132">L'écran de groupe de disponibilité affiche une ligne de résumé pour chaque groupe de disponibilité pour lequel l'instance de serveur connectée héberge un réplica.</span><span class="sxs-lookup"><span data-stu-id="aed7c-132">The availability group screen displays a summary line for each availability group for which the connected server instance hosts a replica.</span></span> <span data-ttu-id="aed7c-133">Ce volet inclut les colonnes suivantes.</span><span class="sxs-lookup"><span data-stu-id="aed7c-133">This pane displays the following columns.</span></span>  
  
 <span data-ttu-id="aed7c-134">**Nom du groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="aed7c-134">**Availability Group Name**</span></span>  
 <span data-ttu-id="aed7c-135">Nom d'un groupe de disponibilité pour lequel l'instance de serveur connectée héberge un réplica.</span><span class="sxs-lookup"><span data-stu-id="aed7c-135">The name of an availability group for which the connected server instance hosts a replica.</span></span>  
  
 <span data-ttu-id="aed7c-136">**Instance principale**</span><span class="sxs-lookup"><span data-stu-id="aed7c-136">**Primary Instance**</span></span>  
 <span data-ttu-id="aed7c-137">Nom de l'instance de serveur qui héberge le réplica principal du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aed7c-137">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="aed7c-138">**Mode de basculement**</span><span class="sxs-lookup"><span data-stu-id="aed7c-138">**Failover Mode**</span></span>  
 <span data-ttu-id="aed7c-139">Affiche le mode de basculement pour lequel le réplica est configuré.</span><span class="sxs-lookup"><span data-stu-id="aed7c-139">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="aed7c-140">Les valeurs possibles pour le mode de basculement sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-140">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="aed7c-141">**Automatique**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-141">**Automatic**.</span></span> <span data-ttu-id="aed7c-142">Indique qu'un ou plusieurs réplicas se trouvent en mode de basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="aed7c-142">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="aed7c-143">**Manuel**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-143">**Manual**.</span></span> <span data-ttu-id="aed7c-144">Indique qu'aucun réplica n'est en mode de basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="aed7c-144">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="aed7c-145">**Problèmes**</span><span class="sxs-lookup"><span data-stu-id="aed7c-145">**Issues**</span></span>  
 <span data-ttu-id="aed7c-146">Cliquez sur le lien **Problèmes** pour ouvrir la documentation de dépannage relative à un problème donné.</span><span class="sxs-lookup"><span data-stu-id="aed7c-146">Click the **Issues** link to open troubleshooting documentation for a given issue.</span></span> <span data-ttu-id="aed7c-147">Pour obtenir la liste de tous les problèmes de stratégie AlwaysOn, consultez [stratégies AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="aed7c-147">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="aed7c-148">Cliquez sur les en-têtes de colonne pour trier les informations de groupe de disponibilité selon le nom du groupe de disponibilité, l'instance principale, le mode de basculement ou le problème.</span><span class="sxs-lookup"><span data-stu-id="aed7c-148">Click the column headings to sort the availability group information by the name of the availability group, primary instance, failover mode, or Issue.</span></span>  
  
##  <a name="availability-group-details"></a><a name="AvGroupDetails"></a> <span data-ttu-id="aed7c-149">Détails du groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="aed7c-149">Availability Group Details</span></span>  
 <span data-ttu-id="aed7c-150">Les informations détaillées suivantes sont affichées pour le groupe de disponibilité que vous sélectionnez dans l'écran récapitulatif :</span><span class="sxs-lookup"><span data-stu-id="aed7c-150">The following detail information is displayed for the availability group that you select from the summary screen:</span></span>  
  
 <span data-ttu-id="aed7c-151">**État du groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="aed7c-151">**Availability group state**</span></span>  
 <span data-ttu-id="aed7c-152">Affiche l'état d'intégrité du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aed7c-152">Displays the state of health for the availability group.</span></span>  
  
 <span data-ttu-id="aed7c-153">**Primary instance**</span><span class="sxs-lookup"><span data-stu-id="aed7c-153">**Primary instance**</span></span>  
 <span data-ttu-id="aed7c-154">Nom de l'instance de serveur qui héberge le réplica principal du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aed7c-154">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="aed7c-155">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="aed7c-155">**Failover mode**</span></span>  
 <span data-ttu-id="aed7c-156">Affiche le mode de basculement pour lequel le réplica est configuré.</span><span class="sxs-lookup"><span data-stu-id="aed7c-156">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="aed7c-157">Les valeurs possibles pour le mode de basculement sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-157">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="aed7c-158">**Automatique**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-158">**Automatic**.</span></span> <span data-ttu-id="aed7c-159">Indique qu'un ou plusieurs réplicas se trouvent en mode de basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="aed7c-159">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="aed7c-160">**Manuel**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-160">**Manual**.</span></span> <span data-ttu-id="aed7c-161">Indique qu'aucun réplica n'est en mode de basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="aed7c-161">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="aed7c-162">**État du cluster**</span><span class="sxs-lookup"><span data-stu-id="aed7c-162">**Cluster state**</span></span>  
 <span data-ttu-id="aed7c-163">Nom et état du cluster dans lequel l'instance du serveur connecté et du groupe de disponibilité est un nœud membre.</span><span class="sxs-lookup"><span data-stu-id="aed7c-163">Name and state of the cluster where the instance of the connected server and the availability group is a member node.</span></span>  
  
##  <a name="availability-replica-details"></a><a name="AvReplicaDetails"></a> <span data-ttu-id="aed7c-164">Détails du réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="aed7c-164">Availability Replica Details</span></span>  
 <span data-ttu-id="aed7c-165">Le volet **Réplica de disponibilité** affiche les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-165">The **Availability replica** pane displays the following columns:</span></span>  
  
 <span data-ttu-id="aed7c-166">**Nom**</span><span class="sxs-lookup"><span data-stu-id="aed7c-166">**Name**</span></span>  
 <span data-ttu-id="aed7c-167">Nom de l'instance du serveur qui héberge le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aed7c-167">The name of the server instance that hosts the availability replica.</span></span> <span data-ttu-id="aed7c-168">Cette colonne est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-168">This column is shown by default.</span></span>  
  
 <span data-ttu-id="aed7c-169">**Rôle**</span><span class="sxs-lookup"><span data-stu-id="aed7c-169">**Role**</span></span>  
 <span data-ttu-id="aed7c-170">Indique le rôle actuel du réplica de disponibilité, à savoir **Principal** ou **Secondaire**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-170">Indicates the current role of the availability replica, either **Primary** or **Secondary**.</span></span> <span data-ttu-id="aed7c-171">Pour plus d’informations sur les rôles des [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], consultez [Vue d’ensemble des groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="aed7c-171">For information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] roles, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span> <span data-ttu-id="aed7c-172">Cette colonne est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-172">This column is shown by default.</span></span>  
  
 <span data-ttu-id="aed7c-173">**Mode de basculement**</span><span class="sxs-lookup"><span data-stu-id="aed7c-173">**Failover Mode**</span></span>  
 <span data-ttu-id="aed7c-174">Affiche le mode de basculement pour lequel le réplica est configuré.</span><span class="sxs-lookup"><span data-stu-id="aed7c-174">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="aed7c-175">Les valeurs possibles pour le mode de basculement sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-175">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="aed7c-176">**Automatique**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-176">**Automatic**.</span></span> <span data-ttu-id="aed7c-177">Indique qu'un ou plusieurs réplicas se trouvent en mode de basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="aed7c-177">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="aed7c-178">**Manuel**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-178">**Manual**.</span></span> <span data-ttu-id="aed7c-179">Indique qu'aucun réplica n'est en mode de basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="aed7c-179">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="aed7c-180">**État de synchronisation**</span><span class="sxs-lookup"><span data-stu-id="aed7c-180">**Synchronization State**</span></span>  
 <span data-ttu-id="aed7c-181">Indique si un réplica secondaire est actuellement synchronisé avec le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-181">Indicates whether a secondary replica is currently synchronized with primary replica.</span></span> <span data-ttu-id="aed7c-182">Cette colonne est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-182">This column is shown by default.</span></span> <span data-ttu-id="aed7c-183">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-183">The possible values are:</span></span>  
  
-   <span data-ttu-id="aed7c-184">**Non synchronisé**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-184">**Not Synchronized**.</span></span> <span data-ttu-id="aed7c-185">Une ou plusieurs bases de données du réplica ne sont pas synchronisées ou n'ont pas encore été jointes au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aed7c-185">One or more databases in the replica are not synchronized or have not yet been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="aed7c-186">**Synchronisation**en cours.</span><span class="sxs-lookup"><span data-stu-id="aed7c-186">**Synchronizing**.</span></span> <span data-ttu-id="aed7c-187">Une ou plusieurs bases de données du réplica sont synchronisées.</span><span class="sxs-lookup"><span data-stu-id="aed7c-187">One or more databases in the replica are being synchronized.</span></span>  
  
-   <span data-ttu-id="aed7c-188">**Synchronisé**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-188">**Synchronized**.</span></span> <span data-ttu-id="aed7c-189">Toutes les bases de données du réplica secondaire sont synchronisées avec les base de données primaires correspondantes sur le réplica principal actuel, le cas échéant, ou sur le dernier réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-189">All databases in the secondary replica are synchronized with the corresponding primary databases on the current primary replica, if any, or on the last primary replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aed7c-190">En mode de performances, la base de données n'est jamais dans l'état synchronisé.</span><span class="sxs-lookup"><span data-stu-id="aed7c-190">In performance mode, the database is never in the synchronized state.</span></span>  
  
-   <span data-ttu-id="aed7c-191">**Valeur null**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-191">**NULL**.</span></span> <span data-ttu-id="aed7c-192">État inconnu.</span><span class="sxs-lookup"><span data-stu-id="aed7c-192">Unknown state.</span></span> <span data-ttu-id="aed7c-193">Cette valeur se produit lorsque l'instance de serveur locale ne peut pas communiquer avec le cluster de basculement WSFC (le nœud local ne fait pas partie du quorum WSFC).</span><span class="sxs-lookup"><span data-stu-id="aed7c-193">This value occurs when the local server instance cannot communicate with the WSFC failover cluster (that is the local node is not part of WSFC quorum).</span></span>  
  
 <span data-ttu-id="aed7c-194">**Problèmes**</span><span class="sxs-lookup"><span data-stu-id="aed7c-194">**Issues**</span></span>  
 <span data-ttu-id="aed7c-195">Énonce le nom du problème.</span><span class="sxs-lookup"><span data-stu-id="aed7c-195">Lists the issue name.</span></span> <span data-ttu-id="aed7c-196">Cette valeur est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-196">This value is shown by default.</span></span> <span data-ttu-id="aed7c-197">Pour obtenir la liste de tous les problèmes de stratégie AlwaysOn, consultez [stratégies AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="aed7c-197">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="aed7c-198">**Mode de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="aed7c-198">**Availability Mode**</span></span>  
 <span data-ttu-id="aed7c-199">Indique la propriété de réplica que vous définissez séparément pour chaque réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aed7c-199">Indicates the replica property that you set separately for each availability replica.</span></span> <span data-ttu-id="aed7c-200">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-200">This value is hidden by default.</span></span> <span data-ttu-id="aed7c-201">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-201">The possible values are:</span></span>  
  
-   <span data-ttu-id="aed7c-202">**Asynchrone**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-202">**Asynchronous**.</span></span> <span data-ttu-id="aed7c-203">Le réplica secondaire n'est jamais synchronisé avec le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-203">The secondary replica never becomes synchronized with the primary replica.</span></span>  
  
-   <span data-ttu-id="aed7c-204">**Synchrone**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-204">**Synchronous**.</span></span> <span data-ttu-id="aed7c-205">Lors du rattrapage du retard par rapport à la base de données primaire, une base de données secondaire entre dans cet état, mais reste en retard tant que la synchronisation des données se poursuit pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="aed7c-205">When catching up to the primary database, a secondary database enters this state, and it remains caught up as long as data synchronization continues for the database.</span></span>  
  
 <span data-ttu-id="aed7c-206">**Mode de connexion principal**</span><span class="sxs-lookup"><span data-stu-id="aed7c-206">**Primary Connection Mode**</span></span>  
 <span data-ttu-id="aed7c-207">Indique le mode utilisé pour se connecter au réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-207">Indicates the mode that is used to connect to the primary replica.</span></span>  <span data-ttu-id="aed7c-208">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-208">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-209">**Mode de connexion secondaire**</span><span class="sxs-lookup"><span data-stu-id="aed7c-209">**Secondary Connection Mode**</span></span>  
 <span data-ttu-id="aed7c-210">Indique le mode utilisé pour se connecter au réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-210">Indicates the mode that is used to connect to the secondary replica.</span></span>  <span data-ttu-id="aed7c-211">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-211">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-212">**État de la connexion**</span><span class="sxs-lookup"><span data-stu-id="aed7c-212">**Connection State**</span></span>  
 <span data-ttu-id="aed7c-213">Indique si un réplica secondaire est actuellement connecté au réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-213">Indicates whether a secondary replica is currently connected to the primary replica.</span></span> <span data-ttu-id="aed7c-214">Cette colonne est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-214">This column is hidden by default.</span></span> <span data-ttu-id="aed7c-215">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-215">The possible values are:</span></span>  
  
-   <span data-ttu-id="aed7c-216">**Déconnecté**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-216">**Disconnected**.</span></span> <span data-ttu-id="aed7c-217">Pour un réplica de disponibilité distant, indique qu'il est déconnecté du réplica de disponibilité local.</span><span class="sxs-lookup"><span data-stu-id="aed7c-217">For a remote availability replica, indicates that it is disconnected from the local availability replica.</span></span> <span data-ttu-id="aed7c-218">La réponse du réplica local à l'état déconnecté dépend de son rôle, comme suit :</span><span class="sxs-lookup"><span data-stu-id="aed7c-218">The response of the local replica to the Disconnected state depends on its role, as follows:</span></span>  
  
    -   <span data-ttu-id="aed7c-219">Sur le réplica principal, si un réplica secondaire est déconnecté, les bases de données secondaires sont marquées comme **Non synchronisé** sur le réplica principal, et le réplica principal attend que le réplica secondaire se reconnecte.</span><span class="sxs-lookup"><span data-stu-id="aed7c-219">On the primary replica, if a secondary replica is disconnected, the secondary databases are marked as **Not Synchronized** on the primary replica, and the primary replica waits for the secondary to reconnect.</span></span>  
  
    -   <span data-ttu-id="aed7c-220">Une fois la déconnexion détectée, le réplica secondaire tente de se reconnecter au réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-220">On the secondary replica, upon detecting that it is disconnected, the secondary replica attempts to reconnect to the primary replica.</span></span>  
  
-   <span data-ttu-id="aed7c-221">**Connecté**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-221">**Connected**.</span></span> <span data-ttu-id="aed7c-222">Réplica de disponibilité distant qui est actuellement connecté au réplica local.</span><span class="sxs-lookup"><span data-stu-id="aed7c-222">A remote availability replica that is currently connected to the local replica.</span></span>  
  
 <span data-ttu-id="aed7c-223">**État opérationnel**</span><span class="sxs-lookup"><span data-stu-id="aed7c-223">**Operational State**</span></span>  
 <span data-ttu-id="aed7c-224">Indique l'état opérationnel actuel du réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-224">Indicates the current operational state of the secondary replica.</span></span> <span data-ttu-id="aed7c-225">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-225">This value is hidden by default.</span></span> <span data-ttu-id="aed7c-226">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-226">The possible values are:</span></span>  
  
 <span data-ttu-id="aed7c-227">**0**. Basculement en attente</span><span class="sxs-lookup"><span data-stu-id="aed7c-227">**0**. Pending failover</span></span>  
  
 <span data-ttu-id="aed7c-228">**1**. En attente</span><span class="sxs-lookup"><span data-stu-id="aed7c-228">**1**. Pending</span></span>  
  
 <span data-ttu-id="aed7c-229">**2**. En ligne</span><span class="sxs-lookup"><span data-stu-id="aed7c-229">**2**. Online</span></span>  
  
 <span data-ttu-id="aed7c-230">**3**. Hors connexion</span><span class="sxs-lookup"><span data-stu-id="aed7c-230">**3**. Offline</span></span>  
  
 <span data-ttu-id="aed7c-231">**4**. Échec</span><span class="sxs-lookup"><span data-stu-id="aed7c-231">**4**. Failed</span></span>  
  
 <span data-ttu-id="aed7c-232">**5**. Échec, pas de quorum</span><span class="sxs-lookup"><span data-stu-id="aed7c-232">**5**. Failed, no quorum</span></span>  
  
 <span data-ttu-id="aed7c-233">**Valeur null**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-233">**NULL**.</span></span> <span data-ttu-id="aed7c-234">Le réplica n'est pas local</span><span class="sxs-lookup"><span data-stu-id="aed7c-234">Replica is not local</span></span>  
  
 <span data-ttu-id="aed7c-235">**Numéro de la dernière erreur de connexion**</span><span class="sxs-lookup"><span data-stu-id="aed7c-235">**Last Connection Error No.**</span></span>  
 <span data-ttu-id="aed7c-236">Numéro de la dernière erreur de connexion.</span><span class="sxs-lookup"><span data-stu-id="aed7c-236">Number of the last connection error.</span></span>  <span data-ttu-id="aed7c-237">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-237">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-238">**Description de la dernière erreur de connexion**</span><span class="sxs-lookup"><span data-stu-id="aed7c-238">**Last Connection Error Description**</span></span>  
 <span data-ttu-id="aed7c-239">Description de la dernière erreur de connexion.</span><span class="sxs-lookup"><span data-stu-id="aed7c-239">Description of the last connection error.</span></span>  <span data-ttu-id="aed7c-240">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-240">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-241">**Horodateur de la dernière erreur de connexion**</span><span class="sxs-lookup"><span data-stu-id="aed7c-241">**Last Connection Error Timestamp**</span></span>  
 <span data-ttu-id="aed7c-242">Horodateur de la dernière erreur de connexion.</span><span class="sxs-lookup"><span data-stu-id="aed7c-242">Timestamp of the last connection error.</span></span> <span data-ttu-id="aed7c-243">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-243">This value is hidden by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aed7c-244">Pour plus d’informations sur les compteurs de performances pour les réplicas de disponibilité, consultez [SQL Server, réplica de disponibilité](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="aed7c-244">For information about performance counters for availability replicas, see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
##  <a name="to-group-availability-group-information"></a><a name="AvDbDetails"></a> <span data-ttu-id="aed7c-245">Pour regrouper les informations de groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="aed7c-245">To Group Availability Group Information</span></span>  
 <span data-ttu-id="aed7c-246">Pour regrouper les informations, cliquez sur **Regrouper par**, puis sélectionnez l'une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-246">To group the information, click **Group by**, and select one of the following:</span></span>  
  
-   <span data-ttu-id="aed7c-247">**Réplicas de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="aed7c-247">**Availability replicas**</span></span>  
  
-   <span data-ttu-id="aed7c-248">**Bases de données de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="aed7c-248">**Availability databases**</span></span>  
  
-   <span data-ttu-id="aed7c-249">**État de synchronisation**</span><span class="sxs-lookup"><span data-stu-id="aed7c-249">**Synchronization state**</span></span>  
  
-   <span data-ttu-id="aed7c-250">**Disponibilité du basculement**</span><span class="sxs-lookup"><span data-stu-id="aed7c-250">**Failover readiness**</span></span>  
  
-   <span data-ttu-id="aed7c-251">**Problèmes**</span><span class="sxs-lookup"><span data-stu-id="aed7c-251">**Issues**</span></span>  
  
 <span data-ttu-id="aed7c-252">Le volet qui affiche les informations regroupées comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-252">The pane that displays the grouped information displays the following columns:</span></span>  
  
 <span data-ttu-id="aed7c-253">**Nom**</span><span class="sxs-lookup"><span data-stu-id="aed7c-253">**Name**</span></span>  
 <span data-ttu-id="aed7c-254">Nom de la base de données de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aed7c-254">The name of the availability database.</span></span> <span data-ttu-id="aed7c-255">Cette valeur est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-255">This value is shown by default.</span></span>  
  
 <span data-ttu-id="aed7c-256">**Réplica**</span><span class="sxs-lookup"><span data-stu-id="aed7c-256">**Replica**</span></span>  
 <span data-ttu-id="aed7c-257">Nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="aed7c-257">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span> <span data-ttu-id="aed7c-258">Cette valeur est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-258">This value is shown by default.</span></span>  
  
 <span data-ttu-id="aed7c-259">**État de synchronisation**</span><span class="sxs-lookup"><span data-stu-id="aed7c-259">**Synchronization State**</span></span>  
 <span data-ttu-id="aed7c-260">Indique si la base de données de disponibilité est actuellement synchronisée avec le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-260">Indicates whether the availability database is currently synchronized with primary replica.</span></span> <span data-ttu-id="aed7c-261">Cette valeur est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-261">This value is shown by default.</span></span> <span data-ttu-id="aed7c-262">Les états de synchronisation possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="aed7c-262">The possible synchronization states are:</span></span>  
  
-   <span data-ttu-id="aed7c-263">**Sans synchronisation**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-263">**Not synchronizing**.</span></span>  
  
    -   <span data-ttu-id="aed7c-264">Pour le rôle principal, indique que la base de données n'est pas prête à synchroniser son journal des transactions avec les bases de données secondaires correspondantes.</span><span class="sxs-lookup"><span data-stu-id="aed7c-264">For the primary role, indicates that the database is not ready to synchronize its transaction log with the corresponding secondary databases.</span></span>  
  
    -   <span data-ttu-id="aed7c-265">Pour une base de données secondaire, indique que la base de données n'a pas commencé la synchronisation du journal en raison d'un problème de connexion, est suspendue, ou passe par des états de transition pendant le démarrage ou lors d'un changement de rôle.</span><span class="sxs-lookup"><span data-stu-id="aed7c-265">For a secondary database, indicates that the database has not started log synchronization because of a connection issue, is being suspended, or is going through transition states during startup or a role switch.</span></span>  
  
-   <span data-ttu-id="aed7c-266">**Synchronisation**en cours.</span><span class="sxs-lookup"><span data-stu-id="aed7c-266">**Synchronizing**.</span></span>  
  
     <span data-ttu-id="aed7c-267">Sur un réplica principal :</span><span class="sxs-lookup"><span data-stu-id="aed7c-267">On a primary replica:</span></span>  
  
    -   <span data-ttu-id="aed7c-268">Pour une base de données primaire, indique que cette base de données est prête à recevoir une demande d'analyse d'une base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-268">For a primary database, indicates that this database is ready to accept a scan request from a secondary database.</span></span>  
  
    -   <span data-ttu-id="aed7c-269">Sur un réplica secondaire, indique qu'il existe un déplacement des données actif pour cette base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-269">On a secondary replica, indicates that there is active data movement going on for that secondary database.</span></span>  
  
     <span data-ttu-id="aed7c-270">Sur un réplica secondaire, indique qu'il existe un déplacement des données actif pour ce réplica.</span><span class="sxs-lookup"><span data-stu-id="aed7c-270">On a secondary replica, indicates that there is active data movement going on for that replica.</span></span>  
  
-   <span data-ttu-id="aed7c-271">**Synchronisé**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-271">**Synchronized**.</span></span>  
  
     <span data-ttu-id="aed7c-272">Pour une base de données primaire, indique qu'au moins une base de données secondaire est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="aed7c-272">For a primary database, indicates that at least one secondary database is synchronized.</span></span>  
  
     <span data-ttu-id="aed7c-273">Pour une base de données secondaire, indique que la base de données est synchronisée avec la base de données primaire correspondante.</span><span class="sxs-lookup"><span data-stu-id="aed7c-273">For a secondary database, indicates that the database is synchronized with the corresponding primary database.</span></span>  
  
-   <span data-ttu-id="aed7c-274">**Rétablissement**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-274">**Reverting**.</span></span>  
  
     <span data-ttu-id="aed7c-275">Indique la phase dans le processus de restauration lorsqu'une base de données secondaire obtient activement les pages de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-275">Indicates the phase in the undo process when a secondary database is actively getting pages from the primary database.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="aed7c-276">Lorsqu'une base de données est dans l'état REVERTING, forcer le basculement vers le réplica secondaire peut laisser cette base de données dans un état dans lequel elle ne peut pas être démarrée.</span><span class="sxs-lookup"><span data-stu-id="aed7c-276">When a database is in the REVERTING state, forcing failover to the secondary replica can leave that database in a state in which it cannot be started.</span></span>  
  
-   <span data-ttu-id="aed7c-277">**Initialisation en cours**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-277">**Initializing**.</span></span>  
  
     <span data-ttu-id="aed7c-278">Indique la phase de restauration lorsque le journal des transactions requis pour qu'une base de données secondaire rattrape le retard du numéro séquentiel de restauration dans le journal est livré et renforcé sur un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-278">Indicates the phase of undo when the transaction log required for a secondary database to catch up to the undo LSN is being shipped and hardened on a secondary replica.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="aed7c-279">Lorsqu'une base de données est dans l'état INITIALIZING, forcer le basculement vers le réplica secondaire laisse toujours cette base de données dans un état dans lequel elle ne peut pas être démarrée.</span><span class="sxs-lookup"><span data-stu-id="aed7c-279">When a database is in the INITIALIZING state, forcing failover to the secondary replica will always leave that database in a state in which it cannot be started.</span></span>  
  
 <span data-ttu-id="aed7c-280">**Disponibilité du basculement**</span><span class="sxs-lookup"><span data-stu-id="aed7c-280">**Failover Readiness**</span></span>  
 <span data-ttu-id="aed7c-281">Indique le réplica de disponibilité qui peut basculer avec ou sans perte possible de données.</span><span class="sxs-lookup"><span data-stu-id="aed7c-281">Indicates which availability replica can be failed over with or without potential data loss.</span></span> <span data-ttu-id="aed7c-282">Cette colonne est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-282">This column is shown by default.</span></span> <span data-ttu-id="aed7c-283">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-283">The possible values are:</span></span>  
  
-   <span data-ttu-id="aed7c-284">**Perte de données**</span><span class="sxs-lookup"><span data-stu-id="aed7c-284">**Data Loss**</span></span>  
  
-   <span data-ttu-id="aed7c-285">**Aucune perte de données**</span><span class="sxs-lookup"><span data-stu-id="aed7c-285">**No Data Loss**</span></span>  
  
 <span data-ttu-id="aed7c-286">**Problèmes**</span><span class="sxs-lookup"><span data-stu-id="aed7c-286">**Issues**</span></span>  
 <span data-ttu-id="aed7c-287">Énonce le nom du problème.</span><span class="sxs-lookup"><span data-stu-id="aed7c-287">Lists the issue name.</span></span> <span data-ttu-id="aed7c-288">Cette colonne est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-288">This column is shown by default.</span></span> <span data-ttu-id="aed7c-289">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="aed7c-289">The possible values are:</span></span>  
  
-   <span data-ttu-id="aed7c-290">**Avertissements**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-290">**Warnings**.</span></span> <span data-ttu-id="aed7c-291">Cliquez pour afficher les problèmes d'avertissements et de seuils.</span><span class="sxs-lookup"><span data-stu-id="aed7c-291">Click to display the thresholds and warnings issues.</span></span>  
  
-   <span data-ttu-id="aed7c-292">**Critique**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-292">**Critical**.</span></span> <span data-ttu-id="aed7c-293">Cliquez pour afficher les problèmes critiques.</span><span class="sxs-lookup"><span data-stu-id="aed7c-293">Click to display the critical issues.</span></span>  
  
 <span data-ttu-id="aed7c-294">Pour obtenir la liste de tous les problèmes de stratégie AlwaysOn, consultez [stratégies AlwaysOn pour les problèmes opérationnels avec groupes de disponibilité AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="aed7c-294">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="aed7c-295">**Suspendu**</span><span class="sxs-lookup"><span data-stu-id="aed7c-295">**Suspended**</span></span>  
 <span data-ttu-id="aed7c-296">Indique si la base de données est à l’état **Suspendu** ou si elle a été **reprise**.</span><span class="sxs-lookup"><span data-stu-id="aed7c-296">Indicates whether the database is **Suspended** or has been **Resumed**.</span></span> <span data-ttu-id="aed7c-297">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-297">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-298">**Motif de suspension**</span><span class="sxs-lookup"><span data-stu-id="aed7c-298">**Suspend Reason**</span></span>  
 <span data-ttu-id="aed7c-299">Indique le motif de l'état suspendu.</span><span class="sxs-lookup"><span data-stu-id="aed7c-299">Indicates the reason for the suspended state.</span></span> <span data-ttu-id="aed7c-300">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-300">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-301">**Estimer la perte de données (secondes)**</span><span class="sxs-lookup"><span data-stu-id="aed7c-301">**Estimate Data Loss (seconds)**</span></span>  
 <span data-ttu-id="aed7c-302">Indique la différence de temps du dernier enregistrement des journaux de transactions dans le réplica principal et le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-302">Indicates the time difference of the last transaction log record in the primary replica and secondary replica.</span></span> <span data-ttu-id="aed7c-303">Si le réplica principal échoue, tous les enregistrements du journal des transactions se trouvant dans cette fenêtre temporelle seront perdus.</span><span class="sxs-lookup"><span data-stu-id="aed7c-303">If the primary replica fails, all transaction log records within the time window will be lost.</span></span> <span data-ttu-id="aed7c-304">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-304">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-305">**Durée estimée de récupération (secondes)**</span><span class="sxs-lookup"><span data-stu-id="aed7c-305">**Estimated Recovery Time (seconds)**</span></span>  
 <span data-ttu-id="aed7c-306">Indique la durée (en secondes) nécessaire pour rétablir le temps de rattrapage.</span><span class="sxs-lookup"><span data-stu-id="aed7c-306">Indicates the time in seconds it takes to redo the catch-up time.</span></span> <span data-ttu-id="aed7c-307">Le *temps de rattrapage* correspond au temps nécessaire pour que le réplica secondaire rattrape le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-307">The *catch-up time* is the time it will take for the secondary replica to catch up with the primary replica.</span></span> <span data-ttu-id="aed7c-308">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-308">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-309">**Performances de synchronisation (secondes)**</span><span class="sxs-lookup"><span data-stu-id="aed7c-309">**Synchronization Performance (seconds)**</span></span>  
 <span data-ttu-id="aed7c-310">Indique le temps (en secondes) nécessaire pour effectuer la synchronisation entre le réplica principal et le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-310">Indicates the time in seconds it takes to synchronize between the primary and secondary replicas.</span></span> <span data-ttu-id="aed7c-311">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-311">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-312">**Taille de la file d'attente d'envoi du journal (Ko)**</span><span class="sxs-lookup"><span data-stu-id="aed7c-312">**Log Send Queue Size (KB)**</span></span>  
 <span data-ttu-id="aed7c-313">Indique la quantité d'enregistrements de journal dans les fichiers journaux de la base de données primaire qui n'ont pas été envoyés au réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-313">Indicates the amount of log records in the log files of the primary database that have not been sent to the secondary replica.</span></span> <span data-ttu-id="aed7c-314">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-314">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-315">**Débit d'envoi du journal (Ko/s)**</span><span class="sxs-lookup"><span data-stu-id="aed7c-315">**Log Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="aed7c-316">Indique le débit, en Ko par seconde, auquel les enregistrements de journal sont envoyés au réplica secondaire. Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-316">Indicates the rate in KB per second at which log records are being sent to the secondary replica This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-317">**Taille de la file d'attente de restauration par progression (Ko)**</span><span class="sxs-lookup"><span data-stu-id="aed7c-317">**Redo Queue Size (KB)**</span></span>  
 <span data-ttu-id="aed7c-318">Indique la quantité d'enregistrements du journal dans les fichiers journaux du réplica secondaire qui n'ont pas encore été restaurés.</span><span class="sxs-lookup"><span data-stu-id="aed7c-318">Indicates the amount of log records in the log files of the secondary replica that have not yet been redone.</span></span> <span data-ttu-id="aed7c-319">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-319">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-320">**Débit de la restauration par progression (Ko/s)**</span><span class="sxs-lookup"><span data-stu-id="aed7c-320">**Redo Rate (KB/sec)**</span></span>  
 <span data-ttu-id="aed7c-321">Indique le débit, en Ko par seconde, auquel les enregistrements de journal sont restaurés.</span><span class="sxs-lookup"><span data-stu-id="aed7c-321">Indicates the rate in KB per second at which the log records are being redone.</span></span> <span data-ttu-id="aed7c-322">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-322">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-323">**Vitesse d'envoi de flux de fichiers (Ko/s)**</span><span class="sxs-lookup"><span data-stu-id="aed7c-323">**FileStream Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="aed7c-324">Indique le débit de FileStream, en Ko par seconde, auquel les transactions sont envoyées au réplica.</span><span class="sxs-lookup"><span data-stu-id="aed7c-324">Indicates the rate of the FileStream in KB per second at which transactions are being sent to the replica.</span></span> <span data-ttu-id="aed7c-325">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-325">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-326">**LSN de fin du journal**</span><span class="sxs-lookup"><span data-stu-id="aed7c-326">**End of Log LSN**</span></span>  
 <span data-ttu-id="aed7c-327">Indique le numéro séquentiel dans le journal (LSN) réel qui correspond au dernier enregistrement du journal dans le cache du journal sur les réplicas principal et secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-327">Indicates the actual log sequence number (LSN) that corresponds to the last log record in the log cache on the primary and secondary replicas.</span></span> <span data-ttu-id="aed7c-328">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-328">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-329">**LSN de récupération**</span><span class="sxs-lookup"><span data-stu-id="aed7c-329">**Recovery LSN**</span></span>  
 <span data-ttu-id="aed7c-330">Indique la fin du journal des transactions avant que le réplica n'écrive de nouveaux enregistrements de journal après la récupération ou le basculement sur le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-330">Indicates the end of the transaction log before the replica writes any new log records after recovery or failover on the primary replica.</span></span> <span data-ttu-id="aed7c-331">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-331">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-332">**LSN de troncation**</span><span class="sxs-lookup"><span data-stu-id="aed7c-332">**Truncation LSN**</span></span>  
 <span data-ttu-id="aed7c-333">Indique la valeur minimale de troncation du journal du réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-333">Indicates the minimum log truncation value for the primary replica.</span></span> <span data-ttu-id="aed7c-334">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-334">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-335">**LSN de dernière validation**</span><span class="sxs-lookup"><span data-stu-id="aed7c-335">**Last Commit LSN**</span></span>  
 <span data-ttu-id="aed7c-336">Indique le numéro séquentiel dans le journal réel correspondant au dernier enregistrement de validation dans le journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="aed7c-336">Indicates the actual LSN corresponding to the last commit record in the transaction log.</span></span> <span data-ttu-id="aed7c-337">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-337">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-338">**Heure de dernière validation**</span><span class="sxs-lookup"><span data-stu-id="aed7c-338">**Last Commit Time**</span></span>  
 <span data-ttu-id="aed7c-339">Indique l'heure correspondant au dernier enregistrement de validation.</span><span class="sxs-lookup"><span data-stu-id="aed7c-339">Indicates the time corresponding to the last commit record.</span></span> <span data-ttu-id="aed7c-340">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-340">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-341">**LSN de dernier envoi**</span><span class="sxs-lookup"><span data-stu-id="aed7c-341">**Last Sent LSN**</span></span>  
 <span data-ttu-id="aed7c-342">Indique le point jusqu'auquel tous les blocs de journal ont été envoyés par le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="aed7c-342">Indicates the point up to which all log blocks have been sent by the primary replica.</span></span> <span data-ttu-id="aed7c-343">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-343">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-344">**Heure de dernier envoi**</span><span class="sxs-lookup"><span data-stu-id="aed7c-344">**Last Sent Time**</span></span>  
 <span data-ttu-id="aed7c-345">Indique l'heure à laquelle le dernier bloc du journal a été envoyé.</span><span class="sxs-lookup"><span data-stu-id="aed7c-345">Indicates the time when the last log block was sent.</span></span> <span data-ttu-id="aed7c-346">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-346">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-347">**LSN de dernière réception**</span><span class="sxs-lookup"><span data-stu-id="aed7c-347">**Last Received LSN**</span></span>  
 <span data-ttu-id="aed7c-348">Indique le point jusqu'auquel tous les blocs de journal ont été reçus par le réplica secondaire qui héberge la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-348">Indicates the point up to which all log blocks have been received by the secondary replica that hosts the secondary database.</span></span> <span data-ttu-id="aed7c-349">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-349">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-350">**Heure de dernière réception**</span><span class="sxs-lookup"><span data-stu-id="aed7c-350">**Last Received Time**</span></span>  
 <span data-ttu-id="aed7c-351">Indique l'heure à laquelle l'identificateur de bloc de journal du dernier message reçu a été lu sur le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-351">Indicates the time when the log block identifier in last message received was read on the secondary replica.</span></span> <span data-ttu-id="aed7c-352">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-352">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-353">**LSN de dernière sécurisation renforcée**</span><span class="sxs-lookup"><span data-stu-id="aed7c-353">**Last Hardened LSN**</span></span>  
 <span data-ttu-id="aed7c-354">Indique le point jusqu'auquel tous les enregistrements de journal ont été vidés sur le disque du réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-354">Indicates the point up to which all log records have been flushed to disk on the secondary replica.</span></span> <span data-ttu-id="aed7c-355">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-355">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-356">**Heure de dernière sécurisation renforcée**</span><span class="sxs-lookup"><span data-stu-id="aed7c-356">**Last Hardened Time**</span></span>  
 <span data-ttu-id="aed7c-357">Indique l'heure à laquelle l'identificateur de bloc de journal a été reçu pour le LSN de dernière sécurisation renforcée sur le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-357">Indicates the time when the log-block identifier was received for the last hardened LSN on the secondary replica.</span></span> <span data-ttu-id="aed7c-358">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-358">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-359">**LSN de dernière restauration par progression**</span><span class="sxs-lookup"><span data-stu-id="aed7c-359">**Last Redone LSN**</span></span>  
 <span data-ttu-id="aed7c-360">Indique le numéro séquentiel réel dans l'enregistrement du journal qui a été reconstruit pour la dernière fois sur le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-360">Indicates the actual LSN of the log record that was redone last on the secondary replica.</span></span> <span data-ttu-id="aed7c-361">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-361">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="aed7c-362">**Heure de dernière restauration par progression**</span><span class="sxs-lookup"><span data-stu-id="aed7c-362">**Last Redone Time**</span></span>  
 <span data-ttu-id="aed7c-363">Indique l'heure à laquelle le dernier enregistrement du journal a été restauré sur la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="aed7c-363">Indicates the time when the last log record was redone on the secondary database.</span></span> <span data-ttu-id="aed7c-364">Cette valeur est masquée par défaut.</span><span class="sxs-lookup"><span data-stu-id="aed7c-364">This value is hidden by default.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="aed7c-365">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="aed7c-365">Related Tasks</span></span>  
  
-   [<span data-ttu-id="aed7c-366">Utilisez les stratégies AlwaysOn pour afficher l’intégrité d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aed7c-366">Use AlwaysOn Policies to View the Health of an Availability Group &#40;SQL Server&#41;</span></span>](use-always-on-policies-to-view-the-health-of-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="aed7c-367">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aed7c-367">See Also</span></span>  
 <span data-ttu-id="aed7c-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aed7c-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span></span>  
 [<span data-ttu-id="aed7c-369">Surveillance des groupes de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aed7c-369">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
