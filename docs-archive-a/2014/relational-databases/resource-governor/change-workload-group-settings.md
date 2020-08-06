---
title: Modifier les paramètres de groupe de charge de travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], alter
- Resource Governor, workload group alter
ms.assetid: 73b6109c-2ad0-4915-b11b-d40d5a0fdc25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 579aad71d32a629d75f1eecd76e7dacfe32d94f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599877"
---
# <a name="change-workload-group-settings"></a><span data-ttu-id="975fa-102">Modifier les paramètres de groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="975fa-102">Change Workload Group Settings</span></span>
  <span data-ttu-id="975fa-103">Vous pouvez modifier les paramètres d'un groupe de charge de travail à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="975fa-103">You can change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="975fa-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="975fa-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="975fa-105">**Pour modifier les paramètres d’un groupe de charge de travail avec :**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="975fa-105">**To change the settings for a workload group, using:**  [SQL Server Management Studio](#ChgWGProp), [Transact-SQL](#ChgWGTSQL)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="975fa-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="975fa-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="975fa-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="975fa-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="975fa-108">Vous pouvez modifier les paramètres du groupe de charge de travail par défaut et des groupes de charge de travail définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="975fa-108">You can change the settings of the default workload group and user-defined workload groups.</span></span>  
  
 <span data-ttu-id="975fa-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="975fa-109">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="975fa-110">La mémoire consommée par la création d'index sur une table partitionnée non-alignée est proportionnelle au nombre de partitions impliquées.</span><span class="sxs-lookup"><span data-stu-id="975fa-110">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="975fa-111">Si la mémoire totale requise dépasse la limite par requête (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposée par le paramètre du groupe de charge de travail, cette création d'index peut ne pas aboutir.</span><span class="sxs-lookup"><span data-stu-id="975fa-111">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="975fa-112">Étant donné que le groupe de charge de travail par défaut permet à une requête de dépasser la limite par requête avec la mémoire minimale requise pour démarrer en vue de la compatibilité SQL Server 2005, l'utilisateur peut être en mesure d'exécuter la même création d'index dans le groupe de charge de travail par défaut, si le pool de ressources par défaut possède assez de mémoire totale configurée pour exécuter une telle requête.</span><span class="sxs-lookup"><span data-stu-id="975fa-112">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="975fa-113">La création d'index est autorisée à utiliser un espace de travail de mémoire supérieur à celui qui lui a été initialement alloué, pour des raisons de performances.</span><span class="sxs-lookup"><span data-stu-id="975fa-113">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="975fa-114">Cette gestion spéciale est prise en charge par Resource Governor. Toutefois, l'allocation initiale et toute allocation de mémoire supplémentaire sont limitées par les paramètres du pool de ressources et du groupe de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="975fa-114">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="975fa-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="975fa-115">Permissions</span></span>  
 <span data-ttu-id="975fa-116">La modification des paramètres de groupe de charge de travail nécessite l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="975fa-116">Changing workload group settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-workload-group-settings-using-sql-server-management-studio"></a><a name="ChgWGProp"></a> <span data-ttu-id="975fa-117">Modifier les paramètres de groupe de charge de travail à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="975fa-117">Change Workload Group Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="975fa-118">**Pour modifier les paramètres de groupe de charge de travail à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="975fa-118">**To change workload group settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="975fa-119">Dans l'Explorateur d'objets, développez de manière récursive le nœud **Gestion** vers le bas et en incluant le dossier **Groupes de charge de travail** qui contient le groupe de charge de travail à modifier.</span><span class="sxs-lookup"><span data-stu-id="975fa-119">In Object Explorer, recursively expand the **Management** node down to and including the **Workload Groups** folder that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="975fa-120">Cliquez avec le bouton droit sur le groupe de charge de travail à modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="975fa-120">Right-click the workload group to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="975fa-121">Dans la page **Propriétés de Resource Governor** , sélectionnez la ligne pour le groupe de charge de travail dans la grille **Groupes de charges de travail pour le pool de ressources** si elle n'est pas sélectionnée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="975fa-121">In the **Resource Governor Properties** page, select the row for the workload group in the **Workload groups for resource pool** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="975fa-122">Cliquez ou double-cliquez sur les cellules de la ligne à modifier, puis entrez les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="975fa-122">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="975fa-123">Cliquez sur **OK**pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="975fa-123">To save the changes, click **OK**</span></span>  
  
##  <a name="change-workload-group-settings-using-transact-sql"></a><a name="ChgWGTSQL"></a> <span data-ttu-id="975fa-124">Modifier les paramètres de groupe de charge de travail à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="975fa-124">Change Workload Group Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="975fa-125">**Pour modifier les paramètres de groupe de charge de travail à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="975fa-125">**To change workload group settings by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="975fa-126">Exécutez l'instruction ALTER WORKLOAD GROUP en spécifiant les valeurs de propriété à modifier.</span><span class="sxs-lookup"><span data-stu-id="975fa-126">Run the ALTER WORKLOAD GROUP statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="975fa-127">Exécutez l'instruction ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="975fa-127">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="975fa-128">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="975fa-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="975fa-129">L'exemple suivant modifie le paramètre de pourcentage maximal d'allocation de mémoire pour le groupe de charge de travail nommé `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="975fa-129">The following example changes the max memory grant percent setting for the workload group named `groupAdhoc`.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
WITH (REQUEST_MAX_MEMORY_GRANT_PERCENT = 30);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="975fa-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="975fa-130">See Also</span></span>  
 <span data-ttu-id="975fa-131">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="975fa-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="975fa-132">[Créer un groupe de charge de travail](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="975fa-132">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="975fa-133">[Créer un pool de ressources](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="975fa-133">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="975fa-134">[Modifier les paramètres de pool de ressources](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="975fa-134">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="975fa-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="975fa-135">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="975fa-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="975fa-136">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="975fa-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="975fa-137">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
