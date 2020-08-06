---
title: Chevauchement des autorisations des utilisateurs et des groupes (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services], resolving permissions
- permissions [Master Data Services], user and group overlaps
- groups [Master Data Services], resolving permissions
ms.assetid: 31c3cf7d-17d4-4474-b6a7-ffcb9fc45b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7044bf6260170cbc598719ec204ddb6f861f6301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698358"
---
# <a name="overlapping-user-and-group-permissions-master-data-services"></a><span data-ttu-id="ff832-102">Chevauchement des autorisations d'accès (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ff832-102">Overlapping User and Group Permissions (Master Data Services)</span></span>
  <span data-ttu-id="ff832-103">Les autorisations d'un utilisateur sont basées sur les :</span><span class="sxs-lookup"><span data-stu-id="ff832-103">A user's permissions are based on:</span></span>  
  
-   <span data-ttu-id="ff832-104">autorisations de l'appartenance aux groupes ;</span><span class="sxs-lookup"><span data-stu-id="ff832-104">Permissions from group memberships.</span></span>  
  
-   <span data-ttu-id="ff832-105">autorisations affectées explicitement à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ff832-105">Permissions assigned explicitly to the user.</span></span>  
  
 <span data-ttu-id="ff832-106">Si un utilisateur est un membre de plusieurs groupes, et que ces groupes ont accès à Master Data Manager, les règles suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="ff832-106">If a user is a member of multiple groups, and those groups have access to Master Data Manager, the following rules apply:</span></span>  
  
-   <span data-ttu-id="ff832-107">**Refuser** remplace toutes les autres autorisations.</span><span class="sxs-lookup"><span data-stu-id="ff832-107">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="ff832-108">**Met à jour** les remplacements **en lecture seule**.</span><span class="sxs-lookup"><span data-stu-id="ff832-108">**Update** overrides **Read-only**.</span></span>  
  
 <span data-ttu-id="ff832-109">Ces règles s'appliquent à la fois à l'onglet **Modèles** et à l'onglet **Membres de hiérarchie** .</span><span class="sxs-lookup"><span data-stu-id="ff832-109">These rules apply to both the **Models** and **Hierarchy Members** tabs.</span></span> <span data-ttu-id="ff832-110">Les autorisations sont résolues pour chaque onglet, puis combinées.</span><span class="sxs-lookup"><span data-stu-id="ff832-110">Permissions are resolved for each tab and then combined.</span></span> <span data-ttu-id="ff832-111">Pour plus d’informations, consultez [Mode de détermination des autorisations &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ff832-111">For more information, see [How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff832-112">Vous pouvez afficher la résolution du chevauchement des autorisations d'accès dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ff832-112">You can view the resolution of user and group overlapping permissions in the user interface.</span></span> <span data-ttu-id="ff832-113">Les onglets **Modèles** et **Membres de hiérarchie** ont tous deux une liste déroulante dans laquelle vous pouvez sélectionner **Effectives** pour afficher les autorisations effectives.</span><span class="sxs-lookup"><span data-stu-id="ff832-113">Both the **Models** and **Hierarchy Members** tab have a drop-down list from which you can choose **Effective** to view effective permissions.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="ff832-114">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="ff832-114">Example 1</span></span>  
 <span data-ttu-id="ff832-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span><span class="sxs-lookup"><span data-stu-id="ff832-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span></span>  
  
 <span data-ttu-id="ff832-116">L'utilisateur appartient au Groupe 1 et au Groupe 2.</span><span class="sxs-lookup"><span data-stu-id="ff832-116">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="ff832-117">L’utilisateur a l’autorisation **lecture seule** sur l’entité Product.</span><span class="sxs-lookup"><span data-stu-id="ff832-117">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="ff832-118">Groupe 1 a l'autorisation **Mise à jour** sur l'entité Product.</span><span class="sxs-lookup"><span data-stu-id="ff832-118">Group 1 has **Update** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="ff832-119">Le groupe 2 a l’autorisation **lecture seule** sur l’entité Product.</span><span class="sxs-lookup"><span data-stu-id="ff832-119">Group 2 has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="ff832-120">Résultat : l'autorisation effective de l'utilisateur est **Mise à jour** sur l'entité Product.</span><span class="sxs-lookup"><span data-stu-id="ff832-120">Result: The user's effective permission is **Update** to the Product entity.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="ff832-121">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="ff832-121">Example 2</span></span>  
 <span data-ttu-id="ff832-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span><span class="sxs-lookup"><span data-stu-id="ff832-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span></span>  
  
 <span data-ttu-id="ff832-123">L'utilisateur appartient au Groupe 1 et au Groupe 2.</span><span class="sxs-lookup"><span data-stu-id="ff832-123">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="ff832-124">L’utilisateur a l’autorisation **lecture seule** sur l’entité Product.</span><span class="sxs-lookup"><span data-stu-id="ff832-124">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="ff832-125">Groupe 1 a l'autorisation **Mise à jour** sur l'entité Product.</span><span class="sxs-lookup"><span data-stu-id="ff832-125">Group 1 has **Update** permission to Product entity.</span></span>  
  
 <span data-ttu-id="ff832-126">Groupe 2 a l'autorisation **Refuser** sur l'entité Product.</span><span class="sxs-lookup"><span data-stu-id="ff832-126">Group 2 has **Deny** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="ff832-127">Résultat : l'autorisation effective de l'utilisateur est **Refuser** sur l'entité Product.</span><span class="sxs-lookup"><span data-stu-id="ff832-127">Result: The user's effective permission is **Deny** to the Product entity.</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="ff832-128">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="ff832-128">Example 3</span></span>  
 <span data-ttu-id="ff832-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span><span class="sxs-lookup"><span data-stu-id="ff832-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span></span>  
  
 <span data-ttu-id="ff832-130">L'utilisateur appartient au Groupe 1 et au Groupe 2.</span><span class="sxs-lookup"><span data-stu-id="ff832-130">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="ff832-131">L'utilisateur a l'autorisation **Mise à jour** sur un groupe de membres dans un nœud de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="ff832-131">The user has **Update** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="ff832-132">Le groupe 1 a l’autorisation **lecture seule** sur un groupe de membres dans un nœud de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="ff832-132">Group 1 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="ff832-133">Le groupe 2 a l’autorisation **lecture seule** sur un groupe de membres dans un nœud de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="ff832-133">Group 2 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="ff832-134">Résultat : l'autorisation effective de l'utilisateur est **Mise à jour** sur les membres.</span><span class="sxs-lookup"><span data-stu-id="ff832-134">Result: The user's effective permission is **Update** to the members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff832-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff832-135">See Also</span></span>  
 <span data-ttu-id="ff832-136">[Mode de détermination des autorisations &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ff832-136">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="ff832-137">Chevauchement des autorisations de modèle et de membre &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ff832-137">Overlapping Model and Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)  
  
  
