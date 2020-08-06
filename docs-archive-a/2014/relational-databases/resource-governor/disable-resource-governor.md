---
title: Désactiver Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, disabling
ms.assetid: 2c2d2db0-34a5-4f50-b783-17693e3ce3f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 172f01bdde0f792cd9ed72ad371e5811b8de8885
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699402"
---
# <a name="disable-resource-governor"></a><span data-ttu-id="02267-102">Désactiver Resource Governor</span><span class="sxs-lookup"><span data-stu-id="02267-102">Disable Resource Governor</span></span>
  <span data-ttu-id="02267-103">Vous pouvez désactiver Resource Governor à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="02267-103">You can disable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="02267-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="02267-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="02267-105">**Pour désactiver Resource Governor avec :**  [Explorateur d’objets](#RGOffObjEx), [Propriétés de Resource Governor](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span><span class="sxs-lookup"><span data-stu-id="02267-105">**To disable Resource Governorn, using:**  [Object Explorer](#RGOffObjEx), [Resource Governor Properties](#RGOffProp), [Transact-SQL](#RGOffTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="02267-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="02267-106">Before You Begin</span></span>  
 <span data-ttu-id="02267-107">La désactivation de Resource Governor entraîne les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="02267-107">Disabling the Resource Governor has the following results:</span></span>  
  
-   <span data-ttu-id="02267-108">La fonction classifieur n'est pas exécutée.</span><span class="sxs-lookup"><span data-stu-id="02267-108">The classifier function is not run.</span></span>  
  
-   <span data-ttu-id="02267-109">Toutes les nouvelles connexions sont classées automatiquement dans le groupe de charge de travail par défaut.</span><span class="sxs-lookup"><span data-stu-id="02267-109">All new connections are automatically classified into the default workload group.</span></span>  
  
-   <span data-ttu-id="02267-110">Les demandes initiées par le système sont classées dans le groupe de charge de travail interne.</span><span class="sxs-lookup"><span data-stu-id="02267-110">System-initiated requests are classified into the internal workload group.</span></span>  
  
-   <span data-ttu-id="02267-111">Tous les paramètres de groupe de charges de travail et de pool de ressources existants sont réinitialisés à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="02267-111">All existing workload group and resource pool settings are reset to their default values.</span></span> <span data-ttu-id="02267-112">Dans ce cas, aucun événement n'est déclenché lorsque les limites sont atteintes.</span><span class="sxs-lookup"><span data-stu-id="02267-112">In this case, no events are fired when limits are reached.</span></span>  
  
-   <span data-ttu-id="02267-113">La surveillance système normale n'est pas affectée.</span><span class="sxs-lookup"><span data-stu-id="02267-113">Normal system monitoring is not affected.</span></span>  
  
-   <span data-ttu-id="02267-114">La configuration peut être modifiée, mais les modifications n'entrent en vigueur qu'une fois que Resource Governor est activé.</span><span class="sxs-lookup"><span data-stu-id="02267-114">Configuration changes can be made, but the changes do not take effect until the Resource Governor is enabled.</span></span>  
  
-   <span data-ttu-id="02267-115">Lors du redémarrage de SQL Server, Resource Governor ne chargera pas sa configuration, mais à la place aura uniquement des pools de ressources et les groupes de charge de travail par défaut et internes.</span><span class="sxs-lookup"><span data-stu-id="02267-115">Upon restarting SQL Server, the Resource Governor will not load its configuration, but instead will have only the default and internal workload groups and resource pools.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="02267-116">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="02267-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="02267-117">Vous ne pouvez pas utiliser l'instruction `ALTER RESOURCE GOVERNOR` pour désactiver le gouverneur de ressources pendant une transaction utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02267-117">You cannot use the `ALTER RESOURCE GOVERNOR` statement to disable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="02267-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="02267-118">Permissions</span></span>  
 <span data-ttu-id="02267-119">La désactivation de Resource Governor requiert l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="02267-119">Disabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="disable-resource-governor-using-object-explorer"></a><a name="RGOffObjEx"></a> <span data-ttu-id="02267-120">Désactiver Resource Governor à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="02267-120">Disable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="02267-121">**Pour désactiver Resource Governor à l'aide de l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="02267-121">**To disable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="02267-122">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l'Explorateur d'objets et développez de manière récursive le nœud **Gestion** jusqu'au **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="02267-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="02267-123">Cliquez avec le bouton droit sur **Resource Governor**, puis sélectionnez **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="02267-123">Right-click **Resource Governor**, and then click **Disable**.</span></span>  
  
##  <a name="disable-resource-governor-using-resource-governor-properties"></a><a name="RGOffProp"></a> <span data-ttu-id="02267-124">Désactiver Resource Governor à l'aide des propriétés de Resource Governor</span><span class="sxs-lookup"><span data-stu-id="02267-124">Disable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="02267-125">**Pour désactiver Resource Governor à l'aide de la page Propriétés de Resource Governor**</span><span class="sxs-lookup"><span data-stu-id="02267-125">**To disable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="02267-126">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l'Explorateur d'objets et développez de manière récursive le nœud **Gestion** jusqu'au **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="02267-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="02267-127">Cliquez avec le bouton droit sur **Resource Governor** , puis sélectionnez **Propriétés**afin d’ouvrir la page **Propriétés de Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="02267-127">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="02267-128">Activez la case à cocher **Activer Resource Governor** , vérifiez que la case à cocher n'est pas sélectionnée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="02267-128">Click the **Enable Resource Governor** check box, ensure that the box is not selected, and then click **OK**.</span></span>  
  
##  <a name="disable-resource-governor-using-transact-sql"></a><a name="RGOffTSQL"></a> <span data-ttu-id="02267-129">Désactiver Resource Governor à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02267-129">Disable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="02267-130">**Pour désactiver Resource Governor à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="02267-130">**To disable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="02267-131">Exécutez l'instruction **ALTER RESOURCE GOVERNOR DISABLE** .</span><span class="sxs-lookup"><span data-stu-id="02267-131">Run the **ALTER RESOURCE GOVERNOR DISABLE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="02267-132">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="02267-132">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="02267-133">L'exemple suivant active Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="02267-133">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR DISABLE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="02267-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02267-134">See Also</span></span>  
 <span data-ttu-id="02267-135">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="02267-135">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="02267-136">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="02267-136">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="02267-137">[Pool de ressources de Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="02267-137">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="02267-138">[Groupe de charge de travail de Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="02267-138">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="02267-139">[Fonction classifieur de Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="02267-139">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="02267-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="02267-140">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
