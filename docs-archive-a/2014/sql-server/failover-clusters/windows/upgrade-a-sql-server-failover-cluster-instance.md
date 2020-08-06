---
title: Mettre à niveau un cluster de basculement SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- upgrading failover clusters
- clusters [SQL Server], upgrading
- failover clustering [SQL Server], upgrading
ms.assetid: daac41fe-7d0b-4f14-84c2-62952ad8cbfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ca08e83c362e714f234a60ee358df3bcb03ade93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605008"
---
# <a name="upgrade-a-sql-server-failover-cluster"></a><span data-ttu-id="1666f-102">Mettre à niveau un cluster de basculement SQL Server</span><span class="sxs-lookup"><span data-stu-id="1666f-102">Upgrade a SQL Server Failover Cluster</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="1666f-103">prend en charge la mise à niveau du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] et d'[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] à partir des clusters de basculement [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] et [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] séparément sur tous les nœuds de cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="1666f-103">supports upgrade of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)], and [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all failover cluster nodes.</span></span>  
  
 <span data-ttu-id="1666f-104">Voici les détails de prise en charge :</span><span class="sxs-lookup"><span data-stu-id="1666f-104">Support details are as follows:</span></span>  
  
-   <span data-ttu-id="1666f-105">La mise à niveau est prise en charge par le biais de l'interface utilisateur et à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="1666f-105">Upgrade is supported both through the user interface and from the command prompt.</span></span> <span data-ttu-id="1666f-106">Pour plus d’informations, consultez [Mettre à niveau une instance de cluster de basculement SQL Server &#40;programme d’installation&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) et [Installer SQL Server 2014 à partir de l’invite de commandes](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="1666f-106">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) and [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
-   <span data-ttu-id="1666f-107">Mise à niveau à partir de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] : vous pouvez exécuter la mise à niveau à partir de l’invite de commandes sur chaque nœud de cluster de basculement ou en utilisant l’interface utilisateur du programme d’installation pour mettre à niveau chaque nœud de cluster.</span><span class="sxs-lookup"><span data-stu-id="1666f-107">Upgrading from [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] - You can run upgrade from the command prompt on each failover cluster node, or by using the Setup UI to upgrade each cluster node.</span></span> <span data-ttu-id="1666f-108">Si les fonctionnalités Recherche en texte intégral et Réplication n'existent pas sur l'instance mise à niveau, elles seront automatiquement installées, sans option pour les omettre.</span><span class="sxs-lookup"><span data-stu-id="1666f-108">If Full-text search and Replication features do not exist on the instance being upgraded, they will be installed automatically with no option to omit them.</span></span>  
  
-   <span data-ttu-id="1666f-109">Installation de Service Packs - Vous devez appliquer les Service Packs et correctifs logiciels [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aux clusters de basculement [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] séparément sur tous les nœuds.</span><span class="sxs-lookup"><span data-stu-id="1666f-109">Service pack installation - you must apply [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service packs and patches to [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all nodes.</span></span>  
  
-   <span data-ttu-id="1666f-110">Les scénarios suivants ne sont pas pris en charge :</span><span class="sxs-lookup"><span data-stu-id="1666f-110">The following scenarios are not supported:</span></span>  
  
    -   <span data-ttu-id="1666f-111">Vous ne pouvez pas effectuer une migration à partir d'une instance autonome de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vers un cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="1666f-111">You cannot migrate from a stand-alone instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to a failover cluster.</span></span>  
  
    -   <span data-ttu-id="1666f-112">Vous ne pouvez pas ajouter de fonctionnalités à un cluster de basculement,</span><span class="sxs-lookup"><span data-stu-id="1666f-112">Add features to a failover cluster.</span></span> <span data-ttu-id="1666f-113">par exemple ajouter le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] à un cluster de basculement existant [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]uniquement.</span><span class="sxs-lookup"><span data-stu-id="1666f-113">For example, you cannot add the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to an existing [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]-only failover cluster.</span></span>  
  
    -   <span data-ttu-id="1666f-114">Vous ne pouvez pas rétrograder un nœud de cluster de basculement à une instance autonome.</span><span class="sxs-lookup"><span data-stu-id="1666f-114">You cannot downgrade a failover cluster node to a stand-alone instance.</span></span>  
  
-   <span data-ttu-id="1666f-115">Pour plus d’informations, consultez [Instances de cluster de basculement AlwaysOn (SQL Server)](always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1666f-115">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="upgrading-a-ssnoversion-multi-subnet-failover-cluster"></a><span data-ttu-id="1666f-116">Mise à niveau d'un cluster de basculement de sous-réseaux multiples [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1666f-116">Upgrading a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Multi-Subnet Failover Cluster</span></span>  
 <span data-ttu-id="1666f-117">Vous ne pouvez pas mettre directement à niveau un cluster de basculement de sous-réseaux multiples [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vers un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cluster de basculement de sous-réseaux multiples.</span><span class="sxs-lookup"><span data-stu-id="1666f-117">You cannot directly upgrade a non-multi-subnet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] multi-subnet failover cluster.</span></span> <span data-ttu-id="1666f-118">Pour plus d’informations, consultez [Mettre à niveau une instance de cluster de basculement SQL Server &#40;programme d’installation&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span><span class="sxs-lookup"><span data-stu-id="1666f-118">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1666f-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1666f-119">See Also</span></span>  
 <span data-ttu-id="1666f-120">[Mises à niveau de la version et de l'édition prises en charge](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="1666f-120">[Supported Version and Edition Upgrades](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 <span data-ttu-id="1666f-121">[Mettre à niveau une instance de cluster de basculement SQL Server &#40;de l’installation&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="1666f-121">[Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="1666f-122">Installer SQL Server 2014 à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="1666f-122">Install SQL Server 2014 from the Command Prompt</span></span>](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md)  
  
  
