---
title: Supprimer les références aux tables système non documentées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system tables [SQL Server]
- system tables [SQL Server]
ms.assetid: 010b1236-2219-4bf4-a6db-e3fc3abfa37a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 45c38038ee3d3214e4303c0ddbe0110be926c37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704707"
---
# <a name="remove-references-to-undocumented-system-tables"></a><span data-ttu-id="32985-102">Supprimer les références aux tables système non documentées</span><span class="sxs-lookup"><span data-stu-id="32985-102">Remove references to undocumented system tables</span></span>
  <span data-ttu-id="32985-103">De nombreuses tables système qui n'étaient pas documentées dans les versions antérieures ont été modifiées ou n'existent plus. Par conséquent, l'utilisation de ces tables peut provoquer des erreurs après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="32985-103">Many system tables that were undocumented in prior releases have changed or no longer exist; therefore, using these tables may cause errors after upgrading.</span></span> <span data-ttu-id="32985-104">Étant donné que le Conseiller de mise à niveau recherche des références aux noms des tables système, il va signaler ces références à toutes les tables utilisateur qui ont le même nom que des tables système.</span><span class="sxs-lookup"><span data-stu-id="32985-104">Because Upgrade Advisor looks for references to system table names, it will report references to any user tables that have the same names as system tables.</span></span>  
  
## <a name="component"></a><span data-ttu-id="32985-105">Composant</span><span class="sxs-lookup"><span data-stu-id="32985-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="32985-106">Description</span><span class="sxs-lookup"><span data-stu-id="32985-106">Description</span></span>  
 <span data-ttu-id="32985-107">Les tables système non documentées suivantes sont supprimées :</span><span class="sxs-lookup"><span data-stu-id="32985-107">The following undocumented system tables are removed:</span></span>  
  
-   <span data-ttu-id="32985-108">**spt_datatype_info**</span><span class="sxs-lookup"><span data-stu-id="32985-108">**spt_datatype_info**</span></span>  
  
-   <span data-ttu-id="32985-109">**spt_datatype_info_ext**</span><span class="sxs-lookup"><span data-stu-id="32985-109">**spt_datatype_info_ext**</span></span>  
  
-   <span data-ttu-id="32985-110">**spt_provider_types**</span><span class="sxs-lookup"><span data-stu-id="32985-110">**spt_provider_types**</span></span>  
  
-   <span data-ttu-id="32985-111">**spt_server_info**</span><span class="sxs-lookup"><span data-stu-id="32985-111">**spt_server_info**</span></span>  
  
-   <span data-ttu-id="32985-112">**spt_values**</span><span class="sxs-lookup"><span data-stu-id="32985-112">**spt_values**</span></span>  
  
-   <span data-ttu-id="32985-113">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="32985-113">**sysfulltextnotify**</span></span>  
  
-   <span data-ttu-id="32985-114">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="32985-114">**syslocks**</span></span>  
  
-   <span data-ttu-id="32985-115">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="32985-115">**sysproperties**</span></span>  
  
-   <span data-ttu-id="32985-116">**sysprotects_aux**</span><span class="sxs-lookup"><span data-stu-id="32985-116">**sysprotects_aux**</span></span>  
  
-   <span data-ttu-id="32985-117">**sysprotects_view**</span><span class="sxs-lookup"><span data-stu-id="32985-117">**sysprotects_view**</span></span>  
  
-   <span data-ttu-id="32985-118">**SYSREMOTE_CATALOGS**</span><span class="sxs-lookup"><span data-stu-id="32985-118">**SYSREMOTE_CATALOGS**</span></span>  
  
-   <span data-ttu-id="32985-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="32985-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="32985-120">**SYSREMOTE_COLUMNS**</span><span class="sxs-lookup"><span data-stu-id="32985-120">**SYSREMOTE_COLUMNS**</span></span>  
  
-   <span data-ttu-id="32985-121">**SYSREMOTE_FOREIGN_KEYS**</span><span class="sxs-lookup"><span data-stu-id="32985-121">**SYSREMOTE_FOREIGN_KEYS**</span></span>  
  
-   <span data-ttu-id="32985-122">**SYSREMOTE_INDEXES**</span><span class="sxs-lookup"><span data-stu-id="32985-122">**SYSREMOTE_INDEXES**</span></span>  
  
