---
title: Créer un groupe de charge de travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group create
- workload groups [SQL Server], create
ms.assetid: 072868ec-ceff-4db6-941b-281af731a067
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 144bcef57b3d6e191b03b1539e9e7382a9085c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603922"
---
# <a name="create-a-workload-group"></a><span data-ttu-id="eea8d-102">Créer un groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="eea8d-102">Create a Workload Group</span></span>
  <span data-ttu-id="eea8d-103">Vous pouvez créer un groupe de charge de travail à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eea8d-103">You can create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="eea8d-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="eea8d-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="eea8d-105">**Pour créer un groupe de charge de travail avec :**  [SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="eea8d-105">**To create a workload group, using:**  [SQL Server Management Studio](#CreWGProp), [Transact-SQL](#CreWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eea8d-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="eea8d-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="eea8d-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="eea8d-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="eea8d-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span><span class="sxs-lookup"><span data-stu-id="eea8d-108">**REQUEST_MAX_MEMORY_GRANT_PERCENT**</span></span>  
  
 <span data-ttu-id="eea8d-109">La mémoire consommée par la création d'index sur une table partitionnée non-alignée est proportionnelle au nombre de partitions impliquées.</span><span class="sxs-lookup"><span data-stu-id="eea8d-109">The memory consumed by index creation on a non-aligned partitioned table is proportional to the number of partitions involved.</span></span> <span data-ttu-id="eea8d-110">Si la mémoire totale requise dépasse la limite par requête (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposée par le paramètre du groupe de charge de travail, cette création d'index peut ne pas aboutir.</span><span class="sxs-lookup"><span data-stu-id="eea8d-110">If the total required memory exceeds the per-query limit, (REQUEST_MAX_MEMORY_GRANT_PERCENT) imposed by the workload group setting, this index creation may fail.</span></span> <span data-ttu-id="eea8d-111">Étant donné que le groupe de charge de travail par défaut permet à une requête de dépasser la limite par requête avec la mémoire minimale requise pour démarrer en vue de la compatibilité SQL Server 2005, l'utilisateur peut être en mesure d'exécuter la même création d'index dans le groupe de charge de travail par défaut, si le pool de ressources par défaut possède assez de mémoire totale configurée pour exécuter une telle requête.</span><span class="sxs-lookup"><span data-stu-id="eea8d-111">Because the default workload group allows a query to exceed the per-query limit with the minimum required memory to start for SQL Server 2005 compatibility, the user may be able to run the same index creation in the default workload group, if the default resource pool has enough total memory configured to run such a query.</span></span>  
  
 <span data-ttu-id="eea8d-112">La création d'index est autorisée à utiliser un espace de travail de mémoire supérieur à celui qui lui a été initialement alloué, pour des raisons de performances.</span><span class="sxs-lookup"><span data-stu-id="eea8d-112">Index creation is allowed to use more memory workspace than initially granted for performance.</span></span> <span data-ttu-id="eea8d-113">Cette gestion spéciale est prise en charge par Resource Governor. Toutefois, l'allocation initiale et toute allocation de mémoire supplémentaire sont limitées par les paramètres du pool de ressources et du groupe de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="eea8d-113">This special handling is supported by Resource Governor, however, the initial grant and any additional memory grant are limited by the workload group and resource pool settings.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eea8d-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="eea8d-114">Permissions</span></span>  
 <span data-ttu-id="eea8d-115">La création d'un groupe de charge de travail nécessite l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="eea8d-115">Creating a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-workload-group-using-sql-server-management-studio"></a><a name="CreWGProp"></a> <span data-ttu-id="eea8d-116">Créer un groupe de charge de travail avec SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eea8d-116">Create a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="eea8d-117">**Pour créer un groupe de charge de travail à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="eea8d-117">**To create a workload group by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="eea8d-118">Dans l'Explorateur d'objets, développez de manière récursive le nœud **Gestion** vers le bas et en incluant le pool de ressources qui contient le groupe de charge de travail à modifier.</span><span class="sxs-lookup"><span data-stu-id="eea8d-118">In Object Explorer, recursively expand the **Management** node down to and including the resource pool that contains the workload group to be modified.</span></span>  
  
2.  <span data-ttu-id="eea8d-119">Cliquez avec le bouton droit sur le dossier **Groupes de charge de travail** , puis sélectionnez **Nouveau groupe de charge de travail**.</span><span class="sxs-lookup"><span data-stu-id="eea8d-119">Right-click the **Workload Groups** folder, and then click **New Workload Group**.</span></span>  
  
3.  <span data-ttu-id="eea8d-120">Dans la grille **Pools de ressources** , assurez-vous que le pool de ressources où vous souhaitez ajouter le groupe de charge de travail est mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="eea8d-120">In the **Resource pools** grid, ensure the resource pool where you want to add the workload group is highlighted.</span></span>  
  
4.  <span data-ttu-id="eea8d-121">La grille **Groupes de charge de travail pour le pool de ressources** comportera une nouvelle ligne avec un nom vide et des valeurs par défaut dans les autres colonnes.</span><span class="sxs-lookup"><span data-stu-id="eea8d-121">The **Workload groups for resource pool** grid will have a new line with a blank name and default values in the other columns.</span></span>  
  
5.  <span data-ttu-id="eea8d-122">Cliquez sur la cellule **Nom** et entrez un nom pour le groupe de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="eea8d-122">Click the **Name** cell and enter a name for the workload group.</span></span>  
  
6.  <span data-ttu-id="eea8d-123">Cliquez ou double-cliquez sur toutes les autres cellules de la ligne dont vous souhaitez modifier les paramètres par défaut, puis entrez les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="eea8d-123">Click or double-click any other cells in the row you want to change from their default settings, and enter the new values.</span></span>  
  
7.  <span data-ttu-id="eea8d-124">Cliquez sur **OK**pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="eea8d-124">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-workload-group-using-transact-sql"></a><a name="CreWGTSQL"></a> <span data-ttu-id="eea8d-125">Créer un groupe de charge de travail avec Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eea8d-125">Create a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="eea8d-126">**Pour créer un groupe de charge de travail à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="eea8d-126">**To create a workload group by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="eea8d-127">Exécutez l'instruction CREATE WORKLOAD GROUP en spécifiant les valeurs de propriété à définir.</span><span class="sxs-lookup"><span data-stu-id="eea8d-127">Run the CREATE WORKLOAD GROUP statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="eea8d-128">Exécutez l'instruction ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="eea8d-128">Run the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="eea8d-129">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eea8d-129">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="eea8d-130">L'exemple suivant crée un groupe de charge de travail nommé `groupAdhoc` dans le pool de ressources nommé `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="eea8d-130">The following example creates a workload group named `groupAdhoc` in the resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE WORKLOAD GROUP groupAdhoc  
USING poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="eea8d-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eea8d-131">See Also</span></span>  
 <span data-ttu-id="eea8d-132">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="eea8d-132">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="eea8d-133">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="eea8d-133">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="eea8d-134">[Créer un pool de ressources](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="eea8d-134">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="eea8d-135">[Modifier les paramètres de groupe de charge de travail](change-workload-group-settings.md) </span><span class="sxs-lookup"><span data-stu-id="eea8d-135">[Change Workload Group Settings](change-workload-group-settings.md) </span></span>  
 <span data-ttu-id="eea8d-136">[Créer et tester une fonction classifieur définie par l’utilisateur](create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="eea8d-136">[Create and Test a Classifier User-Defined Function](create-and-test-a-classifier-user-defined-function.md) </span></span>  
 <span data-ttu-id="eea8d-137">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eea8d-137">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="eea8d-138">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eea8d-138">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
