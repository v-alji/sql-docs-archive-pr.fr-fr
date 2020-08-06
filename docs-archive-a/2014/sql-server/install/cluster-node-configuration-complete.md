---
title: Configuration du nœud de cluster (complète) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 64174d54-edee-49b8-9b43-039574bf2ca1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cc1f8ce4574580746e20c478b23e40485c3e6ecc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604951"
---
# <a name="cluster-node-configuration-complete"></a><span data-ttu-id="4fb97-102">Configuration du nœud de cluster (Complète)</span><span class="sxs-lookup"><span data-stu-id="4fb97-102">Cluster Node Configuration (Complete)</span></span>
  <span data-ttu-id="4fb97-103">Utilisez la page Configuration du nœud de clusters (Complète) pour spécifier une instance existante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui a été préparée pour le clustering. Pour installer ou mettre à niveau un cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez exécuter le programme d'installation sur chaque nœud du cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="4fb97-103">Use the Cluster Node Configuration (Complete) page to specify an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that has been prepared for clustering.To install or upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you must run the Setup program on each node of the failover cluster.</span></span> <span data-ttu-id="4fb97-104">Pour ajouter un nœud à un cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] existant, vous devez exécuter le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur le nœud destiné à être ajouté à l'instance de cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fb97-104">To add a node to an existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you must run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup on the node that is to be added to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4fb97-105">Options</span><span class="sxs-lookup"><span data-stu-id="4fb97-105">Options</span></span>  
 <span data-ttu-id="4fb97-106">Dans les zones de liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="4fb97-106">From the drop-down boxes:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="4fb97-107">nom de l’instance : sélectionnez le nom de l’instance du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="4fb97-107">instance name - Select the instance name for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
-   <span data-ttu-id="4fb97-108">Nom de ce nœud : ce champ est pré-rempli avec le nom de l’ordinateur sur lequel le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] programme d’installation s’exécute.</span><span class="sxs-lookup"><span data-stu-id="4fb97-108">Name of this node - This field is pre-populated with the computer name where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="4fb97-109">Nom réseau du cluster de basculement : ce champ n’est pas pré-rempli.</span><span class="sxs-lookup"><span data-stu-id="4fb97-109">Failover Cluster Network Name - This field is not pre-populated.</span></span> <span data-ttu-id="4fb97-110">Indiquez le nom réseau de la nouvelle instance de cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fb97-110">Specify the network name for the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span> <span data-ttu-id="4fb97-111">Il s'agit du nom qui identifie l'instance de cluster de basculement sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="4fb97-111">This is the name that identifies the failover cluster instance on the network.</span></span>  
  
  