-   <span data-ttu-id="32985-123">**SYSREMOTE_PRIMARY_KEYS**</span><span class="sxs-lookup"><span data-stu-id="32985-123">**SYSREMOTE_PRIMARY_KEYS**</span></span>  
  
-   <span data-ttu-id="32985-124">**SYSREMOTE_PROVIDER_TYPES**</span><span class="sxs-lookup"><span data-stu-id="32985-124">**SYSREMOTE_PROVIDER_TYPES**</span></span>  
  
-   <span data-ttu-id="32985-125">**SYSREMOTE_SCHEMATA**</span><span class="sxs-lookup"><span data-stu-id="32985-125">**SYSREMOTE_SCHEMATA**</span></span>  
  
-   <span data-ttu-id="32985-126">**SYSREMOTE_STATISTICS**</span><span class="sxs-lookup"><span data-stu-id="32985-126">**SYSREMOTE_STATISTICS**</span></span>  
  
-   <span data-ttu-id="32985-127">**SYSREMOTE_TABLE_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="32985-127">**SYSREMOTE_TABLE_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="32985-128">**SYSREMOTE_TABLES**</span><span class="sxs-lookup"><span data-stu-id="32985-128">**SYSREMOTE_TABLES**</span></span>  
  
-   <span data-ttu-id="32985-129">**SYSREMOTE_VIEWS**</span><span class="sxs-lookup"><span data-stu-id="32985-129">**SYSREMOTE_VIEWS**</span></span>  
  
-   <span data-ttu-id="32985-130">**syssegments**</span><span class="sxs-lookup"><span data-stu-id="32985-130">**syssegments**</span></span>  
  
-   <span data-ttu-id="32985-131">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="32985-131">**sysxlogins**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="32985-132">Action corrective</span><span class="sxs-lookup"><span data-stu-id="32985-132">Corrective Action</span></span>  
 <span data-ttu-id="32985-133">Modifiez vos applications d'après le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="32985-133">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="32985-134">À la place de</span><span class="sxs-lookup"><span data-stu-id="32985-134">Instead of</span></span>|<span data-ttu-id="32985-135">Utilisation</span><span class="sxs-lookup"><span data-stu-id="32985-135">Use</span></span>|  
|----------------|---------|  
|<span data-ttu-id="32985-136">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="32985-136">**sysfulltextnotify**</span></span>|<span data-ttu-id="32985-137">propriété**TableFulltextPendingChanges** de la fonction OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="32985-137">**TableFulltextPendingChanges** property of the OBJECTPROPERTYEX function.</span></span>|  
|<span data-ttu-id="32985-138">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="32985-138">**syslocks**</span></span>|<span data-ttu-id="32985-139">vue de gestion dynamique**sys.dm_tran_locks** , sp_lock, ou vue de compatibilité **sys.syslockinfo** .</span><span class="sxs-lookup"><span data-stu-id="32985-139">**sys.dm_tran_locks** dynamic management view, or sp_lock, or the **sys.syslockinfo** compatibility view.</span></span>|  
|<span data-ttu-id="32985-140">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="32985-140">**sysproperties**</span></span>|<span data-ttu-id="32985-141">affichage catalogue**sys.extended_properties** ou fonction **fn_listextendedproperty**</span><span class="sxs-lookup"><span data-stu-id="32985-141">**sys.extended_properties** catalog view or the **fn_listextendedproperty** function</span></span>|  
|<span data-ttu-id="32985-142">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="32985-142">**sysxlogins**</span></span>|<span data-ttu-id="32985-143">affichage catalogue**sys.server_principals** ou vue de compatibilité **syslogins**</span><span class="sxs-lookup"><span data-stu-id="32985-143">**sys.server_principals** catalog view or **syslogins** compatibility view.</span></span>|  
|<span data-ttu-id="32985-144">toutes les tables **spt_**</span><span class="sxs-lookup"><span data-stu-id="32985-144">all **spt_** tables</span></span>|<span data-ttu-id="32985-145">Aucun remplacement disponible</span><span class="sxs-lookup"><span data-stu-id="32985-145">No replacement available</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32985-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32985-146">See Also</span></span>  
 <span data-ttu-id="32985-147">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="32985-147">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="32985-148">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="32985-148">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
