---
title: Établir un référentiel de performances | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database performance [SQL Server], baselines
- monitoring performance [SQL Server], baselines
- tuning databases [SQL Server], baselines
- server performance [SQL Server], baselines
- performance [SQL Server], baselines
- baseline performance [SQL Server]
- measurements for baseline statistics [SQL Server]
- monitoring server performance [SQL Server], establishing baseline
- database monitoring [SQL Server], baselines
ms.assetid: dc5aa8d6-2507-448f-ad86-4196443915fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0cb85ae8ad370b816c6240b58aabd247c7593c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696740"
---
# <a name="establish-a-performance-baseline"></a><span data-ttu-id="5f74e-102">Établir un niveau de référence des performances</span><span class="sxs-lookup"><span data-stu-id="5f74e-102">Establish a Performance Baseline</span></span>
  <span data-ttu-id="5f74e-103">Pour déterminer si votre système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assure des performances optimales, mesurez les performances à intervalles réguliers, même en l'absence de problèmes, pour établir un niveau de référence des performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="5f74e-103">To determine whether your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system is performing optimally, take performance measurements at regular intervals over time, even when no problems occur, to establish a server performance baseline.</span></span> <span data-ttu-id="5f74e-104">Comparez chaque nouvel ensemble de mesures à ceux réalisés précédemment.</span><span class="sxs-lookup"><span data-stu-id="5f74e-104">Compare each new set of measurements with those taken earlier.</span></span>  
  
 <span data-ttu-id="5f74e-105">Les éléments suivants ont une influence sur les performances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5f74e-105">The following areas affect the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="5f74e-106">ressources système (matériel) ;</span><span class="sxs-lookup"><span data-stu-id="5f74e-106">System resources (hardware)</span></span>  
  
-   <span data-ttu-id="5f74e-107">Architecture réseau</span><span class="sxs-lookup"><span data-stu-id="5f74e-107">Network architecture</span></span>  
  
-   <span data-ttu-id="5f74e-108">système d'exploitation ;</span><span class="sxs-lookup"><span data-stu-id="5f74e-108">The operating system</span></span>  
  
-   <span data-ttu-id="5f74e-109">applications de base de données ;</span><span class="sxs-lookup"><span data-stu-id="5f74e-109">Database applications</span></span>  
  
-   <span data-ttu-id="5f74e-110">Applications clientes</span><span class="sxs-lookup"><span data-stu-id="5f74e-110">Client applications</span></span>  
  
 <span data-ttu-id="5f74e-111">Au minimum, vous devez effectuer des mesures de niveau de référence pour déterminer :</span><span class="sxs-lookup"><span data-stu-id="5f74e-111">At a minimum, use baseline measurements to determine:</span></span>  
  
-   <span data-ttu-id="5f74e-112">les heures de pointe et les heures creuses d'exploitation ;</span><span class="sxs-lookup"><span data-stu-id="5f74e-112">Peak and off-peak hours of operation.</span></span>  
  
-   <span data-ttu-id="5f74e-113">les temps de réponse des requêtes de production et des commandes de traitement par lots ;</span><span class="sxs-lookup"><span data-stu-id="5f74e-113">Production-query or batch-command response times.</span></span>  
  
-   <span data-ttu-id="5f74e-114">les temps de sauvegarde et de restauration de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5f74e-114">Database backup and restore completion times.</span></span>  
  
 <span data-ttu-id="5f74e-115">Après avoir établi le niveau de référence des performances, comparez vos statistiques aux performances actuelles du serveur.</span><span class="sxs-lookup"><span data-stu-id="5f74e-115">After you establish a server performance baseline, compare the baseline statistics to current server performance.</span></span> <span data-ttu-id="5f74e-116">Toute valeur très supérieure ou très inférieure à votre niveau de référence doit donner lieu à un examen approfondi.</span><span class="sxs-lookup"><span data-stu-id="5f74e-116">Numbers far above or far below your baseline are candidates for further investigation.</span></span> <span data-ttu-id="5f74e-117">Elle peut indiquer la nécessité d'optimiser ou de reconfigurer certains points.</span><span class="sxs-lookup"><span data-stu-id="5f74e-117">They may indicate areas in need of tuning or reconfiguration.</span></span> <span data-ttu-id="5f74e-118">Par exemple, si le temps nécessaire à l'exécution d'un ensemble de requêtes augmente, examinez les requêtes en question pour déterminer si vous pouvez les réécrire ou si vous devez ajouter des colonnes de statistiques ou de nouveaux index.</span><span class="sxs-lookup"><span data-stu-id="5f74e-118">For example, if the amount of time to execute a set of queries increases, examine the queries to determine if they can be rewritten, or if column statistics or new indexes must be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f74e-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f74e-119">See Also</span></span>  
 [<span data-ttu-id="5f74e-120">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5f74e-120">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
