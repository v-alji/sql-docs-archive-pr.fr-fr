---
title: Activer et désactiver le suivi des modifications (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], disabling
- data changes [SQL Server]
- change tracking [SQL Server], enabling
- tracking data changes [SQL Server]
- change tracking [SQL Server], configuring
- data [SQL Server], changing
ms.assetid: 1c92ec7e-ae53-4498-8bfd-c66a42a24d54
author: rothja
ms.author: jroth
ms.openlocfilehash: 402c63ae03df14e3a725fbc440575f5233d502f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604403"
---
# <a name="enable-and-disable-change-tracking-sql-server"></a><span data-ttu-id="fc022-102">Activer et désactiver le suivi des modifications (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc022-102">Enable and Disable Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="fc022-103">Cette rubrique décrit l'activation et la désactivation du suivi des modifications pour une base de données et une table.</span><span class="sxs-lookup"><span data-stu-id="fc022-103">This topic describes how to enable and disable change tracking for a database and a table.</span></span>  
  
## <a name="enable-change-tracking-for-a-database"></a><span data-ttu-id="fc022-104">Activer le suivi des modifications pour une base de données</span><span class="sxs-lookup"><span data-stu-id="fc022-104">Enable Change Tracking for a Database</span></span>  
 <span data-ttu-id="fc022-105">Avant de pouvoir utiliser le suivi des modifications, vous devez l'activer au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="fc022-105">Before you can use change tracking, you must enable change tracking at the database level.</span></span> <span data-ttu-id="fc022-106">L’exemple suivant indique comment activer le suivi des modifications en utilisant [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="fc022-106">The following example shows how to enable change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = ON  
