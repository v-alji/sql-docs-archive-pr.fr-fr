---
title: Forcer un cluster WSFC à démarrer sans quorum | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: 4a121375-7424-4444-b876-baefa8fe9015
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6f2110b706de015d0c7b19475b335908c118267
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605009"
---
# <a name="force-a-wsfc-cluster-to-start-without-a-quorum"></a><span data-ttu-id="3b292-102">Forcer un cluster WSFC à démarrer sans quorum</span><span class="sxs-lookup"><span data-stu-id="3b292-102">Force a WSFC Cluster to Start Without a Quorum</span></span>
  <span data-ttu-id="3b292-103">Cette rubrique explique comment forcer un nœud de cluster de clustering de basculement Windows Server (WSFC) à démarrer sans quorum.</span><span class="sxs-lookup"><span data-stu-id="3b292-103">This topic describes how to force a Windows Server Failover Clustering (WSFC) cluster node to start without a quorum.</span></span>  <span data-ttu-id="3b292-104">Cela peut être nécessaire dans les scénarios de récupération d'urgence et de sous-réseaux multiples pour récupérer des données et pour rétablir entièrement la haute disponibilité pour [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] et les instances de cluster de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b292-104">This may be required in disaster recovery and multi-subnet scenarios to recover data and fully re-establish high-availability for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="3b292-105">**Avant de commencer :**  [Recommandations](#Recommendations), [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="3b292-105">**Before you start:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="3b292-106">**Pour forcer un cluster à démarrer sans quorum :**  [Utilisation du Gestionnaire du cluster de basculement](#FailoverClusterManagerProcedure), [Utilisation de PowerShell](#PowerShellProcedure), [Utilisation de Net.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="3b292-106">**To force a cluster to start without a quorum using:**  [Using Failover Cluster Manager](#FailoverClusterManagerProcedure), [Using Powershell](#PowerShellProcedure), [Using Net.exe](#CommandPromptProcedure)</span></span>  
  
