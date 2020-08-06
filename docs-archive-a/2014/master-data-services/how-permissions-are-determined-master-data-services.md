---
title: Mode de détermination des autorisations (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], determining permissions
ms.assetid: 1dc0b43a-d023-4e7d-b027-8b1459fd058c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3ea3306b772224bc8602659c7e17e8dc1634f0d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611133"
---
# <a name="how-permissions-are-determined-master-data-services"></a><span data-ttu-id="0a0f7-102">Mode de détermination des autorisations (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0a0f7-102">How Permissions Are Determined (Master Data Services)</span></span>
  <span data-ttu-id="0a0f7-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], la méthode la plus simple pour configurer la sécurité est d'affecter des autorisations d'objet de modèle à un groupe dont l'utilisateur est membre.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], the simplest way to configure security is to assign model object permissions to a group that the user is a member of.</span></span>

 <span data-ttu-id="0a0f7-104">La sécurité devient plus complexe lorsque :</span><span class="sxs-lookup"><span data-stu-id="0a0f7-104">Security becomes more complex when:</span></span>

-   <span data-ttu-id="0a0f7-105">sont attribués à la fois des autorisations d'objet de modèle et des autorisations des membres de la hiérarchie ;</span><span class="sxs-lookup"><span data-stu-id="0a0f7-105">Both model object and hierarchy member permissions are assigned.</span></span>

-   <span data-ttu-id="0a0f7-106">l'utilisateur appartient à des groupes et l'autorisation est attribuée à la fois à l'utilisateur et aux groupes ;</span><span class="sxs-lookup"><span data-stu-id="0a0f7-106">The user belongs to groups and permission is assigned to both the user and groups.</span></span>

-   <span data-ttu-id="0a0f7-107">l'utilisateur appartient à des groupes et l'autorisation est attribuée à plusieurs groupes.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-107">The user belongs to groups and permission is assigned to multiple groups.</span></span>

## <a name="permissions-assigned-to-a-single-group-or-user"></a><span data-ttu-id="0a0f7-108">Autorisations attribuées à un seul groupe ou utilisateur</span><span class="sxs-lookup"><span data-stu-id="0a0f7-108">Permissions assigned to a single group or user</span></span>
 <span data-ttu-id="0a0f7-109">Si vous attribuez des autorisations à un seul groupe ou utilisateur, les autorisations sont déterminées selon le flux de travail suivant.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-109">If you assign permissions to a single group or user, permissions are determined based on the following workflow.</span></span>

 <span data-ttu-id="0a0f7-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span><span class="sxs-lookup"><span data-stu-id="0a0f7-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span></span>

### <a name="step-1-effective-attribute-permissions-are-determined"></a><span data-ttu-id="0a0f7-111">Étape 1 : les autorisations d'attribut effectives sont déterminées.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-111">Step 1: Effective attribute permissions are determined.</span></span>
 <span data-ttu-id="0a0f7-112">La liste suivante décrit comment sont déterminées les autorisations d'attribut effectives :</span><span class="sxs-lookup"><span data-stu-id="0a0f7-112">The following list describes how effective attribute permissions are determined:</span></span>

-   <span data-ttu-id="0a0f7-113">Les autorisations attribuées aux objets de modèle déterminent les attributs auxquels un utilisateur peut accéder.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-113">Permissions assigned to model objects determine which attributes a user can access.</span></span>

-   <span data-ttu-id="0a0f7-114">Tous les objets de modèle héritent automatiquement de l'autorisation de l'objet le plus proche à un niveau supérieur dans la structure du modèle.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-114">All model objects automatically inherit permission from the closest object at a higher level in the model structure.</span></span>

-   <span data-ttu-id="0a0f7-115">Tout objet situé au même niveau que l'entité est refusé implicitement.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-115">Any objects at the same level as the entity are implicitly denied.</span></span>