(CHANGE_RETENTION = 2 DAYS, AUTO_CLEANUP = ON)  
```  
  
 <span data-ttu-id="fc022-107">Vous pouvez également activer le suivi des modifications dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] en utilisant la boîte de dialogue [Propriétés de la base de données &#40;page Suivi des modifications&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="fc022-107">You can also enable change tracking in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="fc022-108">Vous pouvez spécifier les options CHANGE_RETENTION et AUTO_CLEANUP lorsque vous activez le suivi des modifications et vous pouvez modifier leurs valeurs à tout moment une fois que le suivi des modifications a été activé.</span><span class="sxs-lookup"><span data-stu-id="fc022-108">You can specify the CHANGE_RETENTION and AUTO_CLEANUP options when you enable change tracking, and you can change the values at any time after change tracking is enabled.</span></span>  
  
 <span data-ttu-id="fc022-109">La valeur de la rétention des modifications indique la période pendant laquelle les informations de suivi des modifications sont conservées.</span><span class="sxs-lookup"><span data-stu-id="fc022-109">The change retention value specifies the time period for which change tracking information is kept.</span></span> <span data-ttu-id="fc022-110">À l'issue de cette période, les informations de suivi des modifications sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="fc022-110">Change tracking information that is older than this time period is removed periodically.</span></span> <span data-ttu-id="fc022-111">Lorsque vous affectez cette valeur, vous devez considérer la fréquence à laquelle les applications sont synchronisées avec les tables incluses dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="fc022-111">When you are setting this value, you should consider how often applications will synchronize with the tables in the database.</span></span> <span data-ttu-id="fc022-112">En effet, la période de rétention spécifiée doit être supérieure ou égale à la période maximale entre deux synchronisations.</span><span class="sxs-lookup"><span data-stu-id="fc022-112">The specified retention period must be at least as long as the maximum time period between synchronizations.</span></span> <span data-ttu-id="fc022-113">Si une application obtient des modifications sur des intervalles plus longs, les résultats retournés risquent d'être incorrects, parce qu'une partie des informations de modification aura probablement été supprimée.</span><span class="sxs-lookup"><span data-stu-id="fc022-113">If an application obtains changes at longer intervals, the results that are returned might be incorrect because some of the change information has probably been removed.</span></span> <span data-ttu-id="fc022-114">Pour éviter d'obtenir des résultats incorrects, une application peut utiliser la fonction système CHANGE_TRACKING_MIN_VALID_VERSION pour déterminer si l'intervalle entre synchronisations a été trop long.</span><span class="sxs-lookup"><span data-stu-id="fc022-114">To avoid obtaining incorrect results, an application can use the CHANGE_TRACKING_MIN_VALID_VERSION system function to determine whether the interval between synchronizations has been too long.</span></span>  
  
 <span data-ttu-id="fc022-115">Vous pouvez utiliser l'option AUTO_CLEANUP pour activer ou désactiver la tâche de nettoyage qui permet de supprimer les informations de suivi des modifications anciennes.</span><span class="sxs-lookup"><span data-stu-id="fc022-115">You can use the AUTO_CLEANUP option to enable or disable the cleanup task that removes old change tracking information.</span></span> <span data-ttu-id="fc022-116">Ce paramètre peut s'avérer utile lorsqu'il existe un problème temporaire qui empêche les applications de se synchroniser et que le processus de suppression des informations de suivi des modifications antérieures à la période de rétention doit être suspendu jusqu'à ce que le problème soit résolu.</span><span class="sxs-lookup"><span data-stu-id="fc022-116">This can be useful when there is a temporary problem that prevents applications from synchronizing and the process for removing change tracking information older than the retention period must be paused until the problem is resolved.</span></span>  
  
 <span data-ttu-id="fc022-117">Pour toute base de données qui utilise le suivi des modifications, ayez conscience de ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="fc022-117">For any database that uses change tracking, be aware of the following:</span></span>  
  
-   <span data-ttu-id="fc022-118">Pour utiliser le suivi des modifications, le niveau de compatibilité de la base de données doit être défini à 90 ou plus.</span><span class="sxs-lookup"><span data-stu-id="fc022-118">To use change tracking, the database compatibility level must be set to 90 or greater.</span></span> <span data-ttu-id="fc022-119">Si une base de données présente un niveau de compatibilité inférieur à 90, vous pouvez configurer le suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="fc022-119">If a database has a compatibility level of less than 90, you can configure change tracking.</span></span> <span data-ttu-id="fc022-120">Dans ce cas, toutefois, la fonction CHANGETABLE, utilisée pour obtenir des informations de suivi des modifications, retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="fc022-120">However, the CHANGETABLE function, which is used to obtain change tracking information, will return an error.</span></span>  
  
-   <span data-ttu-id="fc022-121">L'utilisation de l'isolement d'instantané constitue le moyen le plus simple de garantir la cohérence de toutes les informations de suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="fc022-121">Using snapshot isolation is the easiest way for you to help ensure that all change tracking information is consistent.</span></span> <span data-ttu-id="fc022-122">C'est pourquoi nous recommandons fortement d'affecter la valeur ON à cet isolement d'instantané pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="fc022-122">For this reason, we strongly recommend that snapshot isolation be set to ON for the database.</span></span> <span data-ttu-id="fc022-123">Pour plus d’informations, consultez [Utiliser le suivi des modifications &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fc022-123">For more information, see [Work with Change Tracking &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span></span>  
  
## <a name="enable-change-tracking-for-a-table"></a><span data-ttu-id="fc022-124">Activer le suivi des modifications pour une table</span><span class="sxs-lookup"><span data-stu-id="fc022-124">Enable Change Tracking for a Table</span></span>  
 <span data-ttu-id="fc022-125">Le suivi des modifications doit être activé pour chaque table que vous souhaitez suivre.</span><span class="sxs-lookup"><span data-stu-id="fc022-125">Change tracking must be enabled for each table that you want tracked.</span></span> <span data-ttu-id="fc022-126">Lorsque le suivi des modifications est activé, les informations correspondantes sont conservées pour toutes les lignes de la table qui sont affectées par une opération DML.</span><span class="sxs-lookup"><span data-stu-id="fc022-126">When change tracking is enabled, change tracking information is maintained for all rows in the table that are affected by a DML operation.</span></span>  
  
 <span data-ttu-id="fc022-127">L’exemple suivant indique comment activer le suivi des modifications pour une table en utilisant [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fc022-127">The following example shows how to enable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
ENABLE CHANGE_TRACKING  
WITH (TRACK_COLUMNS_UPDATED = ON)  
```  
  
 <span data-ttu-id="fc022-128">Vous pouvez également activer le suivi des modifications pour une table dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] en utilisant la boîte de dialogue [Propriétés de la base de données &#40;page Suivi des modifications&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="fc022-128">You can also enable change tracking for a table in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="fc022-129">Quand l’option TRACK_COLUMNS_UPDATED a la valeur ON, le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] stocke des informations supplémentaires sur les colonnes qui ont été mises à jour dans la table de suivi des modifications interne.</span><span class="sxs-lookup"><span data-stu-id="fc022-129">When the TRACK_COLUMNS_UPDATED option is set to ON, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] stores extra information about which columns were updated to the internal change tracking table.</span></span> <span data-ttu-id="fc022-130">Le suivi des colonnes peut permettre à une application de synchroniser uniquement les colonnes mises à jour.</span><span class="sxs-lookup"><span data-stu-id="fc022-130">Column tracking can enable an application to synchronize only those columns that were updated.</span></span> <span data-ttu-id="fc022-131">Il permet ainsi d'améliorer l'efficacité et les performances.</span><span class="sxs-lookup"><span data-stu-id="fc022-131">This can improve efficiency and performance.</span></span> <span data-ttu-id="fc022-132">Toutefois, étant donné que la conservation des informations de suivi des colonnes augmente la charge de stockage, cette option a la valeur OFF par défaut.</span><span class="sxs-lookup"><span data-stu-id="fc022-132">However, because maintaining column tracking information adds some extra storage overhead, this option is set to OFF by default.</span></span>  
  
## <a name="disable-change-tracking-for-a-database-or-table"></a><span data-ttu-id="fc022-133">Désactiver le suivi des modifications pour une base de données ou une table</span><span class="sxs-lookup"><span data-stu-id="fc022-133">Disable Change Tracking for a Database or Table</span></span>  
 <span data-ttu-id="fc022-134">Vous devez d'abord désactiver le suivi des modifications pour toutes les tables qui en font l'objet avant d'affecter la valeur OFF au suivi des modifications pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="fc022-134">Change tracking must first be disabled for all change-tracked tables before change tracking can be set to OFF for the database.</span></span> <span data-ttu-id="fc022-135">Pour déterminer les tables dont le suivi des modifications est activé pour une base de données, utilisez l’affichage catalogue [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) .</span><span class="sxs-lookup"><span data-stu-id="fc022-135">To determine the tables that have change tracking enabled for a database, use the [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) catalog view.</span></span>  
  
 <span data-ttu-id="fc022-136">Quand aucune table n'effectue un suivi des modifications dans une base de données, vous pouvez désactiver le suivi des modifications pour cette base de données.</span><span class="sxs-lookup"><span data-stu-id="fc022-136">When no tables in a database track changes, you can disable change tracking for the database.</span></span> <span data-ttu-id="fc022-137">L’exemple suivant indique comment désactiver le suivi des modifications pour une base de données en utilisant [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="fc022-137">The following example shows how to disable change tracking for a database by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = OFF  
```  
  
 <span data-ttu-id="fc022-138">L’exemple suivant indique comment désactiver le suivi des modifications pour une table en utilisant [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fc022-138">The following example shows how to disable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
DISABLE CHANGE_TRACKING;  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc022-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fc022-139">See Also</span></span>  
 <span data-ttu-id="fc022-140">[Propriétés de la base de données &#40;page Suivi des modifications&#41;](../databases/database-properties-changetracking-page.md) </span><span class="sxs-lookup"><span data-stu-id="fc022-140">[Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) </span></span>  
 <span data-ttu-id="fc022-141">[Options ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="fc022-141">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="fc022-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span><span class="sxs-lookup"><span data-stu-id="fc022-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span></span>  
 <span data-ttu-id="fc022-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span><span class="sxs-lookup"><span data-stu-id="fc022-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span></span>  
 <span data-ttu-id="fc022-144">[Suivi des modifications de données &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fc022-144">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="fc022-145">[À propos du suivi des modifications &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fc022-145">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="fc022-146">[Utiliser les données modifiées &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fc022-146">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="fc022-147">Gérer le suivi des modifications &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fc022-147">Manage Change Tracking &#40;SQL Server&#41;</span></span>](manage-change-tracking-sql-server.md)  
  
  
