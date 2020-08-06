---
title: Configurer les paramètres NodeWeight pour un quorum de cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: cb3fd9a6-39a2-4e9c-9157-619bf3db9951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e469d5fc0fc030304a7cf2f1bdd894eb578aa056
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605021"
---
# <a name="configure-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="a3083-102">Configurer les paramètres NodeWeight pour un quorum de cluster</span><span class="sxs-lookup"><span data-stu-id="a3083-102">Configure Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="a3083-103">Cette rubrique explique comment configurer les paramètres NodeWeight pour un nœud membre dans un cluster de clustering de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="a3083-103">This topic describes how to configure NodeWeight settings for a member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="a3083-104">Les paramètres NodeWeight sont utilisés pendant le vote du quorum pour prendre en charge les scénarios de récupération d'urgence et de sous-réseaux multiples pour [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] et les instances de cluster de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3083-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="a3083-105">**Avant de commencer :**  [Prérequis](#Prerequisites), [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="a3083-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="a3083-106">**Pour afficher les paramètres NodeWeight du quorum avec :** [Utilisation de PowerShell](#PowerShellProcedure), [Utilisation de Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="a3083-106">**To view quorum NodeWeight settings using:** [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
-   [<span data-ttu-id="a3083-107">Contenu connexe</span><span class="sxs-lookup"><span data-stu-id="a3083-107">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a3083-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a3083-108">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a3083-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="a3083-109">Prerequisites</span></span>  
 <span data-ttu-id="a3083-110">Cette fonctionnalité est prise en charge uniquement dans [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] ou versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="a3083-110">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a3083-111">Pour utiliser les paramètres NodeWeight, le correctif logiciel suivant doit être appliqué à tous les serveurs dans le cluster WSFC :</span><span class="sxs-lookup"><span data-stu-id="a3083-111">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="a3083-112">[KB2494036](https://support.microsoft.com/kb/2494036) : un correctif est disponible pour vous permettre de configurer un nœud de cluster qui n'a pas de votes de quorum dans [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] et dans [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3083-112">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a3083-113">Si ce correctif logiciel n'est pas installé, les exemples de cette rubrique retournent des valeurs vides ou NULL pour NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="a3083-113">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a3083-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a3083-114">Security</span></span>  
 <span data-ttu-id="a3083-115">L'utilisateur doit être un compte de domaine qui est membre du groupe Administrateurs local sur chaque nœud du cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="a3083-115">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a3083-116">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3083-116">Using Powershell</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="a3083-117">Pour configurer les paramètres NodeWeight</span><span class="sxs-lookup"><span data-stu-id="a3083-117">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="a3083-118">Démarrez Windows PowerShell avec élévation de privilèges via **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="a3083-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="a3083-119">Importez le module `FailoverClusters` pour activer les applets de commande de cluster.</span><span class="sxs-lookup"><span data-stu-id="a3083-119">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="a3083-120">Utilisez l'objet `Get-ClusterNode` pour définir la propriété `NodeWeight` pour chaque nœud du cluster.</span><span class="sxs-lookup"><span data-stu-id="a3083-120">Use the `Get-ClusterNode` object to set the `NodeWeight` property for each node in the cluster.</span></span>  
  
4.  <span data-ttu-id="a3083-121">Générez la sortie des propriétés du nœud de cluster dans un format lisible.</span><span class="sxs-lookup"><span data-stu-id="a3083-121">Output the cluster node properties in a readable format.</span></span>  
  
 <span data-ttu-id="a3083-122">L’exemple suivant modifie le paramètre NodeWeight pour supprimer le vote du quorum pour le nœud « AlwaysOnSrv1 », puis génère les paramètres pour tous les nœuds du cluster.</span><span class="sxs-lookup"><span data-stu-id="a3083-122">The following example changes the NodeWeight setting to remove the quorum vote for the "AlwaysOnSrv1" node, and then outputs the settings for all nodes in the cluster.</span></span>
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv1"  
(Get-ClusterNode $node).NodeWeight = 0  
  
$cluster = (Get-ClusterNode $node).Cluster  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="a3083-123">Utilisation de Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="a3083-123">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3083-124">L'utilitaire cluster.exe est déconseillé dans [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3083-124">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="a3083-125">Utilisez PowerShell avec le clustering de basculement pour le développement futur.</span><span class="sxs-lookup"><span data-stu-id="a3083-125">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="a3083-126">L'utilitaire cluster.exe sera supprimé dans la prochaine version de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a3083-126">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="a3083-127">Pour plus d'informations, consultez [Mappage des commandes Cluster.exe aux applets de commande Windows PowerShell pour les clusters de basculement](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="a3083-127">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="a3083-128">Pour configurer les paramètres NodeWeight</span><span class="sxs-lookup"><span data-stu-id="a3083-128">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="a3083-129">Démarrez une invite de commandes avec élévation de privilèges via **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="a3083-129">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="a3083-130">Utilisez **cluster.exe** pour définir les valeurs `NodeWeight` .</span><span class="sxs-lookup"><span data-stu-id="a3083-130">Use **cluster.exe** to set `NodeWeight` values.</span></span>  

 <span data-ttu-id="a3083-131">L’exemple suivant modifie la valeur NodeWeight pour supprimer le vote du quorum pour le nœud « AlwaysOnSrv1 » dans le cluster « Cluster001 ».</span><span class="sxs-lookup"><span data-stu-id="a3083-131">The following example changes the NodeWeight value to remove the quorum vote of the "AlwaysOnSrv1" node in the "Cluster001" cluster.</span></span>  
  
```cmd
cluster.exe Cluster001 node AlwaysOnSrv1 /prop NodeWeight=0  
```  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="a3083-132">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="a3083-132">Related Content</span></span>  
  
-   <span data-ttu-id="a3083-133">[Afficher les événements et journaux pour un cluster de basculement](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a3083-133">[View Events and Logs for a Failover Cluster](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="a3083-134">Applets de commande de cluster de basculement Get-ClusterLog</span><span class="sxs-lookup"><span data-stu-id="a3083-134">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="a3083-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3083-135">See Also</span></span>  
 <span data-ttu-id="a3083-136">[Modes de quorum WSFC et configuration de vote &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a3083-136">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="a3083-137">[Afficher les paramètres NodeWeight du quorum du cluster](view-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="a3083-137">[View Cluster Quorum NodeWeight Settings](view-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="a3083-138">[Applets de commande de cluster de basculement dans Windows PowerShell répertoriées par tâche](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a3083-138">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
