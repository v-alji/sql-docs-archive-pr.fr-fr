---
title: MSSQLSERVER_41030 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41030 (Database Engine error)
ms.assetid: c85341ae-0fbf-42ae-9275-4cfe678238f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b137b739d4c1641b88983708df62d2e52fd0eab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705156"
---
# <a name="mssqlserver_41030"></a><span data-ttu-id="efa65-102">MSSQLSERVER_41030</span><span class="sxs-lookup"><span data-stu-id="efa65-102">MSSQLSERVER_41030</span></span>
    
## <a name="details"></a><span data-ttu-id="efa65-103">Détails</span><span class="sxs-lookup"><span data-stu-id="efa65-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efa65-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="efa65-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="efa65-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="efa65-105">Event ID</span></span>|<span data-ttu-id="efa65-106">41030</span><span class="sxs-lookup"><span data-stu-id="efa65-106">41030</span></span>|  
|<span data-ttu-id="efa65-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="efa65-107">Event Source</span></span>|<span data-ttu-id="efa65-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="efa65-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="efa65-109">Composant</span><span class="sxs-lookup"><span data-stu-id="efa65-109">Component</span></span>|<span data-ttu-id="efa65-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="efa65-110">SQLEngine</span></span>|  
|<span data-ttu-id="efa65-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="efa65-111">Symbolic Name</span></span>|<span data-ttu-id="efa65-112">OPEN_CLUSTER_SUB_KEY</span><span class="sxs-lookup"><span data-stu-id="efa65-112">OPEN_CLUSTER_SUB_KEY</span></span>|  
|<span data-ttu-id="efa65-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="efa65-113">Message Text</span></span>|<span data-ttu-id="efa65-114">Échec de l'ouverture de la sous-clé de Registre de clustering de basculement Windows Server « %.\*ls » (code d'erreur %d).</span><span class="sxs-lookup"><span data-stu-id="efa65-114">Failed to open the Windows Server Failover Clustering registry subkey '%.\*ls' (Error code %d).</span></span>  <span data-ttu-id="efa65-115">La clé parente est la clé racine de cluster.</span><span class="sxs-lookup"><span data-stu-id="efa65-115">The parent key is the cluster root key.</span></span>  <span data-ttu-id="efa65-116">Le service WSFC n'est peut-être pas en cours d'exécution ou n'est pas disponible dans son état actuel, ou les arguments spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="efa65-116">The WSFC service may not be running or may not be accessible in its current state, or the specified arguments are invalid.</span></span> <span data-ttu-id="efa65-117">Si le groupe de disponibilité correspondant a été supprimé, cette erreur est attendue.</span><span class="sxs-lookup"><span data-stu-id="efa65-117">If the corresponding availability group has been dropped, this error is expected.</span></span> <span data-ttu-id="efa65-118">Pour plus d'informations sur ce code d'erreur, consultez « codes d'erreur système » dans la documentation relative au développement Windows.</span><span class="sxs-lookup"><span data-stu-id="efa65-118">For information about this error code, see "System Error Codes" in the Windows Development documentation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="efa65-119">Explication</span><span class="sxs-lookup"><span data-stu-id="efa65-119">Explanation</span></span>  
 <span data-ttu-id="efa65-120">Si un cluster WSFC est détruit, toutes les clés de Registre associées à [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="efa65-120">If a WSFC cluster is destroyed, it removes all registry keys related to [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="efa65-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="efa65-121">User Action</span></span>  
 <span data-ttu-id="efa65-122">Après recréation d'un cluster WSFC, désactivez et réactivez ensuite AlwaysOn sur chaque nœud de cluster sur lequel une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est activée pour AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="efa65-122">After re-creating a WSFC cluster, disable and then re-enable AlwaysOn on every cluster node on which an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is enabled for AlwaysOn.</span></span> <span data-ttu-id="efa65-123">Vous pouvez utiliser le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour cette tâche.</span><span class="sxs-lookup"><span data-stu-id="efa65-123">You can use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for this task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa65-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="efa65-124">See Also</span></span>  
 <span data-ttu-id="efa65-125">[Activer et désactiver les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="efa65-125">[Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="efa65-126">Clustering de basculement Windows Server &#40;WSFC&#41; avec SQL Server</span><span class="sxs-lookup"><span data-stu-id="efa65-126">Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server</span></span>](../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md)  
  
  
