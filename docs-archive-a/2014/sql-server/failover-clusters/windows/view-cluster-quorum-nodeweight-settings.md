---
title: Afficher les paramètres NodeWeight pour le quorum de cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: b845e73a-bb01-4de2-aac2-8ac12abebc95
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef2176d4916e8affbb9ef89c9b26499289c520ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605006"
---
# <a name="view-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="7a077-102">Afficher les paramètres NodeWeight pour le quorum de cluster</span><span class="sxs-lookup"><span data-stu-id="7a077-102">View Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="7a077-103">Cette rubrique explique comment afficher les paramètres NodeWeight pour chaque nœud membre dans un cluster de clustering de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="7a077-103">This topic describes how to view NodeWeight settings for each member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="7a077-104">Les paramètres NodeWeight sont utilisés pendant le vote du quorum pour prendre en charge les scénarios de récupération d'urgence et de sous-réseaux multiples pour [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] et les instances de cluster de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a077-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="7a077-105">**Avant de commencer :**  [Prérequis](#Prerequisites), [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="7a077-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="7a077-106">**Pour afficher les paramètres NodeWeight du quorum avec :** [Utilisation de Transact-SQL](#TsqlProcedure), [Utilisation de PowerShell](#PowerShellProcedure), [Utilisation de Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="7a077-106">**To view quorum NodeWeight settings using:** [Using Transact-SQL](#TsqlProcedure), [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a077-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7a077-107">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7a077-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="7a077-108">Prerequisites</span></span>  
 <span data-ttu-id="7a077-109">Cette fonctionnalité est prise en charge uniquement dans [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] ou versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="7a077-109">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7a077-110">Pour utiliser les paramètres NodeWeight, le correctif logiciel suivant doit être appliqué à tous les serveurs dans le cluster WSFC :</span><span class="sxs-lookup"><span data-stu-id="7a077-110">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="7a077-111">[KB2494036](https://support.microsoft.com/kb/2494036) : un correctif est disponible pour vous permettre de configurer un nœud de cluster qui n'a pas de votes de quorum dans [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] et dans [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a077-111">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="7a077-112">Si ce correctif logiciel n'est pas installé, les exemples de cette rubrique retournent des valeurs vides ou NULL pour NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="7a077-112">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a077-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7a077-113">Security</span></span>  
 <span data-ttu-id="7a077-114">L'utilisateur doit être un compte de domaine qui est membre du groupe Administrateurs local sur chaque nœud du cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="7a077-114">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a077-115">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a077-115">Using Transact-SQL</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="7a077-116">Pour consulter les paramètres NodeWeight</span><span class="sxs-lookup"><span data-stu-id="7a077-116">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="7a077-117">Connectez-vous à une instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans le cluster.</span><span class="sxs-lookup"><span data-stu-id="7a077-117">Connect to any [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the cluster.</span></span>  
  
2.  <span data-ttu-id="7a077-118">Interrogez la vue [sys].[dm_hadr_cluster_members].</span><span class="sxs-lookup"><span data-stu-id="7a077-118">Query the [sys].[dm_hadr_cluster_members] view.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="7a077-119">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7a077-119">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="7a077-120">L’exemple suivant interroge une vue système pour retourner les valeurs de tous les nœuds du cluster de cette instance.</span><span class="sxs-lookup"><span data-stu-id="7a077-120">The following example queries a system view to return values for all of the nodes in that instance's cluster.</span></span>  
  
```sql  
SELECT  member_name, member_state_desc, number_of_quorum_votes  
 FROM   sys.dm_hadr_cluster_members;  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="7a077-121">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a077-121">Using Powershell</span></span>  
  
### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="7a077-122">Pour consulter les paramètres NodeWeight</span><span class="sxs-lookup"><span data-stu-id="7a077-122">To view NodeWeight settings</span></span>
  
1.  <span data-ttu-id="7a077-123">Démarrez Windows PowerShell avec élévation de privilèges via **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="7a077-123">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="7a077-124">Importez le module `FailoverClusters` pour activer les applets de commande de cluster.</span><span class="sxs-lookup"><span data-stu-id="7a077-124">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="7a077-125">Utilisez l'objet `Get-ClusterNode` pour retourner une collection d'objets du nœud de cluster.</span><span class="sxs-lookup"><span data-stu-id="7a077-125">Use the `Get-ClusterNode` object to return a collection of cluster node objects.</span></span>  
  
4.  <span data-ttu-id="7a077-126">Générez la sortie des propriétés du nœud de cluster dans un format lisible.</span><span class="sxs-lookup"><span data-stu-id="7a077-126">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="7a077-127">Exemple (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="7a077-127">Example (Powershell)</span></span>  
 <span data-ttu-id="7a077-128">L’exemple suivant génère certaines des propriétés de nœud du cluster « Cluster001 ».</span><span class="sxs-lookup"><span data-stu-id="7a077-128">The following example output some of the node properties for the cluster called "Cluster001".</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$cluster = "Cluster001"  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -Property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="7a077-129">Utilisation de Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="7a077-129">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a077-130">L'utilitaire cluster.exe est déconseillé dans [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a077-130">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="7a077-131">Utilisez PowerShell avec le clustering de basculement pour le développement futur.</span><span class="sxs-lookup"><span data-stu-id="7a077-131">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="7a077-132">L'utilitaire cluster.exe sera supprimé dans la prochaine version de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7a077-132">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="7a077-133">Pour plus d'informations, consultez [Mappage des commandes Cluster.exe aux applets de commande Windows PowerShell pour les clusters de basculement](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="7a077-133">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="7a077-134">Pour consulter les paramètres NodeWeight</span><span class="sxs-lookup"><span data-stu-id="7a077-134">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="7a077-135">Démarrez une invite de commandes avec élévation de privilèges via **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="7a077-135">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="7a077-136">Utilisez **cluster.exe** pour retourner l'état du nœud et les valeurs de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="7a077-136">Use **cluster.exe** to return node status and NodeWeight values</span></span>  
  
### <a name="example-clusterexe"></a><span data-ttu-id="7a077-137">Exemple (Cluster.exe)</span><span class="sxs-lookup"><span data-stu-id="7a077-137">Example (Cluster.exe)</span></span>  
 <span data-ttu-id="7a077-138">L’exemple suivant génère certaines des propriétés de nœud du cluster « Cluster001 ».</span><span class="sxs-lookup"><span data-stu-id="7a077-138">The following example outputs some of the node properties for the cluster called "Cluster001".</span></span>  
  
```cmd
cluster.exe Cluster001 node /status /properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a077-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a077-139">See Also</span></span>  
 <span data-ttu-id="7a077-140">[Modes de quorum WSFC et configuration de vote &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a077-140">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="7a077-141">[Configurer les paramètres NodeWeight pour un quorum de cluster](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7a077-141">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="7a077-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a077-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span></span>  
 <span data-ttu-id="7a077-143">[Applets de commande de cluster de basculement dans Windows PowerShell répertoriées par tâche](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a077-143">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
