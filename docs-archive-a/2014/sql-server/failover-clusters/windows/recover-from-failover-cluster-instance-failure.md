---
title: Récupérer à partir d’une défaillance d’instance de cluster de basculement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], recovery from failure
- failover clustering [SQL Server], recovery from failure
- hardware failures [SQL Server]
- recovering failover cluster failures [SQL Server]
ms.assetid: 3d151d0c-e841-4325-8606-c094de37d7d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60db4c2e480b094c18d0a8071e947a38cdc779d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708112"
---
# <a name="recover-from-failover-cluster-instance-failure"></a><span data-ttu-id="18f36-102">Récupérer à partir d'une défaillance d'instance de cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="18f36-102">Recover from Failover Cluster Instance Failure</span></span>
  <span data-ttu-id="18f36-103">Cette rubrique explique comment récupérer des échecs de cluster à l'aide du composant logiciel enfichable Gestionnaire du cluster de basculement après un basculement dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18f36-103">This topic describes how to recover from cluster failures by using the Failover Cluster Manager snap-in after a failover occurs in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="18f36-104">Le composant logiciel enfichable Gestionnaire du cluster de basculement est l'application de gestion du service de cluster de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="18f36-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Serer Failover Clustering (WSFC) service.</span></span>  
  
-   [<span data-ttu-id="18f36-105">Récupération suite à une défaillance irréparable</span><span class="sxs-lookup"><span data-stu-id="18f36-105">Recover from an irreparable failure</span></span>](#Scenario1)  
  
-   [<span data-ttu-id="18f36-106">Récupérer en cas d'erreur logicielle</span><span class="sxs-lookup"><span data-stu-id="18f36-106">Recover from a software failure</span></span>](#Scenario2)  
  
##  <a name="recover-from-an-irreparable-failure"></a><a name="Scenario1"></a> <span data-ttu-id="18f36-107">Récupérer en cas d'erreur irréparable</span><span class="sxs-lookup"><span data-stu-id="18f36-107">Recover from an irreparable failure</span></span>  
 <span data-ttu-id="18f36-108">Utilisez les étapes suivantes pour récupérer une erreur irréparable.</span><span class="sxs-lookup"><span data-stu-id="18f36-108">Use the following steps to recover from an irreparable failure.</span></span> <span data-ttu-id="18f36-109">L'erreur peut être provoquée, par exemple, par la défaillance d'un contrôleur de disque ou du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="18f36-109">The failure could be caused, for example, by the failure of a disk controller or the operating system.</span></span> <span data-ttu-id="18f36-110">Dans ce cas, l'erreur est due à une défaillance matérielle dans le nœud 1 d'un cluster à deux nœuds.</span><span class="sxs-lookup"><span data-stu-id="18f36-110">In this case, failure is caused by hardware failure in Node 1 of a two-node cluster.</span></span>  
  
1.  <span data-ttu-id="18f36-111">Après la défaillance du nœud 1, la FCI de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] bascule sur le nœud 2.</span><span class="sxs-lookup"><span data-stu-id="18f36-111">After Node 1 fails, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="18f36-112">Supprimez le nœud 1 de la FCI.</span><span class="sxs-lookup"><span data-stu-id="18f36-112">Evict Node 1 from the FCI.</span></span> <span data-ttu-id="18f36-113">Pour cela, à partir du nœud 2, ouvrez le composant logiciel enfichable Gestionnaire du cluster de basculement, cliquez avec le bouton droit sur Node1, cliquez sur **Déplacer des actions**, puis sur **Supprimer le nœud**.</span><span class="sxs-lookup"><span data-stu-id="18f36-113">To do this, from Node 2, open the Failover Cluster Manager snap-in, right-click Node1, click **Move Actions**, and then click **Evict Node**.</span></span>  
  
3.  <span data-ttu-id="18f36-114">Assurez-vous que le nœud 1 a été supprimé de la définition de cluster.</span><span class="sxs-lookup"><span data-stu-id="18f36-114">Verify that Node 1 has been evicted from the cluster definition.</span></span>  
  
4.  <span data-ttu-id="18f36-115">Installez le nouveau matériel pour remplacer le matériel défaillant dans le nœud 1.</span><span class="sxs-lookup"><span data-stu-id="18f36-115">Install new hardware to replace the failed hardware in Node 1.</span></span>  
  
5.  <span data-ttu-id="18f36-116">Ajoutez le nœud 1 au cluster existant à l'aide du composant logiciel enfichable Gestionnaire du cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="18f36-116">Using the Failover Cluster Manager snap-in, add Node 1 to the existing cluster.</span></span> <span data-ttu-id="18f36-117">Pour plus d’informations, consultez [Avant l’installation du clustering de basculement](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="18f36-117">For more information, see [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
6.  <span data-ttu-id="18f36-118">Vérifiez que les comptes administrateurs sont bien les mêmes sur tous les nœuds de cluster.</span><span class="sxs-lookup"><span data-stu-id="18f36-118">Ensure that the administrator accounts are the same on all cluster nodes.</span></span>  
  
7.  <span data-ttu-id="18f36-119">Exécutez le programme d'installation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] afin d'ajouter le nœud 1 à la FCI.</span><span class="sxs-lookup"><span data-stu-id="18f36-119">Run [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup to add Node 1 to the FCI.</span></span> <span data-ttu-id="18f36-120">Pour plus d’informations, consultez [Ajouter ou supprimer des nœuds dans un cluster de basculement SQL Server &#40;d’installation&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="18f36-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
##  <a name="recover-from-a-reparable-failure"></a><a name="Scenario2"></a> <span data-ttu-id="18f36-121">Récupérer d'une erreur réparable</span><span class="sxs-lookup"><span data-stu-id="18f36-121">Recover from a reparable failure</span></span>  
 <span data-ttu-id="18f36-122">Utilisez les étapes suivantes pour récupérer suite à une erreur réparable.</span><span class="sxs-lookup"><span data-stu-id="18f36-122">Us the following steps to recover from a reparable failure.</span></span> <span data-ttu-id="18f36-123">Dans ce cas, la défaillance est causée par le nœud 1, défectueux ou hors connexion, mais il n'est pas rompu de manière irrémédiable.</span><span class="sxs-lookup"><span data-stu-id="18f36-123">In this case, failure is caused by Node 1 being down or offline but not irretrievably broken.</span></span> <span data-ttu-id="18f36-124">Cette erreur peut être due à une défaillance du système d'exploitation, à une défaillance matérielle ou à une défaillance dans l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] elle-même.</span><span class="sxs-lookup"><span data-stu-id="18f36-124">This could be caused by an operating system failure, hardware failure, or failure in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance itself.</span></span>  
  
1.  <span data-ttu-id="18f36-125">Après la défaillance du nœud 1, la FCI bascule sur le nœud 2.</span><span class="sxs-lookup"><span data-stu-id="18f36-125">After Node 1 fails, the FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="18f36-126">Résolvez le problème du nœud 1.</span><span class="sxs-lookup"><span data-stu-id="18f36-126">Resolve the problem with Node 1.</span></span>  
  
3.  <span data-ttu-id="18f36-127">Vérifiez que le service WSFC fonctionne et que tous les nœuds sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="18f36-127">Ensure that all nodes are online and the WSFC service is working.</span></span>  
  
4.  <span data-ttu-id="18f36-128">Effectuez le basculement de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vers le nœud récupéré.</span><span class="sxs-lookup"><span data-stu-id="18f36-128">Fail over [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the recovered node.</span></span>  
  
  
