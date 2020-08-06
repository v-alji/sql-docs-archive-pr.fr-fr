---
title: Supprimer un pool de ressources | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool delete
- resource pools [SQL Server], delete
ms.assetid: 3bdd348b-6582-4ffa-80ef-d49e50596ce5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a67b0e2262fa3007597091b6087cc937bb0f3276
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699407"
---
# <a name="delete-a-resource-pool"></a><span data-ttu-id="c9559-102">Supprimer un pool de ressources</span><span class="sxs-lookup"><span data-stu-id="c9559-102">Delete a Resource Pool</span></span>
  <span data-ttu-id="c9559-103">Vous pouvez supprimer un pool de ressources à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="c9559-103">You can delete a resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="c9559-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="c9559-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="c9559-105">**Pour supprimer un pool de ressources avec :** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="c9559-105">**To delete a resource pool, using:** [SQL Server Management Studio](#DelRPSSMS), [Transact-SQL](#DelRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c9559-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c9559-106">Before You Begin</span></span>  
 <span data-ttu-id="c9559-107">Vous ne pouvez pas supprimer un pool de ressources s'il contient des groupes de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="c9559-107">You cannot delete a resource pool if it contains workload groups.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="c9559-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c9559-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c9559-109">Vous ne pouvez pas supprimer les pools de ressources par défaut ou internes de Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="c9559-109">You cannot delete the Resource Governor default or internal resource pools.</span></span> <span data-ttu-id="c9559-110">Vous ne pouvez pas supprimer un pool de ressources s'il contient des groupes de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="c9559-110">You cannot delete a resource pool if it contains workload groups.</span></span> <span data-ttu-id="c9559-111">Pour plus d’informations, consultez [Delete a Workload Group](delete-a-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="c9559-111">For more information, see [Delete a Workload Group](delete-a-workload-group.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c9559-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c9559-112">Permissions</span></span>  
 <span data-ttu-id="c9559-113">La suppression d'un pool de ressources requiert l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="c9559-113">Deleting a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-resource-pool-using-object-explorer"></a><a name="DelRPSSMS"></a> <span data-ttu-id="c9559-114">Supprimer un pool de ressources à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="c9559-114">Delete a Resource Pool Using Object Explorer</span></span>  
 <span data-ttu-id="c9559-115">**Pour supprimer un pool de ressources à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="c9559-115">**To delete a resource pool by using SQL Server Management Studio**</span></span>  
  
1.  <span data-ttu-id="c9559-116">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l'Explorateur d'objets et développez de manière récursive le nœud **Gestion** jusqu'à **Resource Governor**inclus.</span><span class="sxs-lookup"><span data-stu-id="c9559-116">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="c9559-117">Cliquez avec le bouton droit sur le pool de ressources à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c9559-117">Right-click the resource pool to be deleted, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="c9559-118">Dans la fenêtre **Supprimer un objet** , le pool de ressources est répertorié dans la liste **Objet à supprimer** .</span><span class="sxs-lookup"><span data-stu-id="c9559-118">In the **Delete Object** window, the resource pool is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="c9559-119">Pour supprimer le pool de ressources, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9559-119">To delete the resource pool, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c9559-120">Si le pool de ressources que vous cherchez à supprimer contient un groupe de charge de travail, l'action échoue.</span><span class="sxs-lookup"><span data-stu-id="c9559-120">If the resource pool that you are trying to delete contains a workload group, this action will fail.</span></span>  
  
##  <a name="delete-a-resource-pool-using-transact-sql"></a><a name="DelRPTSQL"></a> <span data-ttu-id="c9559-121">Supprimer un pool de ressources à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9559-121">Delete a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="c9559-122">**Pour supprimer un pool de ressources à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="c9559-122">**To delete a resource pool by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="c9559-123">Exécutez l'instruction `DROP RESOURCE POOL` en spécifiant le nom du pool de ressources à supprimer.</span><span class="sxs-lookup"><span data-stu-id="c9559-123">Run the `DROP RESOURCE POOL` statement specifying the name of the resource pool to delete.</span></span>  
  
2.  <span data-ttu-id="c9559-124">Exécutez l'instruction **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="c9559-124">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="c9559-125">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c9559-125">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="c9559-126">L'exemple suivant supprime un groupe de charge de travail nommé `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="c9559-126">The following example drops a workload group named `poolAdhoc`.</span></span>  
  
```  
DROP RESOURCE POOL poolAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9559-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9559-127">See Also</span></span>  
 <span data-ttu-id="c9559-128">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="c9559-128">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="c9559-129">[Pool de ressources de Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="c9559-129">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="c9559-130">[Créer un pool de ressources](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="c9559-130">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="c9559-131">[Modifier les paramètres de pool de ressources](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="c9559-131">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="c9559-132">[Groupe de charge de travail de Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="c9559-132">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="c9559-133">[Fonction classifieur de Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="c9559-133">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="c9559-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9559-134">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="c9559-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9559-135">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="c9559-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c9559-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
