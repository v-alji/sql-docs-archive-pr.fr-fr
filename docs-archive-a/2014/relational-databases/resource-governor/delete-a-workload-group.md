---
title: Supprimer un groupe de charge de travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- workload groups [SQL Server], delete
- Resource Governor, workload group delete
ms.assetid: d5902c46-5c28-4ac1-8b56-cb4ca2b072d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 801a731db6c5b31bc479d1a3f6079c45ad9a7c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699419"
---
# <a name="delete-a-workload-group"></a><span data-ttu-id="8c365-102">Supprimer un groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="8c365-102">Delete a Workload Group</span></span>
  <span data-ttu-id="8c365-103">Vous pouvez supprimer un groupe de charge de travail ou un pool de ressources à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="8c365-103">You can delete a workload group or resource pool by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="8c365-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="8c365-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="8c365-105">**Pour supprimer un groupe de charge de travail avec :**  [Explorateur d’objets](#DelWGObjEx), [Propriétés de Resource Governor](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span><span class="sxs-lookup"><span data-stu-id="8c365-105">**To delete a workload group, using:**  [Object Explorer](#DelWGObjEx), [Resource Governor Properties](#DelWGRGProp), [Transact-SQL](#DelWGTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8c365-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8c365-106">Before You Begin</span></span>  
 <span data-ttu-id="8c365-107">Vous ne pouvez pas supprimer un groupe de charge de travail s'il contient des sessions actives.</span><span class="sxs-lookup"><span data-stu-id="8c365-107">You cannot delete a workload group if it contains active sessions.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="8c365-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8c365-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8c365-109">Si un groupe de charge de travail contient des sessions actives, sa suppression ou son déplacement vers un pool de ressources différent échoue lorsque l'instruction ALTER RESOURCE GOVERNOR RECONFIGURE est appelée pour appliquer la modification.</span><span class="sxs-lookup"><span data-stu-id="8c365-109">If a workload group contains active sessions, deleting or moving the workload group to a different resource pool will fail when the ALTER RESOURCE GOVERNOR RECONFIGURE statement is called to apply the change.</span></span> <span data-ttu-id="8c365-110">Pour éviter ce problème, vous pouvez suivre l'une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c365-110">To avoid this problem, you can take one of the following actions:</span></span>  
  
-   <span data-ttu-id="8c365-111">Attendez la déconnexion de toutes les sessions du groupe affecté, puis réexécutez l'instruction ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="8c365-111">Wait until all the sessions from the affected group have disconnected, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span>  
  
-   <span data-ttu-id="8c365-112">Arrêtez explicitement les sessions du groupe affecté à l'aide de la commande KILL, puis réexécutez l'instruction ALTER RESOURCE GOVERNOR RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="8c365-112">Explicitly stop sessions in the affected group by using the KILL command, and then rerun the ALTER RESOURCE GOVERNOR RECONFIGURE statement.</span></span> <span data-ttu-id="8c365-113">Si vous décidez que vous ne souhaitez pas arrêter des sessions explicitement après avoir utilisé **Supprimer** mais avant d’arrêter des sessions actives, recréez le groupe en utilisant le nom d’origine et déplacez le groupe vers le pool de ressources d’origine.</span><span class="sxs-lookup"><span data-stu-id="8c365-113">If you decide that you do not want to explicitly stop sessions after you use **Delete** but before you stop active sessions, re-create the group by using the original name and move the group to the original resource pool.</span></span>  
  
-   <span data-ttu-id="8c365-114">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="8c365-114">Restart the server.</span></span> <span data-ttu-id="8c365-115">Au terme du processus de redémarrage, le groupe supprimé ne sera pas créé, et un groupe déplacé utilisera la nouvelle affectation de pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="8c365-115">After the restart process is completed, the deleted group will not be created, and a moved group will use the new resource pool assignment.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8c365-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8c365-116">Permissions</span></span>  
 <span data-ttu-id="8c365-117">La suppression d'un groupe de charge de travail nécessite l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="8c365-117">Deleting a workload group requires CONTROL SERVER permission.</span></span>  
  
##  <a name="delete-a-workload-group-using-object-explorer"></a><a name="DelWGObjEx"></a> <span data-ttu-id="8c365-118">Supprimer un groupe de charge de travail à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="8c365-118">Delete a Workload Group Using Object Explorer</span></span>  
 <span data-ttu-id="8c365-119">**Pour supprimer un groupe de charge de travail à l'aide de l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="8c365-119">**To delete a workload group by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="8c365-120">Dans[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l'Explorateur d'objets, développez de manière récursive le nœud **Gestion** jusqu'à **Pools de ressources**.</span><span class="sxs-lookup"><span data-stu-id="8c365-120">In[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="8c365-121">Développez de manière récursive **Pools de ressources** vers le bas et en incluant le nœud **Groupes de charge de travail** dans le pool de ressources qui contient le groupe de charge de travail à supprimer.</span><span class="sxs-lookup"><span data-stu-id="8c365-121">Recursively expand **Resource Pools** down to and including the **Workload Groups** node in the resource pool that contains the workload group to be deleted.</span></span>  
  
3.  <span data-ttu-id="8c365-122">Cliquez avec le bouton droit sur le groupe de charge de travail, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="8c365-122">Right-click the workload group, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="8c365-123">Dans la fenêtre **Supprimer un objet** , le groupe de charge de travail est répertorié dans la liste **Objet à supprimer** .</span><span class="sxs-lookup"><span data-stu-id="8c365-123">In the **Delete Object** window, the workload group is listed in the **Object to be deleted** list.</span></span> <span data-ttu-id="8c365-124">Pour supprimer le groupe de charge de travail, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c365-124">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-resource-governor-properties"></a><a name="DelWGRGProp"></a> <span data-ttu-id="8c365-125">Supprimer un groupe de charge de travail à l'aide des propriétés de Resource Governor</span><span class="sxs-lookup"><span data-stu-id="8c365-125">Delete a Workload Group Using Resource Governor Properties</span></span>  
 <span data-ttu-id="8c365-126">**Pour supprimer un groupe de charge de travail à l'aide de la page Propriétés de Resource Governor**</span><span class="sxs-lookup"><span data-stu-id="8c365-126">**To delete a workload group by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="8c365-127">Dans l'Explorateur d'objets, développez de manière récursive le nœud **Gestion** jusqu'à **Pools de ressources**inclus.</span><span class="sxs-lookup"><span data-stu-id="8c365-127">In Object Explorer, recursively expand the **Management** node down to and including **Resource Pools**.</span></span>  
  
2.  <span data-ttu-id="8c365-128">Cliquez avec le bouton droit sur le pool de ressources qui contient le groupe de charge de travail à supprimer, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8c365-128">Right-click the resource pool that contains the workload group to be deleted, and then click **Properties**.</span></span> <span data-ttu-id="8c365-129">Cette procédure ouvre la page **Propriétés de Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="8c365-129">This opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="8c365-130">Dans la fenêtre **Groupes de charge de travail pour le pool de ressources** , cliquez sur la ligne du groupe de charge de travail à supprimer, puis cliquez avec le bouton droit sur la flèche droite à gauche de la ligne et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="8c365-130">In the **Workload groups for resource pool** window, click the line for the workload group to be deleted, then right-click the right arrow on the left side of the line, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="8c365-131">Pour supprimer le groupe de charge de travail, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c365-131">To delete the workload group, click **OK**.</span></span>  
  
##  <a name="delete-a-workload-group-using-transact-sql"></a><a name="DelWGTSQL"></a> <span data-ttu-id="8c365-132">Supprimer un groupe de charge de travail à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8c365-132">Delete a Workload Group Using Transact-SQL</span></span>  
 <span data-ttu-id="8c365-133">**Pour supprimer un groupe de charge de travail à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="8c365-133">**To delete a workload group by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="8c365-134">Exécutez l'instruction `DROP WORKLOAD GROUP` en spécifiant le nom du groupe de charge de travail à supprimer.</span><span class="sxs-lookup"><span data-stu-id="8c365-134">Run the `DROP WORKLOAD GROUP` statement specifying the name of the workload group to delete.</span></span>  
  
2.  <span data-ttu-id="8c365-135">Avant d'émettre l'instruction `ALTER RESOURCE GOVERNOR RECONFIGURE`, vérifiez qu'il n'y a pas de demandes actives dans le groupe de charge de travail en cours de suppression.</span><span class="sxs-lookup"><span data-stu-id="8c365-135">Before you issue the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement, verify that there are no active requests in the workload group being deleted.</span></span> <span data-ttu-id="8c365-136">S'il existe des demandes actives, `ALTER RESOURCE GOVERNOR` échoue.</span><span class="sxs-lookup"><span data-stu-id="8c365-136">If there are active requests, `ALTER RESOURCE GOVERNOR` will fail.</span></span> <span data-ttu-id="8c365-137">Pour éviter ce problème, vous pouvez effectuer l'une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c365-137">To avoid this issue, you can take one of the following actions:</span></span>  
  
    -   <span data-ttu-id="8c365-138">Attendez jusqu'à ce que toutes les sessions du groupe de charges de travail soient déconnectées.</span><span class="sxs-lookup"><span data-stu-id="8c365-138">Wait until all the sessions from the workload group have disconnected.</span></span>  
  
    -   <span data-ttu-id="8c365-139">Arrêtez explicitement les sessions dans le groupe de charge de travail à l'aide de la commande `KILL`.</span><span class="sxs-lookup"><span data-stu-id="8c365-139">Explicitly stop sessions in the workload group by using the `KILL` command.</span></span>  
  
    -   <span data-ttu-id="8c365-140">Redémarrez le serveur.</span><span class="sxs-lookup"><span data-stu-id="8c365-140">Restart the server.</span></span> <span data-ttu-id="8c365-141">Le groupe de charge de travail ne sera pas recréé.</span><span class="sxs-lookup"><span data-stu-id="8c365-141">The workload group will not be re-created.</span></span>  
  
    -   <span data-ttu-id="8c365-142">Dans un scénario dans lequel vous avez émis l'instruction `DROP WORKLOAD GROUP` mais décidez que vous ne souhaitez pas arrêter explicitement des sessions pour appliquer la modification, vous pouvez recréer le groupe en utilisant le nom qu'il portait avant l'émission de l'instruction DROP, puis déplacer le groupe dans le pool de ressources d'origine.</span><span class="sxs-lookup"><span data-stu-id="8c365-142">In a scenario in which you have issued the `DROP WORKLOAD GROUP` statement but decide that you do not want to explicitly stop sessions to apply the change, you can re-create the group by using the same name that it had before you issued the DROP statement, and then move the group to the original resource pool.</span></span>  
  
3.  <span data-ttu-id="8c365-143">Exécutez l' `ALTER RESOURCE GOVERNOR RECONFIGURE` instruction.</span><span class="sxs-lookup"><span data-stu-id="8c365-143">Run the `ALTER RESOURCE GOVERNOR RECONFIGURE` statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="8c365-144">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8c365-144">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="8c365-145">L'exemple suivant supprime un groupe de charge de travail nommé `groupAdhoc`.</span><span class="sxs-lookup"><span data-stu-id="8c365-145">The following example drops a workload group named `groupAdhoc`.</span></span>  
  
```  
DROP WORKLOAD GROUP groupAdhoc;  
GO  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c365-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c365-146">See Also</span></span>  
 <span data-ttu-id="8c365-147">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="8c365-147">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="8c365-148">[Créer un pool de ressources](create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="8c365-148">[Create a Resource Pool](create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="8c365-149">[Créer un groupe de charge de travail](create-a-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="8c365-149">[Create a Workload Group](create-a-workload-group.md) </span></span>  
 <span data-ttu-id="8c365-150">[Supprimer un pool de ressources](delete-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="8c365-150">[Delete a Resource Pool](delete-a-resource-pool.md) </span></span>  
 <span data-ttu-id="8c365-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8c365-151">[DROP WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="8c365-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8c365-152">[DROP RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-resource-pool-transact-sql) </span></span>  
 [<span data-ttu-id="8c365-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8c365-153">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
