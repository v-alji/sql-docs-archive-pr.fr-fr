---
title: Supprimer une instance de cluster de basculement SQL Server (programme d’installation) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], removing failover clustered instance
- failover clustering [SQL Server], removing failover clustered instance
- uninstalling failover clustered instances
- removing failover clustered instances
ms.assetid: bf63353b-69cf-4c5c-98ea-7b151e36537f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a4d0ae492481b0677be2d2692fbda0fbc8eb604b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605041"
---
# <a name="remove-a-sql-server-failover-cluster-instance-setup"></a><span data-ttu-id="bbe14-102">Supprimer une instance de cluster de basculement SQL Server (programme d'installation)</span><span class="sxs-lookup"><span data-stu-id="bbe14-102">Remove a SQL Server Failover Cluster Instance (Setup)</span></span>
  <span data-ttu-id="bbe14-103">Suivez cette procédure pour désinstaller une instance de cluster de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bbe14-103">Use this procedure to uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover clustered instance.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bbe14-104">Pour mettre à jour ou supprimer un cluster de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , vous devez être un administrateur local autorisé à se connecter en tant que service sur tous les nœuds du cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="bbe14-104">To update or remove a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster, you must be a local administrator with permission to login as a service on all nodes of the failover cluster.</span></span>  
  
 <span data-ttu-id="bbe14-105">**Avant de commencer**</span><span class="sxs-lookup"><span data-stu-id="bbe14-105">**Before you begin**</span></span>  
  
 <span data-ttu-id="bbe14-106">Prenez en compte les points importants suivants avant de désinstaller un cluster de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="bbe14-106">Consider the following important points before you uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster:</span></span>  
  
-   <span data-ttu-id="bbe14-107">Si [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client est désinstallé par accident, les ressources [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ne pourront pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="bbe14-107">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is uninstalled by accident, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources will fail to start.</span></span> <span data-ttu-id="bbe14-108">Pour réinstaller [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, exécutez le programme d'installation [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour installer les éléments requis de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bbe14-108">To reinstall [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, run the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup program to install [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] prerequisites.</span></span>  
  
-   <span data-ttu-id="bbe14-109">Si vous avez désinstallé un cluster de basculement comportant plusieurs ressources de cluster IP SQL, vous devez supprimer les ressources IP SQL supplémentaires à l'aide de l'administrateur de clusters.</span><span class="sxs-lookup"><span data-stu-id="bbe14-109">If you uninstall a failover cluster that has more than one SQL IP cluster resource, you must remove the additional SQL IP resources using cluster administrator.</span></span>  
  
 <span data-ttu-id="bbe14-110">Pour plus d’informations sur la syntaxe de l’invite de commandes, consultez [installer SQL Server 2014 à partir de l’invite de commandes](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="bbe14-110">For information about command prompt syntax, see [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
### <a name="to-uninstall-a-ssnoversion-failover-cluster"></a><span data-ttu-id="bbe14-111">Pour désinstaller un cluster de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbe14-111">To uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster</span></span>  
  
1.  <span data-ttu-id="bbe14-112">Pour désinstaller un cluster de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , utilisez la fonctionnalité Supprimer un nœud fournie par le programme d'installation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour supprimer chaque nœud individuellement.</span><span class="sxs-lookup"><span data-stu-id="bbe14-112">To uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster, use the Remove Node functionality provided by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup to remove each node individually.</span></span> <span data-ttu-id="bbe14-113">Pour plus d’informations, consultez [Ajouter ou supprimer des nœuds dans un cluster de basculement SQL Server &#40;programme d’installation&#41;](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="bbe14-113">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe14-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bbe14-114">See Also</span></span>  
 [<span data-ttu-id="bbe14-115">Afficher et lire les fichiers journaux d'installation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="bbe14-115">View and Read SQL Server Setup Log Files</span></span>](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)  
  
  
