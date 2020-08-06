---
title: Vue d’ensemble du moniteur SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlservermonitor.main.f1
helpviewer_keywords:
- SQL Server Monitor [SQL Server]
ms.assetid: 048ae16d-31c3-489a-9f1e-1400a3bacd39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab90186ed493e616e672cfacf881fd61be166f88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601083"
---
# <a name="sql-server-monitor-overview"></a><span data-ttu-id="41cdb-102">Vue d'ensemble du moniteur SQL Server</span><span class="sxs-lookup"><span data-stu-id="41cdb-102">SQL Server Monitor Overview</span></span>
  <span data-ttu-id="41cdb-103">Le moniteur SQL Server n'effectue pas de fonctions de surveillance, mais il héberge des modules qui ont ce rôle.</span><span class="sxs-lookup"><span data-stu-id="41cdb-103">SQL Server Monitor does not perform monitoring functions, but it hosts modules that do.</span></span> <span data-ttu-id="41cdb-104">Le moniteur SQL Server inclut le moniteur de réplication et le moniteur de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="41cdb-104">The SQL Server Monitor modules include Replication Monitor and Database Mirroring Monitor.</span></span>  
  
 <span data-ttu-id="41cdb-105">Pour utiliser l'un de ces modules, sélectionnez le module souhaité dans le menu **Atteindre** .</span><span class="sxs-lookup"><span data-stu-id="41cdb-105">To use one of these modules, select that module on the **Go** menu.</span></span> <span data-ttu-id="41cdb-106">Le module sélectionné comprend le contenu des volets de navigation et d'informations, l'interaction utilisateur dans les volets d'informations ainsi que les requêtes portant sur le contenu et l'état.</span><span class="sxs-lookup"><span data-stu-id="41cdb-106">The currently selected module owns the content of the navigation and detail panes, user interaction in the detail panes, and the queries for content and status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41cdb-107">Pour plus d’informations sur ces moniteurs, consultez [Surveillance de la réplication](../../relational-databases/replication/monitoring-replication.md) et [Surveillance de la mise en miroir de bases de données &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="41cdb-107">For more information about these monitors, see [Monitoring Replication](../../relational-databases/replication/monitoring-replication.md) and [Monitoring Database Mirroring &#40;SQL Server&#41;](../database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="41cdb-108">Autorisations</span><span class="sxs-lookup"><span data-stu-id="41cdb-108">Permissions</span></span>  
  
-   <span data-ttu-id="41cdb-109">Moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="41cdb-109">Replication Monitor</span></span>  
  
     <span data-ttu-id="41cdb-110">Pour surveiller la réplication, vous devez être membre du rôle de serveur fixe **sysadmin** sur le serveur de distribution ou membre du rôle de base de données fixe **replmonitor** dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="41cdb-110">To monitor replication, you must be a member of the **sysadmin** fixed server role at the Distributor or a member of the **replmonitor** fixed database role in the distribution database.</span></span> <span data-ttu-id="41cdb-111">Un administrateur système peut ajouter n'importe quel utilisateur au rôle **replmonitor** , ce qui lui permet de visionner l'activité de réplication dans le Moniteur de réplication ; cependant, l'utilisateur ne peut pas administrer la réplication.</span><span class="sxs-lookup"><span data-stu-id="41cdb-111">A system administrator can add any user to the **replmonitor** role, which allows that user to view replication activity in Replication Monitor; however, the user cannot administer replication.</span></span>  
  
-   <span data-ttu-id="41cdb-112">Moniteur de mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="41cdb-112">Database Mirroring Monitor</span></span>  
  
     <span data-ttu-id="41cdb-113">Pour surveiller la mise en miroir de bases de données, vous devez être membre du rôle de serveur fixe **sysadmin** ou membre du rôle de base de données fixe **dbm_monitor** sur l’instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="41cdb-113">To monitor database mirroring, you must be a member of either the **sysadmin** fixed server role or the **dbm_monitor** fixed database role on the server instance.</span></span> <span data-ttu-id="41cdb-114">Si vous êtes membre de **sysadmin** ou **dbm_monitor** sur une seule des instances de serveur partenaire, le moniteur peut se connecter uniquement à ce partenaire ; il ne peut pas extraire d’informations de l’autre partenaire.</span><span class="sxs-lookup"><span data-stu-id="41cdb-114">If you are a member of **sysadmin** or **dbm_monitor** on only one of the partner server instances, the monitor can connect only to that partner; the monitor cannot retrieve information from the other partner.</span></span> <span data-ttu-id="41cdb-115">Pour plus d'informations, consultez [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="41cdb-115">For more information, see [Database Mirroring Monitor Overview](../database-mirroring/database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="menu-options"></a><span data-ttu-id="41cdb-116">Options de menu</span><span class="sxs-lookup"><span data-stu-id="41cdb-116">Menu Options</span></span>  
 <span data-ttu-id="41cdb-117">Le moniteur SQL Server comporte un menu de commandes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="41cdb-117">SQL Server Monitor has a menu that contains commands that pertain to SQL Server Monitor.</span></span> <span data-ttu-id="41cdb-118">Ce menu peut également comprendre des commandes du module sélectionné.</span><span class="sxs-lookup"><span data-stu-id="41cdb-118">This menu may also contain commands from the selected module.</span></span>  
  
 <span data-ttu-id="41cdb-119">Les options de menu suivantes appartiennent au moniteur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="41cdb-119">The following menu options pertain to SQL Server Monitor.</span></span>  
  
 <span data-ttu-id="41cdb-120">**File**</span><span class="sxs-lookup"><span data-stu-id="41cdb-120">**File**</span></span>  
 <span data-ttu-id="41cdb-121">Ce menu comprend la commande **Quitter** .</span><span class="sxs-lookup"><span data-stu-id="41cdb-121">This menu contains the **Exit** command.</span></span>  
  
 <span data-ttu-id="41cdb-122">**Action**</span><span class="sxs-lookup"><span data-stu-id="41cdb-122">**Action**</span></span>  
 <span data-ttu-id="41cdb-123">Comprend le menu contextuel du nœud sélectionné dans l'arborescence de navigation.</span><span class="sxs-lookup"><span data-stu-id="41cdb-123">Contains the context menu of the node selected in the navigation tree.</span></span>  
  
 <span data-ttu-id="41cdb-124">**Go**</span><span class="sxs-lookup"><span data-stu-id="41cdb-124">**Go**</span></span>  
 <span data-ttu-id="41cdb-125">Comprend une liste des composants de surveillance :</span><span class="sxs-lookup"><span data-stu-id="41cdb-125">Contains a list of monitoring components:</span></span>  
  
-   <span data-ttu-id="41cdb-126">Mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="41cdb-126">Database Mirroring</span></span>  
  
-   <span data-ttu-id="41cdb-127">Réplication</span><span class="sxs-lookup"><span data-stu-id="41cdb-127">Replication</span></span>  
  
 <span data-ttu-id="41cdb-128">**Pour utiliser SQL Server Management Studio pour contrôler la mise en miroir de base de données**</span><span class="sxs-lookup"><span data-stu-id="41cdb-128">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="41cdb-129">Démarrer le moniteur de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="41cdb-129">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="41cdb-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41cdb-130">See Also</span></span>  
 [<span data-ttu-id="41cdb-131">Surveillance de la mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="41cdb-131">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-sql-server.md)  
  
  
