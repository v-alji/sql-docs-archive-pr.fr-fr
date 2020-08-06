---
title: Modifier les paramètres de pool de ressources | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, resource pool alter
- resource pools [SQL Server], alter
ms.assetid: 49438285-a011-4dac-bd4f-f35cd90fda61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2183cceaaf8a3e183d96c154075f9a922942c2c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697878"
---
# <a name="change-resource-pool-settings"></a><span data-ttu-id="b0691-102">Modifier les paramètres de pool de ressources</span><span class="sxs-lookup"><span data-stu-id="b0691-102">Change Resource Pool Settings</span></span>
  <span data-ttu-id="b0691-103">Vous pouvez modifier des paramètres de pool de ressources à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0691-103">You can change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="b0691-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="b0691-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="b0691-105">**Pour modifier les paramètres d’un pool de ressources avec :**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="b0691-105">**To change the settings for a resource pool, using:**  [SQL Server Management Studio](#ChgRPProp), [Transact-SQL](#ChgRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b0691-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b0691-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="b0691-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b0691-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b0691-108">Le pourcentage maximal de l'UC doit être supérieur ou égal au pourcentage minimal de l'UC.</span><span class="sxs-lookup"><span data-stu-id="b0691-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="b0691-109">Le pourcentage maximal de mémoire doit être supérieur ou égal au pourcentage minimal de mémoire.</span><span class="sxs-lookup"><span data-stu-id="b0691-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="b0691-110">La somme des pourcentages d'UC minimal et de mémoire minimal pour tous les pools de ressources ne doit pas dépasser 100.</span><span class="sxs-lookup"><span data-stu-id="b0691-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b0691-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b0691-111">Permissions</span></span>  
 <span data-ttu-id="b0691-112">La modification des paramètres du pool de ressources requiert l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="b0691-112">Changing resource pool settings requires CONTROL SERVER permission.</span></span>  
  
##  <a name="change-resource-pool-settings-using-sql-server-management-studio"></a><a name="ChgRPProp"></a> <span data-ttu-id="b0691-113">Modifier les paramètres du pool de ressources à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0691-113">Change Resource Pool Settings Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b0691-114">**Pour modifier les paramètres du pool de ressources à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="b0691-114">**To change resource pool settings by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="b0691-115">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l’Explorateur d’objets et développez de manière récursive le nœud **Gestion** jusqu’à **Pools de ressources**.</span><span class="sxs-lookup"><span data-stu-id="b0691-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="b0691-116">Cliquez avec le bouton droit sur le pool de ressources à modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b0691-116">Right-click the resource pool to be modified, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="b0691-117">Dans la page **Propriétés de Resource Governor** , sélectionnez la ligne du pool de ressources dans la grille **Pools de ressources** si elle n'est pas sélectionnée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b0691-117">In the **Resource Governor Properties** page, select the row for the resource pool in the **Resource pools** grid if it is not automatically selected.</span></span>  
  
4.  <span data-ttu-id="b0691-118">Cliquez ou double-cliquez sur les cellules de la ligne à modifier, puis entrez les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="b0691-118">Click or double-click the cells in the row to be changed, and enter the new values.</span></span>  
  
5.  <span data-ttu-id="b0691-119">Cliquez sur **OK**pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="b0691-119">To save the changes, click **OK**</span></span>  
  
##  <a name="change-resource-pool-settings-using-transact-sql"></a><a name="ChgRPTSQL"></a> <span data-ttu-id="b0691-120">Modifier les paramètres du pool de ressources à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b0691-120">Change Resource Pool Settings Using Transact-SQL</span></span>  
 <span data-ttu-id="b0691-121">**Pour modifier les paramètres du pool de ressources à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="b0691-121">**To change resource pool settings by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="b0691-122">Exécutez l'instruction `ALTER RESOURCE POOL` en spécifiant les valeurs de propriété à modifier.</span><span class="sxs-lookup"><span data-stu-id="b0691-122">Run the `ALTER RESOURCE POOL` statement specifying the property values to be changed.</span></span>  
  
2.  <span data-ttu-id="b0691-123">Exécutez l'instruction **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="b0691-123">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="b0691-124">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b0691-124">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="b0691-125">L'exemple suivant modifie le paramètre de pourcentage maximal de l'UC pour le pool de ressources nommé `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="b0691-125">The following example changes the max CPU percentage setting for the resource pool named `poolAdhoc`.</span></span>  
  
```  
ALTER RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 25);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0691-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0691-126">See Also</span></span>  
 <span data-ttu-id="b0691-127">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="b0691-127">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="b0691-128">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="b0691-128">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="b0691-129">[Créer un pool de ressources](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="b0691-129">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="b0691-130">[Supprimer un pool de ressources](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="b0691-130">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="b0691-131">[Groupe de charge de travail de Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="b0691-131">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="b0691-132">[Fonction classifieur de Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="b0691-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="b0691-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b0691-133">[ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="b0691-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b0691-134">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
