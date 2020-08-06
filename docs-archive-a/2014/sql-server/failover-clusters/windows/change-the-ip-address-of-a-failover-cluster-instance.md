---
title: Modifier l’adresse IP d’une instance de cluster de basculement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- modifying IP addresses
- failover clustering [SQL Server], IP addresses
- IP addresses [SQL Server]
- clusters [SQL Server], IP addresses
ms.assetid: b685f400-cbfe-4c5d-a070-227a1123dae4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45d3ef0b70282efd870e4a076663719c2549deaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605023"
---
# <a name="change-the-ip-address-of-a-failover-cluster-instance"></a><span data-ttu-id="58bd3-102">Modifier l'adresse IP d'une instance de cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="58bd3-102">Change the IP Address of a Failover Cluster Instance</span></span>
  <span data-ttu-id="58bd3-103">Cette rubrique explique comment modifier la ressource d'adresse IP d'une instance de cluster de basculement (FCI) AlwaysOn à l'aide du composant logiciel enfichable Gestionnaire du cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="58bd3-103">This topic describes how to change the IP address resource in an AlwaysOn Failover Cluster Instance (FCI) by using the Failover Cluster Manager snap-in.</span></span> <span data-ttu-id="58bd3-104">Le composant logiciel enfichable Gestionnaire du cluster de basculement est l'application de gestion du service de cluster de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="58bd3-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Server Failover Clustering (WSFC) service.</span></span>  
  
-   <span data-ttu-id="58bd3-105">**Avant de commencer :**  [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="58bd3-105">**Before you begin:**  [Security](#Security)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="58bd3-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="58bd3-106">Before You Begin</span></span>  
 <span data-ttu-id="58bd3-107">Avant de commencer, consultez la rubrique [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Avant l’installation du clustering de basculement [dans la documentation en ligne de](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="58bd3-107">Before you begin, review the following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online topic: [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="58bd3-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="58bd3-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="58bd3-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="58bd3-109">Permissions</span></span>  
 <span data-ttu-id="58bd3-110">Pour maintenir ou mettre à jour une FCI, vous devez être un administrateur local et disposer des autorisations requises pour vous connecter en tant que service sur tous les nœuds de la FCI.</span><span class="sxs-lookup"><span data-stu-id="58bd3-110">To maintain or update an FCI, you must be a local administrator with permission to logon as a service on all nodes of the FCI.</span></span>  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="58bd3-111">Utilisation du composant logiciel enfichable Gestionnaire du cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="58bd3-111">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="58bd3-112">**Pour modifier la ressource d'adresse IP pour une FCI**</span><span class="sxs-lookup"><span data-stu-id="58bd3-112">**To change the IP address resource for an FCI**</span></span>  
  
1.  <span data-ttu-id="58bd3-113">Ouvrez le composant logiciel enfichable Gestionnaire du cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="58bd3-113">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="58bd3-114">Développez le nœud **Services et applications** dans le volet gauche et cliquez sur la FCI.</span><span class="sxs-lookup"><span data-stu-id="58bd3-114">Expand the **Services and applications** node, in the left pane and click on the FCI.</span></span>  
  
3.  <span data-ttu-id="58bd3-115">Dans le volet droit, sous la catégorie **Nom du serveur** , cliquez avec le bouton droit sur l’instance SQL Server et sélectionnez l’option **Propriétés** pour ouvrir la boîte de dialogue **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="58bd3-115">On the right pane, under the **Server Name** category, right-click the SQL Server Instance, and select **Properties** option to open the **Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="58bd3-116">Dans l'onglet **Général** , modifiez la ressource d'adresse IP.</span><span class="sxs-lookup"><span data-stu-id="58bd3-116">On the **General** tab, change the IP address resource.</span></span>  
  
5.  <span data-ttu-id="58bd3-117">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="58bd3-117">Click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="58bd3-118">Dans le volet droit, cliquez avec le bouton droit sur l’adresse IP SQL 1 (nom d’instance du cluster de basculement), puis sélectionnez **Mettre hors ligne**.</span><span class="sxs-lookup"><span data-stu-id="58bd3-118">In the right-hand pane, right-click the SQL IP Address1(failover cluster instance name) and select **Take Offline**.</span></span> <span data-ttu-id="58bd3-119">Vous voyez l'adresse IP SQL 1 (nom d'instance du cluster de basculement), le nom de réseau SQL (nom d'instance du cluster de basculement), ainsi que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] passant de l'état Connecté à l'état Déconnexion en cours, puis à l'état Déconnecté.</span><span class="sxs-lookup"><span data-stu-id="58bd3-119">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Online to Offline Pending, and then to Offline.</span></span>  
  
7.  <span data-ttu-id="58bd3-120">Dans le volet droit, cliquez avec le bouton droit sur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], puis sélectionnez **Mettre en ligne**.</span><span class="sxs-lookup"><span data-stu-id="58bd3-120">In the right-hand pane, right-click [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and then select **Bring Online**.</span></span> <span data-ttu-id="58bd3-121">Vous voyez l'adresse IP SQL 1 (nom d'instance du cluster de basculement), le nom de réseau SQL (nom d'instance du cluster de basculement), ainsi que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] passant de l'état Déconnecté à l'état Connexion en cours, puis à l'état Connecté.</span><span class="sxs-lookup"><span data-stu-id="58bd3-121">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Offline to Online Pending, and then to Online.</span></span>  
  
8.  <span data-ttu-id="58bd3-122">Fermez le composant logiciel enfichable Gestionnaire du cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="58bd3-122">Close the Failover Cluster Manager snap-in.</span></span>  
  
  
