---
title: Déplacer un groupe de charge de travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties_moveworkloadgroup.f1
helpviewer_keywords:
- workload groups [SQL Server], move
- Resource Governor, workload group move
ms.assetid: f2068636-6e53-486a-a6fc-c12de2a38424
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f73b48f0ec2255760b4ee55acfaf91dc02af7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699390"
---
# <a name="move-a-workload-group"></a><span data-ttu-id="4f405-102">Déplacer un groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="4f405-102">Move a Workload Group</span></span>
  <span data-ttu-id="4f405-103">Vous pouvez déplacer un groupe de charge de travail de Resource Governor vers un pool de ressources différent à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="4f405-103">You can move a Resource Governor workload group to a different resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="4f405-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="4f405-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="4f405-105">**Pour déplacer un groupe de charge de travail avec :**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="4f405-105">**To move a workload group, using:**  [SQL Server Management Studio](#MoveWGSSMS), [Transact-SQL](#MoveWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4f405-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4f405-106">Before You Begin</span></span>  
 <span data-ttu-id="4f405-107">Vous ne pouvez pas déplacer un groupe de charge de travail s'il existe une opération en attente de configuration de Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="4f405-107">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="4f405-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4f405-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4f405-109">Vous ne pouvez pas déplacer un groupe de charge de travail s'il existe une opération en attente de configuration de Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="4f405-109">You cannot move a workload group if there is a pending Resource Governor configuration operation.</span></span> <span data-ttu-id="4f405-110">Vous pouvez déterminer s’il existe une configuration en attente en interrogeant la vue de gestion dynamique [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) pour obtenir l’état en cours d’is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="4f405-110">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f405-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4f405-111">Permissions</span></span>  
 <span data-ttu-id="4f405-112">Le déplacement d'un groupe de charge de travail nécessite l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="4f405-112">Moving a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="move-a-workload-group-using-sql-server-management-studio"></a><a name="MoveWGSSMS"></a> <span data-ttu-id="4f405-113">Déplacer un groupe de charge de travail à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f405-113">Move a Workload Group Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4f405-114">**Pour déplacer un groupe de charge de travail à l'aide de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="4f405-114">**To move a workload group by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**</span></span>  
  
1.  <span data-ttu-id="4f405-115">Dans l'Explorateur d'objets, développez de manière récursive le nœud **Gestion** vers le bas jusqu'à **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="4f405-115">In Object Explorer, recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="4f405-116">Cliquez avec le bouton droit sur **Resource Governor** , puis sélectionnez **Propriétés**afin d’ouvrir la page **Propriétés de Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="4f405-116">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="4f405-117">Dans la fenêtre **Pools de ressources** , cliquez sur pool de ressources qui contient le groupe de charge de travail à déplacer.</span><span class="sxs-lookup"><span data-stu-id="4f405-117">In the **Resource Pools** window, click the resource pool containing the workload group to be moved.</span></span> <span data-ttu-id="4f405-118">La fenêtre **Groupes de charge de travail** répertorie maintenant les groupes de charge de travail de ce pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="4f405-118">The **Workload Groups** window now lists the workload groups in that resource pool.</span></span>  
  
4.  <span data-ttu-id="4f405-119">Dans la fenêtre **Groupes de charge de travail** , cliquez avec le bouton droit sur la flèche vers la droite à gauche du groupe de charge de travail à déplacer, puis sélectionnez **Déplacer vers**.</span><span class="sxs-lookup"><span data-stu-id="4f405-119">In the **Workload Groups** window, right-click the right arrow to the left of the workload group to be moved, and click **Move to**.</span></span> <span data-ttu-id="4f405-120">Cela affiche une fenêtre **Déplacer le groupe de charge de travail** .</span><span class="sxs-lookup"><span data-stu-id="4f405-120">This displays a **Move Workload Group** window.</span></span>  
  
5.  <span data-ttu-id="4f405-121">Les pools de ressources disponibles sont affichés dans la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="4f405-121">Available resource pools are displayed in the window.</span></span> <span data-ttu-id="4f405-122">Cliquez sur le nom du pool de ressources vers lequel vous souhaitez déplacer le groupe de charge de travail, puis cliquez sur **OK** pour effectuer cette action.</span><span class="sxs-lookup"><span data-stu-id="4f405-122">Click the name of the resource pool that you want to move the workload group to, and then click **OK** to carry out this action.</span></span>  
  
6.  <span data-ttu-id="4f405-123">Cette action n'est pas effectuée tant que vous n'avez pas cliqué sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f405-123">This action is not completed until after you click **OK**.</span></span> <span data-ttu-id="4f405-124">Lorsque vous cliquez sur **OK**, l'instruction ALTER RESOURCE GOVERNOR RECONFIGURE est exécutée.</span><span class="sxs-lookup"><span data-stu-id="4f405-124">When you click **OK**, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
7.  <span data-ttu-id="4f405-125">Si l'opération de création ou de reconfiguration du pool de ressources ou du groupe de charge de travail échoue, un message d'erreur récapitulatif apparaît sous le titre de la page de propriétés.</span><span class="sxs-lookup"><span data-stu-id="4f405-125">If the create or reconfigure operation fails for the resource pool or workload group, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="4f405-126">Pour consulter le message d'erreur détaillé, cliquez sur la flèche vers le bas du message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="4f405-126">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
##  <a name="move-a-workload-group-using-transact-sql"></a><a name="MoveWGTSQL"></a> <span data-ttu-id="4f405-127">Déplacer un groupe de charge de travail à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f405-127">Move a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="4f405-128">**Pour déplacer un groupe de charge de travail à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4f405-128">**To move a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="4f405-129">Exécutez l'instruction `ALTER WORKLOAD GROUP` en spécifiant le nom du groupe de charge de travail à déplacer, ainsi que le pool de ressources vers lequel il doit être déplacé.</span><span class="sxs-lookup"><span data-stu-id="4f405-129">Run the `ALTER WORKLOAD GROUP` statement specifying the name of the workload group to be moved and the resource pool to which it should be moved.</span></span>  
  
2.  <span data-ttu-id="4f405-130">Exécutez l'instruction **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="4f405-130">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="4f405-131">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4f405-131">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="4f405-132">L'exemple suivant déplace un groupe de charge de travail nommé `groupAdhoc` vers le pool de ressources par défaut.</span><span class="sxs-lookup"><span data-stu-id="4f405-132">The following example moves a workload group named `groupAdhoc` to the default resource pool.</span></span>  
  
```  
ALTER WORKLOAD GROUP groupAdhoc  
USING [default];  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f405-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f405-133">See Also</span></span>  
 <span data-ttu-id="4f405-134">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="4f405-134">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="4f405-135">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="4f405-135">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="4f405-136">[Créer un pool de ressources](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="4f405-136">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="4f405-137">[Créer un groupe de charge de travail](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="4f405-137">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="4f405-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4f405-138">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 [<span data-ttu-id="4f405-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4f405-139">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
