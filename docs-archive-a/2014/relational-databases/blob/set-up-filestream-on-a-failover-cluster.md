---
title: Configurer FILESTREAM sur un cluster de basculement | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], setting up on a failover cluster
ms.assetid: 6721f780-20b7-4109-8ddb-ac327310699e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29541bbcfd323a85a3fa751f60904fd1a26e1199
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695723"
---
# <a name="set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="7c3bd-102">Configurer FILESTREAM sur un cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="7c3bd-102">Set Up FILESTREAM on a Failover Cluster</span></span>
  <span data-ttu-id="7c3bd-103">Cette rubrique décrit comment activer FILESTREAM sur un cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-103">This topic describes how to enable FILESTREAM on a failover cluster.</span></span> <span data-ttu-id="7c3bd-104">Avant d’essayer d’appliquer cette procédure, vous devez comprendre la notion de [clustering de basculement](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) et activer FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-104">Before you try this procedure, you should understand [failover clustering](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) and have FILESTREAM enabled.</span></span> <span data-ttu-id="7c3bd-105">Pour plus d’informations sur l’activation de FILESTREAM, consultez [Activer et configurer FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="7c3bd-105">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
### <a name="to-set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="7c3bd-106">Pour configurer FILESTREAM sur un cluster de basculement</span><span class="sxs-lookup"><span data-stu-id="7c3bd-106">To set up FILESTREAM on a failover cluster</span></span>  
  
1.  <span data-ttu-id="7c3bd-107">Installez le nœud principal pour le cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-107">Set up the primary node for the failover cluster.</span></span>  
  
     <span data-ttu-id="7c3bd-108">Une fois l’installation terminée, activez FILESTREAM sur le nœud principal à l’aide du **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-108">After the setup finishes, enable FILESTREAM on the primary node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="7c3bd-109">Cela active les paramètres qui requièrent les privilèges d'administrateur Windows.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-109">This enables the settings that require Windows Admin privileges.</span></span> <span data-ttu-id="7c3bd-110">Si l’accès distant est requis, sélectionnez **Autoriser les clients distants à avoir un accès en continu aux données FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-110">If remote access is required, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span> <span data-ttu-id="7c3bd-111">Cela crée une ressource de cluster de fichiers partagés.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-111">This will create a file-share cluster resource.</span></span>  
  
2.  <span data-ttu-id="7c3bd-112">Installez un nœud passif.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-112">Set up a passive node.</span></span>  
  
     <span data-ttu-id="7c3bd-113">Une fois l’installation terminée, activez FILESTREAM sur le nœud passif à l’aide du **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-113">After the setup finishes, enable FILESTREAM on the passive node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="7c3bd-114">Le nom que vous spécifiez pour **Nom de partage Windows** doit être identique sur tous les nœuds du cluster.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-114">The name that you specify for **Windows Share Name** must be the same across all nodes in the cluster.</span></span>  
  
3.  <span data-ttu-id="7c3bd-115">Pour ajouter davantage de nœuds passifs, répétez l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-115">To add more passive nodes, repeat step 2.</span></span>  
  
4.  <span data-ttu-id="7c3bd-116">Après avoir ajouté tous les nœuds, terminez le processus en exécutant la procédure stockée sp_configure sur chaque instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c3bd-116">After all the nodes are added, complete the process by executing the sp_configure stored procedure on each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="7c3bd-117">Pour ajouter et activer des nœuds supplémentaires au cluster à tout moment, vous pouvez répéter les étapes 2, 3 et 4.</span><span class="sxs-lookup"><span data-stu-id="7c3bd-117">To add and enable additional nodes to the cluster at any time, you can repeat steps 2, 3, and 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c3bd-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c3bd-118">See Also</span></span>  
 <span data-ttu-id="7c3bd-119">[Options de configuration de serveur &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7c3bd-119">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="7c3bd-120">[Créer un cluster de basculement SQL Server &#40;programme d’installation&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span><span class="sxs-lookup"><span data-stu-id="7c3bd-120">[Create a New SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span></span>  
 <span data-ttu-id="7c3bd-121">[Supprimer une instance de cluster de basculement SQL Server &#40;programme d’installation&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="7c3bd-121">[Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="7c3bd-122">Ajouter ou supprimer des nœuds dans un cluster de basculement SQL Server &#40;programme d’installation&#41;</span><span class="sxs-lookup"><span data-stu-id="7c3bd-122">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
  
