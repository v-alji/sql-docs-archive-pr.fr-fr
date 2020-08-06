---
title: Afficher les propriétés de Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.rg.properties.f1
helpviewer_keywords:
- Resource Governor, properties
ms.assetid: de3510df-f792-4a9d-80fa-f198fd36cdc8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cd7af8f4f8eb3cd0531bc907011846f73f94f6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603918"
---
# <a name="view-resource-governor-properties"></a><span data-ttu-id="ac6cd-102">Afficher les propriétés du gouverneur de ressources</span><span class="sxs-lookup"><span data-stu-id="ac6cd-102">View Resource Governor Properties</span></span>
  <span data-ttu-id="ac6cd-103">Vous pouvez créer ou configurer des entités de Resource Governor, telles que des pools de ressources et des groupes de charge de travail, en utilisant la page Propriétés de Resource Governor dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac6cd-103">You can create or configure Resource Governor entities, such as resource pools and workload groups, by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="ac6cd-104">**Avant de commencer :**  [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="ac6cd-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="ac6cd-105">**Pour afficher les propriétés du gouverneur de ressources, avec :**  [Page Propriétés du gouverneur de ressources](#ViewRGProp)</span><span class="sxs-lookup"><span data-stu-id="ac6cd-105">**To view Resource Governor properties, using:**  [Resource Governor Properties page](#ViewRGProp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ac6cd-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ac6cd-106">Before You Begin</span></span>  
 <span data-ttu-id="ac6cd-107">Outre la consultation des propriétés des entités de Resource Governor, vous pouvez effectuer plusieurs tâches de configuration à l'aide de la page **ropriétés de Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="ac6cd-107">In addition to viewing the properties of Resource Governor entities, you can perform several configuration tasks using the **Resource Governor Properties** page.</span></span> <span data-ttu-id="ac6cd-108">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ac6cd-108">For more information, see these topics:</span></span>  
  
-   [<span data-ttu-id="ac6cd-109">Activer Resource Governor</span><span class="sxs-lookup"><span data-stu-id="ac6cd-109">Enable Resource Governor</span></span>](enable-resource-governor.md)  
  
-   [<span data-ttu-id="ac6cd-110">Désactiver Resource Governor</span><span class="sxs-lookup"><span data-stu-id="ac6cd-110">Disable Resource Governor</span></span>](disable-resource-governor.md)  
  
-   [<span data-ttu-id="ac6cd-111">Créer un pool de ressources</span><span class="sxs-lookup"><span data-stu-id="ac6cd-111">Create a Resource Pool</span></span>](create-a-resource-pool.md)  
  
-   [<span data-ttu-id="ac6cd-112">Créer un groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="ac6cd-112">Create a Workload Group</span></span>](create-a-workload-group.md)  
  
-   [<span data-ttu-id="ac6cd-113">Modifier les paramètres de pool de ressources</span><span class="sxs-lookup"><span data-stu-id="ac6cd-113">Change Resource Pool Settings</span></span>](change-resource-pool-settings.md)  
  
-   [<span data-ttu-id="ac6cd-114">Modifier les paramètres de groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="ac6cd-114">Change Workload Group Settings</span></span>](change-workload-group-settings.md)  
  
-   [<span data-ttu-id="ac6cd-115">Déplacer un groupe de charge de travail</span><span class="sxs-lookup"><span data-stu-id="ac6cd-115">Move a Workload Group</span></span>](move-a-workload-group.md)  
  
 <span data-ttu-id="ac6cd-116">Lorsque vous cliquez sur **OK** après avoir ajouté, supprimé ou déplacé un groupe de charge de travail ou un pool de ressources, l'instruction ALTER RESOURCE GOVERNOR RECONFIGURE s'exécute.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-116">When you click **OK** after adding, deleting, or moving a workload group or resource pool, the ALTER RESOURCE GOVERNOR RECONFIGURE statement is executed.</span></span>  
  
 <span data-ttu-id="ac6cd-117">Si l'opération de création ou de reconfiguration du pool de ressources ou du groupe de charge de travail échoue, un message d'erreur récapitulatif apparaît sous le titre de la page de propriétés.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-117">If the create or reconfigure operation for the resource pool or workload group fails, a summary error message appears below the title of the property page.</span></span> <span data-ttu-id="ac6cd-118">Pour consulter le message d'erreur détaillé, cliquez sur la flèche vers le bas du message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-118">To see a detailed error message, click the down arrow on the error message.</span></span>  
  
 <span data-ttu-id="ac6cd-119">Vous pouvez déterminer s’il existe une configuration en attente en interrogeant la vue de gestion dynamique [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) pour obtenir l’état en cours d’is_configuration_pending.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-119">You can determine whether there is a configuration pending by querying the [sys.dm_resource_governor_configuration](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-configuration-transact-sql) dynamic management view to get the current status of is_configuration_pending.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ac6cd-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ac6cd-120">Permissions</span></span>  
 <span data-ttu-id="ac6cd-121">L'affichage des propriétés de Resource Governor nécessite l'autorisation VIEW SERVER STATER.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-121">Viewing resource governor properties requires VIEW SERVER STATER permission.</span></span> <span data-ttu-id="ac6cd-122">Les tâches de configuration de Resource Governor nécessitent l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-122">The resource governor configuration tasks require CONTROL SERVER permission.</span></span>  
  
##  <a name="view-the-resource-governor-properties-page"></a><a name="ViewRGProp"></a><span data-ttu-id="ac6cd-123">Afficher la page de propriétés Resource Governor</span><span class="sxs-lookup"><span data-stu-id="ac6cd-123">View the Resource Governor Properties Page</span></span>  
 <span data-ttu-id="ac6cd-124">**Pour afficher les propriétés de Resource Governor à l’aide de la page Propriétés de Resource Governor dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-124">**To view resource governor properties by using the Resource Governor Properties page in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="ac6cd-125">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l'Explorateur d'objets et développez de manière récursive le nœud **Gestion** jusqu'au **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="ac6cd-126">Cliquez avec le bouton droit sur **Resource Governor** , puis sélectionnez **Propriétés**afin d’ouvrir la page **Propriétés de Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="ac6cd-126">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="ac6cd-127">Pour obtenir les descriptions des champs de la page, consultez [Propriétés de Resource Governor](#RGProp).</span><span class="sxs-lookup"><span data-stu-id="ac6cd-127">For descriptions of the fields in the page, see [Resource Governor Properties](#RGProp).</span></span>  
  
4.  <span data-ttu-id="ac6cd-128">Cliquez sur **OK**pour enregistrer les éventuelles modifications.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-128">To save any changes, click **OK**.</span></span>  
  
##  <a name="resource-governor-properties"></a><a name="RGProp"></a><span data-ttu-id="ac6cd-129">Propriétés de la Resource Governor</span><span class="sxs-lookup"><span data-stu-id="ac6cd-129">Resource Governor Properties</span></span>  
 <span data-ttu-id="ac6cd-130">**Nom de la fonction classifieur**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-130">**Classifier function name**</span></span>  
 <span data-ttu-id="ac6cd-131">Spécifiez la fonction classifieur en la sélectionnant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-131">Specify the classifier function by selecting from the list.</span></span>  
  
 <span data-ttu-id="ac6cd-132">**Activer Resource Governor**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-132">**Enable Resource Governor**</span></span>  
 <span data-ttu-id="ac6cd-133">Activez ou désactivez Resource Governor en activant ou désactivant la case à cocher.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-133">Enable or disable Resource Governor by selecting or clearing the check box.</span></span>  
  
 <span data-ttu-id="ac6cd-134">**Pools de ressources**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-134">**Resource pools**</span></span>  
 <span data-ttu-id="ac6cd-135">Créez ou modifiez la configuration des pools de ressources à l'aide de la grille fournie.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-135">Create or change resource pool configuration by using the grid that is provided.</span></span> <span data-ttu-id="ac6cd-136">Cette grille est remplie à l'aide des informations des pools internes et par défaut prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-136">This grid is populated with information for the predefined internal and default pools.</span></span> <span data-ttu-id="ac6cd-137">Sélectionnez un pool à utiliser en cliquant sur la première colonne de la ligne du pool.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-137">Select a pool to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="ac6cd-138">Pour créer un pool de ressources, cliquez sur la ligne comportant le préfixe **&#42;** (astérisque).</span><span class="sxs-lookup"><span data-stu-id="ac6cd-138">To create a new resource pool, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="ac6cd-139">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-139">**Name**</span></span>  
 <span data-ttu-id="ac6cd-140">Spécifiez le nom du pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-140">Specify the name of the resource pool.</span></span>  
  
 <span data-ttu-id="ac6cd-141">**% processeur minimal**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-141">**Minimum CPU %**</span></span>  
 <span data-ttu-id="ac6cd-142">Spécifiez la bande passante de l'UC moyenne garantie pour toutes les demandes dans le pool de ressources en cas de contention de l'UC.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-142">Specify the guaranteed average CPU bandwidth for all requests in the resource pool when there is CPU contention.</span></span> <span data-ttu-id="ac6cd-143">La plage est comprise entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-143">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="ac6cd-144">**% processeur maximal**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-144">**Maximum CPU %**</span></span>  
 <span data-ttu-id="ac6cd-145">Spécifiez la bande passante de l'UC moyenne maximale que toutes les demandes dans ce pool de ressources recevront en cas de contention de l'UC.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-145">Specify the maximum average CPU bandwidth that all requests in this resource pool will receive when there is CPU contention.</span></span> <span data-ttu-id="ac6cd-146">La plage est comprise entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-146">Range is 0 to 100.</span></span> <span data-ttu-id="ac6cd-147">La valeur par défaut est 100.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-147">The default setting is 100.</span></span>  
  
 <span data-ttu-id="ac6cd-148">**% mémoire minimal**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-148">**Minimum Memory %**</span></span>  
 <span data-ttu-id="ac6cd-149">Spécifiez la quantité de mémoire minimale réservée à ce pool de ressources qui ne peut pas être partagée avec d'autres pools de ressources.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-149">Specify the minimum amount of memory reserved for this resource pool that can not be shared with other resource pools.</span></span> <span data-ttu-id="ac6cd-150">La plage est comprise entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-150">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="ac6cd-151">**% mémoire maximal**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-151">**Maximum Memory %**</span></span>  
 <span data-ttu-id="ac6cd-152">Spécifiez la mémoire totale du serveur qui peut être utilisée par les demandes dans ce pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-152">Specify the total server memory that can be used by requests in this resource pool.</span></span> <span data-ttu-id="ac6cd-153">La plage est comprise entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-153">Range is 0 to 100.</span></span> <span data-ttu-id="ac6cd-154">La valeur par défaut est 100.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-154">The default setting is 100.</span></span>  
  
 <span data-ttu-id="ac6cd-155">Pour plus d’informations, consultez [Create RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac6cd-155">For more information, see [CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql).</span></span>  
  
 <span data-ttu-id="ac6cd-156">**Groupes de charge de travail pour le pool de ressources**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-156">**Workload groups for resource pool**</span></span>  
 <span data-ttu-id="ac6cd-157">Créez ou modifiez la configuration du groupe de charges de travail à l'aide de la grille fournie.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-157">Create or change the workload group configuration by using the grid that is provided.</span></span> <span data-ttu-id="ac6cd-158">Cette grille est remplie à l'aide des informations des groupes internes et par défaut prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-158">This grid is populated with information for the predefined internal and default groups.</span></span> <span data-ttu-id="ac6cd-159">Sélectionnez un groupe à utiliser en cliquant sur la première colonne de la ligne du pool.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-159">Select a group to work with by clicking the first column in the row for the pool.</span></span> <span data-ttu-id="ac6cd-160">Pour créer un groupe de charges de travail, cliquez sur la ligne comportant le préfixe **&#42;** (astérisque).</span><span class="sxs-lookup"><span data-stu-id="ac6cd-160">To create a new workload group, click the row that is prefixed by the asterisk (**&#42;**).</span></span>  
  
 <span data-ttu-id="ac6cd-161">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-161">**Name**</span></span>  
 <span data-ttu-id="ac6cd-162">Spécifiez le nom du groupe de charges de travail.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-162">Specify the name of the workload group.</span></span>  
  
 <span data-ttu-id="ac6cd-163">**Importance**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-163">**Importance**</span></span>  
 <span data-ttu-id="ac6cd-164">Spécifiez l'importance relative d'une demande dans le groupe de charges de travail.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-164">Specify the relative importance of a request in the workload group.</span></span> <span data-ttu-id="ac6cd-165">Les paramètres disponibles sont Faible, Moyenne et Haute.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-165">Available settings are Low, Medium, and High.</span></span>  
  
 <span data-ttu-id="ac6cd-166">**Demandes maximales**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-166">**Maximum Requests**</span></span>  
 <span data-ttu-id="ac6cd-167">Spécifiez le nombre maximal de demandes simultanées autorisées à s'exécuter dans le groupe de charges de travail.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-167">Specify the maximum number of simultaneous requests that are allowed to execute in the workload group.</span></span> <span data-ttu-id="ac6cd-168">Doit être égal à 0 ou un entier positif.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-168">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="ac6cd-169">**Temps processeur (s)**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-169">**CPU Time (sec)**</span></span>  
 <span data-ttu-id="ac6cd-170">Spécifiez la quantité de temps maximale de temps processeur qu'une demande peut utiliser.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-170">Specify the maximum amount of CPU time that a request can use.</span></span> <span data-ttu-id="ac6cd-171">Doit être égal à 0 ou un entier positif.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-171">Must be 0 or a positive integer.</span></span> <span data-ttu-id="ac6cd-172">Si 0, le temps est illimité.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-172">If 0, the time is unlimited.</span></span>  
  
 <span data-ttu-id="ac6cd-173">**% allocation mémoire**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-173">**Memory Grant %**</span></span>  
 <span data-ttu-id="ac6cd-174">Spécifiez la quantité de mémoire maximale qu'une demande unique peut prendre du pool.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-174">Specify the maximum amount of memory that a single request can take from the pool.</span></span> <span data-ttu-id="ac6cd-175">La plage est comprise entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-175">Range is 0 to 100.</span></span>  
  
 <span data-ttu-id="ac6cd-176">**Délai d'expiration de l'allocation (s)**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-176">**Grant Time-out (sec)**</span></span>  
 <span data-ttu-id="ac6cd-177">Spécifiez le délai maximal pendant lequel une requête peut attendre qu'une ressource devienne disponible avant d'échouer.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-177">Specify the maximum time that a query can wait for a resource to become available before the query fails.</span></span> <span data-ttu-id="ac6cd-178">Doit être égal à 0 ou un entier positif.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-178">Must be 0 or a positive integer.</span></span>  
  
 <span data-ttu-id="ac6cd-179">**Degré de parallélisme**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-179">**Degree of Parallelism**</span></span>  
 <span data-ttu-id="ac6cd-180">Spécifiez le degré maximal de parallélisme (DOP) pour les demandes parallèles.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-180">Specify the maximum degree of parallelism (DOP) for parallel requests.</span></span> <span data-ttu-id="ac6cd-181">La plage est comprise entre 0 et 64.</span><span class="sxs-lookup"><span data-stu-id="ac6cd-181">Range is 0 to 64.</span></span>  
  
 <span data-ttu-id="ac6cd-182">Pour plus d’informations, consultez [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac6cd-182">For more information, see [CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql).</span></span>  
  
## <a name="view-resource-governor-properties-by-using-transact-sql"></a><span data-ttu-id="ac6cd-183">Afficher les propriétés du gouverneur de ressources à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ac6cd-183">View Resource Governor Properties by Using Transact-SQL</span></span>  
 <span data-ttu-id="ac6cd-184">**Afficher les propriétés de Resource Governor à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ac6cd-184">**View resource governor properties by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="ac6cd-185">Pour afficher les définitions des entités de Resource Governor, utilisez les [Affichages catalogue de Resource Governor &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac6cd-185">To view the definitions of resource governor entities, use the [Resource Governor Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/resource-governor-catalog-views-transact-sql).</span></span>  
  
2.  <span data-ttu-id="ac6cd-186">Pour consulter la configuration actuelle des entités de Resource Governor, utilisez les [Vues de gestion dynamique liées à Resource Governor &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac6cd-186">To view the current configuration of resource governor entities, use the [Resource Governor Related Dynamic Management Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/resource-governor-related-dynamic-management-views-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac6cd-187">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac6cd-187">See Also</span></span>  
 <span data-ttu-id="ac6cd-188">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ac6cd-188">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="ac6cd-189">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="ac6cd-189">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="ac6cd-190">[Pool de ressources de Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="ac6cd-190">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="ac6cd-191">[Groupe de charge de travail de Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="ac6cd-191">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 [<span data-ttu-id="ac6cd-192">Fonction classifieur de Resource Governor</span><span class="sxs-lookup"><span data-stu-id="ac6cd-192">Resource Governor Classifier Function</span></span>](resource-governor-classifier-function.md)  
  
  