-   <span data-ttu-id="3b292-107">**Suivi :**  [Suivi : après avoir forcé le cluster à démarrer sans quorum](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="3b292-107">**Follow up:**  [Follow Up: After Forcing Cluster to Start without a Quorum](#FollowUp)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3b292-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="3b292-108">Before You Start</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3b292-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="3b292-109">Recommendations</span></span>  
 <span data-ttu-id="3b292-110">Sauf instructions spécifiques, les procédures de cette rubrique doivent fonctionner si vous les exécutez à partir de n'importe quel nœud du cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="3b292-110">Except where explicitly directed, the procedures in this topic should work if you execute them from any node in the WSFC cluster.</span></span>  <span data-ttu-id="3b292-111">Toutefois, vous pouvez obtenir de meilleurs résultats, et éviter des problèmes de connexion, en exécutant ces étapes à partir du nœud que vous envisagez de forcer à démarrer sans quorum.</span><span class="sxs-lookup"><span data-stu-id="3b292-111">However, you may obtain better results, and avoid networking issues, by executing these steps from the node that you intend to force to start without a quorum.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3b292-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="3b292-112">Security</span></span>  
 <span data-ttu-id="3b292-113">L'utilisateur doit être un compte de domaine qui est membre du groupe Administrateurs local sur chaque nœud du cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="3b292-113">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-failover-cluster-manager"></a><a name="FailoverClusterManagerProcedure"></a><span data-ttu-id="3b292-114">Utilisation de Gestionnaire du cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="3b292-114">Using Failover Cluster Manager</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="3b292-115">Pour forcer un cluster à démarrer sans quorum</span><span class="sxs-lookup"><span data-stu-id="3b292-115">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="3b292-116">Ouvrez un Gestionnaire du cluster de basculement et connectez-vous au nœud de cluster souhaité pour forcer la mise en ligne.</span><span class="sxs-lookup"><span data-stu-id="3b292-116">Open a Failover Cluster Manager and connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="3b292-117">Dans le volet **actions** , cliquez sur **forcer le démarrage du cluster**, puis sur **Oui-forcer mon cluster à démarrer**.</span><span class="sxs-lookup"><span data-stu-id="3b292-117">In the **Actions** pane, click **Force Cluster Start**, and then click **Yes - Force my cluster to start**.</span></span>  
  
3.  <span data-ttu-id="3b292-118">Dans le volet gauche, dans l'arborescence du **Gestionnaire du cluster de basculement** , cliquez sur le nom de cluster.</span><span class="sxs-lookup"><span data-stu-id="3b292-118">In the left pane, in the **Failover Cluster Manager** tree, click the cluster name.</span></span>  
  
4.  <span data-ttu-id="3b292-119">Dans le volet résumé, vérifiez que la valeur active de **Configuration de quorum** est  **Avertissement : le cluster s'exécute dans l'état ForceQuorum**.</span><span class="sxs-lookup"><span data-stu-id="3b292-119">In the summary pane, confirm that the current **Quorum Configuration** value is:  **Warning: Cluster is running in ForceQuorum state**.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a><span data-ttu-id="3b292-120">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b292-120">Using Powershell</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="3b292-121">Pour forcer un cluster à démarrer sans quorum</span><span class="sxs-lookup"><span data-stu-id="3b292-121">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="3b292-122">Démarrez Windows PowerShell avec élévation de privilèges via **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="3b292-122">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="3b292-123">Importez le module `FailoverClusters` pour activer les applets de commande de cluster.</span><span class="sxs-lookup"><span data-stu-id="3b292-123">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="3b292-124">Utilisez `Stop-ClusterNode` pour vous assurer que le service de cluster est arrêté.</span><span class="sxs-lookup"><span data-stu-id="3b292-124">Use `Stop-ClusterNode` to make sure that the cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="3b292-125">Utilisez `Start-ClusterNode` avec `-FixQuorum` pour forcer le service de cluster à démarrer.</span><span class="sxs-lookup"><span data-stu-id="3b292-125">Use `Start-ClusterNode` with `-FixQuorum` to force the cluster service to start.</span></span>  
  
5.  <span data-ttu-id="3b292-126">Utilisez `Get-ClusterNode` avec `-Propery NodeWieght = 1` pour définir la valeur qui garantit que le nœud est un membre du quorum disposant de droits de vote.</span><span class="sxs-lookup"><span data-stu-id="3b292-126">Use `Get-ClusterNode` with `-Propery NodeWieght = 1` to set the value the guarantees that the node is a voting member of the quorum.</span></span>  
  
6.  <span data-ttu-id="3b292-127">Générez la sortie des propriétés du nœud de cluster dans un format lisible.</span><span class="sxs-lookup"><span data-stu-id="3b292-127">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="3b292-128">Exemple (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="3b292-128">Example (Powershell)</span></span>  
 <span data-ttu-id="3b292-129">L'exemple suivant force le service de cluster du nœud AlwaysOnSrv02 à démarrer sans quorum, définit `NodeWeight = 1`, puis énumère l'état du nœud de cluster à partir du nœud récemment forcé.</span><span class="sxs-lookup"><span data-stu-id="3b292-129">The following example forces the AlwaysOnSrv02 node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv02"  
Stop-ClusterNode -Name $node  
Start-ClusterNode -Name $node -FixQuorum  
  
(Get-ClusterNode $node).NodeWeight = 1  
  
$nodes = Get-ClusterNode -Cluster $node  
$nodes | Format-Table -property NodeName, State, NodeWeight
```  
  
##  <a name="using-netexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="3b292-130">Utilisation de Net.exe</span><span class="sxs-lookup"><span data-stu-id="3b292-130">Using Net.exe</span></span>  
  
### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="3b292-131">Pour forcer un cluster à démarrer sans quorum</span><span class="sxs-lookup"><span data-stu-id="3b292-131">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="3b292-132">Utilisez le Bureau à distance pour vous connecter au nœud de cluster souhaité pour forcer la mise en ligne.</span><span class="sxs-lookup"><span data-stu-id="3b292-132">Use Remote Desktop to connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="3b292-133">Démarrez une invite de commandes avec élévation de privilèges via **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="3b292-133">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
3.  <span data-ttu-id="3b292-134">Utilisez **net.exe** pour vous assurer que le service de cluster local est arrêté.</span><span class="sxs-lookup"><span data-stu-id="3b292-134">Use **net.exe** to make sure that the local cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="3b292-135">Utilisez **net.exe** avec `/forcequorum` pour forcer le service de cluster local à démarrer.</span><span class="sxs-lookup"><span data-stu-id="3b292-135">Use **net.exe** with `/forcequorum` to force the local cluster service to start.</span></span>  
  
### <a name="example-netexe"></a><span data-ttu-id="3b292-136">Exemple (Net.exe)</span><span class="sxs-lookup"><span data-stu-id="3b292-136">Example (Net.exe)</span></span>  
 <span data-ttu-id="3b292-137">L'exemple suivant force le service de cluster d'un nœud à démarrer sans quorum, définit `NodeWeight = 1`, puis énumère l'état du nœud de cluster à partir du nœud récemment forcé.</span><span class="sxs-lookup"><span data-stu-id="3b292-137">The following example forces a node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```cmd
net.exe stop clussvc  
net.exe start clussvc /forcequorum  
```  
  
##  <a name="follow-up-after-forcing-cluster-to-start-without-a-quorum"></a><a name="FollowUp"></a><span data-ttu-id="3b292-138">Suivi : après avoir forcé le cluster à démarrer sans quorum</span><span class="sxs-lookup"><span data-stu-id="3b292-138">Follow Up: After Forcing Cluster to Start without a Quorum</span></span>  
  
-   <span data-ttu-id="3b292-139">Vous devez réévaluer et reconfigurer les valeurs NodeWeight pour construire correctement un nouveau quorum avant de mettre en ligne d'autres nœuds.</span><span class="sxs-lookup"><span data-stu-id="3b292-139">You must re-evaluate and reconfigure NodeWeight values to correctly construct a new quorum before bringing other nodes back online.</span></span> <span data-ttu-id="3b292-140">Sinon, le cluster peut de nouveau se trouver hors connexion.</span><span class="sxs-lookup"><span data-stu-id="3b292-140">Otherwise, the cluster may go back offline again.</span></span>  
  
     <span data-ttu-id="3b292-141">Pour plus d’informations, consultez [Modes de quorum WSFC et configuration de vote &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3b292-141">For more information, see [WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="3b292-142">Les procédures de cette rubrique ne constituent qu'une étape de la mise en ligne du cluster WSFC si un échec non planifié du quorum se produit.</span><span class="sxs-lookup"><span data-stu-id="3b292-142">The procedures in this topic are only one step in bringing the WSFC cluster back online if an un-planned quorum failure were to occur.</span></span>  <span data-ttu-id="3b292-143">Vous pouvez aussi effectuer des étapes supplémentaires pour empêcher d'autres nœuds de cluster WSFC d'interférer avec la nouvelle configuration de quorum.</span><span class="sxs-lookup"><span data-stu-id="3b292-143">You may also want to take additional steps to prevent other WSFC cluster nodes from interfering with the new quorum configuration.</span></span>  
  
-   <span data-ttu-id="3b292-144">D'autres fonctionnalités [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , telles que [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], la mise en miroir de bases de données et la copie des journaux de transaction peuvent également nécessiter les actions suivantes pour récupérer les données et rétablir entièrement la haute disponibilité.</span><span class="sxs-lookup"><span data-stu-id="3b292-144">Other [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features such as [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], database mirroring, and log shipping may also require subsequent actions to recover data and to fully re-establish high-availability.</span></span>  
  
     <span data-ttu-id="3b292-145">**Pour plus d’informations :**</span><span class="sxs-lookup"><span data-stu-id="3b292-145">**For more information:**</span></span>  
  
     [<span data-ttu-id="3b292-146">Effectuer un basculement manuel forcé d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3b292-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](../../../database-engine/availability-groups/windows/perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
     [<span data-ttu-id="3b292-147">Forcer le service dans une session de mise en miroir de bases de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3b292-147">Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](../../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md)  
  
     [<span data-ttu-id="3b292-148">Basculer vers un serveur secondaire d’envoi de journaux &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3b292-148">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](../../../database-engine/log-shipping/fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="3b292-149">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="3b292-149">Related Content</span></span>  
  
-   <span data-ttu-id="3b292-150">[Afficher les événements et journaux pour un cluster de basculement](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="3b292-150">[View Events and Logs for a Failover Cluster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span></span>  
  
-   [<span data-ttu-id="3b292-151">Applets de commande de cluster de basculement Get-ClusterLog</span><span class="sxs-lookup"><span data-stu-id="3b292-151">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="3b292-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3b292-152">See Also</span></span>  
 <span data-ttu-id="3b292-153">[Récupération d’urgence WSFC par le quorum forcé &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3b292-153">[WSFC Disaster Recovery through Forced Quorum &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span></span>  
 <span data-ttu-id="3b292-154">[Configurer les paramètres NodeWeight du quorum du cluster](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3b292-154">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="3b292-155">[Applets de commande de cluster de basculement dans Windows PowerShell répertoriées par tâche](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3b292-155">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