-   <span data-ttu-id="0a0f7-116">Tout objet situé à un niveau supérieur obtient un accès de navigation.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-116">Any objects at a higher level are given navigational access.</span></span> <span data-ttu-id="0a0f7-117">Pour plus d’informations sur l’accès de navigation, consultez [&#40;de l’accès de navigation Master Data Services&#41;](navigational-access-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0a0f7-117">For more information about navigational access, see [Navigational Access &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span></span>

 <span data-ttu-id="0a0f7-118">Dans cet exemple, l’autorisation **en lecture seule** est assignée à une entité et cette autorisation est héritée par son attribut, qui se trouve à un niveau inférieur dans la structure du modèle.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-118">In this example, **Read-only** permission is assigned to an entity and that permission is inherited by its attribute, which is at a lower level in the model structure.</span></span> <span data-ttu-id="0a0f7-119">Le modèle fournit un accès de navigation à cette entité et à son attribut.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-119">The model provides navigational access to this entity and its attribute.</span></span> <span data-ttu-id="0a0f7-120">L'autre entité dans le modèle ne dispose d'aucune autorisation explicite attribuée et n'hérite d'aucune autorisation, donc elle est refusée implicitement.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-120">The other entity in the model has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="0a0f7-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="0a0f7-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>

### <a name="step-2-if-hierarchy-member-permissions-are-assigned-effective-member-permissions-are-determined"></a><span data-ttu-id="0a0f7-122">Étape 2 : si les autorisations des membres de la hiérarchie sont attribuées, les autorisations de membre effectives sont déterminées.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-122">Step 2: If hierarchy member permissions are assigned, effective member permissions are determined.</span></span>
 <span data-ttu-id="0a0f7-123">La liste suivante explique comment les autorisations des membres de la hiérarchie effectives sont déterminées :</span><span class="sxs-lookup"><span data-stu-id="0a0f7-123">The following list describes how effective hierarchy member permissions are determined:</span></span>

-   <span data-ttu-id="0a0f7-124">Les autorisations attribuées aux nœuds de la hiérarchie déterminent les membres auxquels un utilisateur peut accéder.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-124">Permissions assigned to hierarchy nodes determine which members a user can access.</span></span>

-   <span data-ttu-id="0a0f7-125">Tous les nœuds dans une hiérarchie héritent automatiquement de l'autorisation de l'objet le plus proche à un niveau supérieur dans la structure de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-125">All nodes in a hierarchy automatically inherit permission from the closest object at a higher level in the hierarchy structure.</span></span>

-   <span data-ttu-id="0a0f7-126">Tout nœud situé au même niveau est refusé implicitement.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-126">Any nodes at the same level are implicitly denied.</span></span>

-   <span data-ttu-id="0a0f7-127">Tout nœud situé aux niveaux supérieurs auquel aucune autorisation n'est attribuée est refusé implicitement.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-127">Any nodes at higher levels that do not have permissions assigned are implicitly denied.</span></span>

 <span data-ttu-id="0a0f7-128">Dans cet exemple, l’autorisation **lecture seule** est affectée à un nœud de la hiérarchie et cette autorisation est héritée par un nœud à un niveau inférieur dans la structure de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-128">In this example, **Read-only** permission is assigned to one node of the hierarchy and that permission is inherited by a node at a lower level in the hierarchy structure.</span></span> <span data-ttu-id="0a0f7-129">La racine n'a aucune autorisation attribuée, donc elle est refusée implicitement.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-129">The root has no permission assigned, so it is implicitly denied.</span></span> <span data-ttu-id="0a0f7-130">L'autre nœud dans la structure de hiérarchie ne dispose d'aucune autorisation explicite attribuée et n'hérite d'aucune autorisation, donc il est refusé implicitement.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-130">The other node in the hierarchy structure has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="0a0f7-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="0a0f7-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span></span>

### <a name="step-3-the-intersection-of-attribute-and-member-permissions-is-determined"></a><span data-ttu-id="0a0f7-132">Étape 3 : l'intersection des autorisations d'attribut et de membre est déterminée.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-132">Step 3: The intersection of attribute and member permissions is determined.</span></span>
 <span data-ttu-id="0a0f7-133">Si les autorisations d'attribut effectives sont différentes des autorisations de membre effectives, les autorisations doivent être déterminées pour chaque valeur d'attribut individuelle.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-133">If the effective attribute permissions are different than the effective member permissions, permissions must be determined for each individual attribute value.</span></span> <span data-ttu-id="0a0f7-134">Pour plus d’informations, consultez [Chevauchement des autorisations de modèle et de membre &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0a0f7-134">For more information, see [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span></span>

## <a name="permissions-assigned-to-multiple-groups"></a><span data-ttu-id="0a0f7-135">Autorisations attribuées à plusieurs groupes</span><span class="sxs-lookup"><span data-stu-id="0a0f7-135">Permissions assigned to multiple groups</span></span>
 <span data-ttu-id="0a0f7-136">Si un utilisateur appartient à un ou plusieurs groupes et que les autorisations sont attribuées à la fois à l'utilisateur et aux groupes, le flux de travail devient plus complexe.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-136">If a user belongs to one or more groups and permissions are assigned to both the user and the groups, the workflow becomes more complex.</span></span>

 <span data-ttu-id="0a0f7-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span><span class="sxs-lookup"><span data-stu-id="0a0f7-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span></span>

 <span data-ttu-id="0a0f7-138">Dans ce cas, le chevauchement des autorisations de l'utilisateur et du groupe doit être résolu avant que les autorisations de l'objet de modèle et des membres de la hiérarchie puissent être comparées.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-138">In this case, overlapping user and group permissions must be resolved before model object and hierarchy member permissions can be compared.</span></span> <span data-ttu-id="0a0f7-139">Pour plus d’informations, consultez [Chevauchement des autorisations d’accès &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0a0f7-139">For more information, see [Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0a0f7-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a0f7-140">See Also</span></span>
 <span data-ttu-id="0a0f7-141">Le [chevauchement des autorisations d’accès &#40;d’utilisateurs et de groupes Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) le [chevauchement des autorisations de modèle et de membre &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="0a0f7-141">[Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span></span>


