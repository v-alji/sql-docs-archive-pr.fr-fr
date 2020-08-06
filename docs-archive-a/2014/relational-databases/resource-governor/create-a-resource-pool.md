---
title: Créer un pool de ressources | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- resource pools [SQL Server], create
- Resource Governor, resource pool create
ms.assetid: 44dd0567-a4c8-4c72-89ff-e76f6ddef344
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5abd2e60f4f9bb5290b47f95349782f8b26ad8bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614483"
---
# <a name="create-a-resource-pool"></a><span data-ttu-id="577a7-102">Créer un pool de ressources</span><span class="sxs-lookup"><span data-stu-id="577a7-102">Create a Resource Pool</span></span>
  <span data-ttu-id="577a7-103">Vous pouvez créer un pool de ressources à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="577a7-103">You can create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="577a7-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="577a7-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="577a7-105">**Pour créer un pool de ressources avec :**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span><span class="sxs-lookup"><span data-stu-id="577a7-105">**To create a resource pool, using:**  [SQL Server Management Studio](#CreRPProp), [Transact-SQL](#CreRPTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="577a7-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="577a7-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="577a7-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="577a7-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="577a7-108">Le pourcentage maximal de l'UC doit être supérieur ou égal au pourcentage minimal de l'UC.</span><span class="sxs-lookup"><span data-stu-id="577a7-108">The maximum CPU percentage must be equal to or higher than the minimum CPU percentage.</span></span> <span data-ttu-id="577a7-109">Le pourcentage maximal de mémoire doit être supérieur ou égal au pourcentage minimal de mémoire.</span><span class="sxs-lookup"><span data-stu-id="577a7-109">The maximum memory percentage must be equal to or higher than the minimum memory percentage.</span></span>  
  
 <span data-ttu-id="577a7-110">La somme des pourcentages d'UC minimal et de mémoire minimal pour tous les pools de ressources ne doit pas dépasser 100.</span><span class="sxs-lookup"><span data-stu-id="577a7-110">The sums of the minimum CPU percentages and minimum memory percentages for all resource pools must not exceed 100.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="577a7-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="577a7-111">Permissions</span></span>  
 <span data-ttu-id="577a7-112">La création d'un pool de ressources requiert l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="577a7-112">Creating a resource pool requires CONTROL SERVER permission.</span></span>  
  
##  <a name="create-a-resource-pool-using-sql-server-management-studio"></a><a name="CreRPProp"></a> <span data-ttu-id="577a7-113">Créer un pool de ressources à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="577a7-113">Create a Resource Pool Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="577a7-114">**Pour créer un pool de ressources à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="577a7-114">**To create a resource pool by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="577a7-115">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l'Explorateur d'objets et développez de manière récursive le nœud **Gestion** jusqu'à **Resource Governor**inclus.</span><span class="sxs-lookup"><span data-stu-id="577a7-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="577a7-116">Cliquez avec le bouton droit sur **Resource Governor**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="577a7-116">Right-click **Resource Governor**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="577a7-117">Dans la grille **Pools de ressources** , cliquez sur la première colonne dans la ligne vide.</span><span class="sxs-lookup"><span data-stu-id="577a7-117">In the **Resource pools** grid, click the first column in the empty row.</span></span> <span data-ttu-id="577a7-118">Cette colonne est marquée d'un astérisque (\*).</span><span class="sxs-lookup"><span data-stu-id="577a7-118">This column is labeled with an asterisk (\*).</span></span>  
  
4.  <span data-ttu-id="577a7-119">Double-cliquez sur la cellule vide dans la colonne **Nom** .</span><span class="sxs-lookup"><span data-stu-id="577a7-119">Double-click the empty cell in the **Name** column.</span></span> <span data-ttu-id="577a7-120">Tapez le nom de votre choix pour le pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="577a7-120">Type in the name that you want to use for the resource pool.</span></span>  
  
5.  <span data-ttu-id="577a7-121">Cliquez ou double-cliquez sur toutes les autres cellules de la ligne que vous souhaitez modifier, puis entrez les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="577a7-121">Click or double-click any other cells in the row you want to change, and enter the new values.</span></span>  
  
6.  <span data-ttu-id="577a7-122">Cliquez sur **OK**pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="577a7-122">To save the changes, click **OK**</span></span>  
  
##  <a name="create-a-resource-pool-using-transact-sql"></a><a name="CreRPTSQL"></a> <span data-ttu-id="577a7-123">Créer un pool de ressources à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="577a7-123">Create a Resource Pool Using Transact-SQL</span></span>  
 <span data-ttu-id="577a7-124">**Pour créer un pool de ressources à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="577a7-124">**To create a resource pool by using [!INCLUDE[tsql](../../includes/tsql-md.md)]**</span></span>  
  
1.  <span data-ttu-id="577a7-125">Exécutez l'instruction `CREATE RESOURCE POOL` en spécifiant les valeurs de propriété à définir.</span><span class="sxs-lookup"><span data-stu-id="577a7-125">Run the `CREATE RESOURCE POOL` statement specifying the property values to be set.</span></span>  
  
2.  <span data-ttu-id="577a7-126">Exécutez l'instruction **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="577a7-126">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="577a7-127">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="577a7-127">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="577a7-128">L'exemple suivant crée un pool de ressources nommé `poolAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="577a7-128">The following example creates a resource pool named `poolAdhoc`.</span></span>  
  
```  
CREATE RESOURCE POOL poolAdhoc  
WITH (MAX_CPU_PERCENT = 20);  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="577a7-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="577a7-129">See Also</span></span>  
 <span data-ttu-id="577a7-130">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="577a7-130">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="577a7-131">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="577a7-131">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="577a7-132">[Pool de ressources de Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="577a7-132">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="577a7-133">[Modifier les paramètres de pool de ressources](change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="577a7-133">[Change Resource Pool Settings](change-resource-pool-settings.md) </span></span>  
 <span data-ttu-id="577a7-134">[Supprimer un pool de ressources](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="577a7-134">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="577a7-135">[Configurer le gouverneur de ressources à l'aide d'un modèle](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="577a7-135">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="577a7-136">[Groupe de charge de travail de Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="577a7-136">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="577a7-137">[Fonction classifieur de Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="577a7-137">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="577a7-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="577a7-138">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="577a7-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="577a7-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
