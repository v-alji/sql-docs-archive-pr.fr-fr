---
title: Chevauchement des autorisations de modèle et de membre (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], effective permissions
- permissions [Master Data Services], model and member overlaps
- members [Master Data Services], effective permissions
ms.assetid: 9fd7a555-43bf-4796-a8b6-1ca63a291216
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ec5f4019f25a777e4c70433bd9a7e72fca2277e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601532"
---
# <a name="overlapping-model-and-member-permissions-master-data-services"></a><span data-ttu-id="8451e-102">Chevauchement des autorisations de modèle et de membre (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8451e-102">Overlapping Model and Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="8451e-103">Une autorisation attribuée à un membre et une autorisation attribuée à un objet de modèle peuvent se chevaucher.</span><span class="sxs-lookup"><span data-stu-id="8451e-103">Permission assigned to a member can overlap with permission assigned to a model object.</span></span> <span data-ttu-id="8451e-104">Lorsque des chevauchements se produisent, l'autorisation la plus restrictive entre en vigueur.</span><span class="sxs-lookup"><span data-stu-id="8451e-104">When overlaps occur, the more restrictive permission takes effect.</span></span>  
  
 <span data-ttu-id="8451e-105">Si un membre a une autorisation qui est différente de celle de son objet de modèle correspondant, les règles suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="8451e-105">If a member has permission that is different than its corresponding model object, the following rules apply:</span></span>  
  
-   <span data-ttu-id="8451e-106">**Refuser** remplace toutes les autres autorisations.</span><span class="sxs-lookup"><span data-stu-id="8451e-106">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="8451e-107">La **lecture** seule remplace la **mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="8451e-107">**Read-only** overrides **Update**.</span></span>  
  
 <span data-ttu-id="8451e-108">L'image suivante montre les autorisations appliquées sur une valeur d'attribut individuelle lorsque les autorisations d'attribut sont différentes des autorisations de membre.</span><span class="sxs-lookup"><span data-stu-id="8451e-108">The following image shows which permissions take effect on an individual attribute value when attribute permissions are different than member permissions.</span></span>  
  
 <span data-ttu-id="8451e-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span><span class="sxs-lookup"><span data-stu-id="8451e-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="8451e-110">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="8451e-110">Example 1</span></span>  
 <span data-ttu-id="8451e-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span><span class="sxs-lookup"><span data-stu-id="8451e-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span></span>  
  
 <span data-ttu-id="8451e-112">Sous l'onglet **Modèles** , l'entité Product a l'autorisation **Mise à jour** attribuée.</span><span class="sxs-lookup"><span data-stu-id="8451e-112">On the **Models** tab, the Product entity has **Update** permission assigned.</span></span> <span data-ttu-id="8451e-113">Tous les attributs dans l'entité héritent de cette autorisation.</span><span class="sxs-lookup"><span data-stu-id="8451e-113">All attributes in the entity inherit that permission.</span></span>  
  
 <span data-ttu-id="8451e-114">Sous l'onglet **Membres de hiérarchie** , le nœud de sous-catégorie Mountain Bikes dans une hiérarchie dérivée a l'autorisation **Mise à jour** attribuée.</span><span class="sxs-lookup"><span data-stu-id="8451e-114">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="8451e-115">Résultat : dans **Explorateur**, l'utilisateur a l'autorisation **Mise à jour** sur toutes les valeurs d'attribut de tous les membres qui se trouvent dans le nœud Mountain Bikes.</span><span class="sxs-lookup"><span data-stu-id="8451e-115">Result: In **Explorer**, the user has **Update** permission to all attribute values for all members in the Mountain Bikes node.</span></span> <span data-ttu-id="8451e-116">Tous les autres membres et attributs sont masqués.</span><span class="sxs-lookup"><span data-stu-id="8451e-116">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="8451e-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span><span class="sxs-lookup"><span data-stu-id="8451e-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="8451e-118">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="8451e-118">Example 2</span></span>  
 <span data-ttu-id="8451e-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span><span class="sxs-lookup"><span data-stu-id="8451e-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span></span>  
  
 <span data-ttu-id="8451e-120">Sous l'onglet **Modèles** , l'attribut Subcategory a l'autorisation **Mise à jour** attribuée.</span><span class="sxs-lookup"><span data-stu-id="8451e-120">On the **Models** tab, the Subcategory attribute has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="8451e-121">Sous l’onglet **membres de hiérarchie** , le nœud de sous-catégorie Mountain Bikes dans une hiérarchie dérivée est explicitement affecté à l’autorisation **lecture seule** .</span><span class="sxs-lookup"><span data-stu-id="8451e-121">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy is explicitly assigned **Read-only** permission.</span></span>  
  
 <span data-ttu-id="8451e-122">Résultat : dans l **'Explorateur**, l’utilisateur a l’autorisation **lecture seule** sur les valeurs d’attribut de sous-catégorie pour les membres du nœud Mountain Bikes.</span><span class="sxs-lookup"><span data-stu-id="8451e-122">Result: In **Explorer**, the user has **Read-only** permission to the Subcategory attribute values for the members in the Mountain Bikes node.</span></span> <span data-ttu-id="8451e-123">Tous les autres membres et attributs sont masqués.</span><span class="sxs-lookup"><span data-stu-id="8451e-123">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="8451e-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="8451e-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="8451e-125">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="8451e-125">Example 3</span></span>  
 <span data-ttu-id="8451e-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span><span class="sxs-lookup"><span data-stu-id="8451e-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span></span>  
  
 <span data-ttu-id="8451e-127">Sous l’onglet **modèles** , l’attribut sous-catégorie a **une autorisation en lecture seule** affectée.</span><span class="sxs-lookup"><span data-stu-id="8451e-127">On the **Models** tab, the Subcategory attribute has **Read-only** permission assigned.</span></span>  
  
 <span data-ttu-id="8451e-128">Sous l'onglet **Membres de hiérarchie** , le nœud de sous-catégorie Mountain Bikes dans une hiérarchie dérivée a l'autorisation **Mise à jour** attribuée explicitement.</span><span class="sxs-lookup"><span data-stu-id="8451e-128">On the **Hierarchy Members** tab, the Mountain Bikes subcategory in a derived hierarchy is explicitly assigned **Update** permission.</span></span>  
  
 <span data-ttu-id="8451e-129">Résultat : dans l **'Explorateur**, l’utilisateur a l’autorisation **lecture seule** sur les valeurs d’attribut.</span><span class="sxs-lookup"><span data-stu-id="8451e-129">Result: In **Explorer**, the user has **Read-only** permission to the attribute values.</span></span> <span data-ttu-id="8451e-130">Tous les autres membres et attributs sont masqués.</span><span class="sxs-lookup"><span data-stu-id="8451e-130">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="8451e-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="8451e-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8451e-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8451e-132">See Also</span></span>  
 <span data-ttu-id="8451e-133">[Mode de détermination des autorisations &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8451e-133">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="8451e-134">Chevauchement des autorisations d’accès &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8451e-134">Overlapping User and Group Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md)  
  
  
