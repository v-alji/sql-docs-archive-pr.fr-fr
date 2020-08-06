---
title: Groupes d’attributs (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services]
- attribute groups [Master Data Services], about attribute groups
ms.assetid: 648b3d0b-e15a-45f9-8292-3a54a072e62c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 390b402489799639e66a44992da1e20b0d0c1bbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610717"
---
# <a name="attribute-groups-master-data-services"></a><span data-ttu-id="7a40b-102">Groupes d'attributs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7a40b-102">Attribute Groups (Master Data Services)</span></span>
  <span data-ttu-id="7a40b-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], les groupes d’attributs permettent d’organiser les attributs dans une entité.</span><span class="sxs-lookup"><span data-stu-id="7a40b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], attribute groups help organize attributes in an entity.</span></span> <span data-ttu-id="7a40b-104">Lorsqu'une entité comporte un grand nombre d'attributs, les groupes d'attributs améliorent la manière dont elle est affichée dans l'application Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a40b-104">When an entity has lots of attributes, attribute groups improve the way an entity is displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
## <a name="how-attribute-groups-change-the-display"></a><span data-ttu-id="7a40b-105">Comment les groupes d'attributs modifient l'affichage</span><span class="sxs-lookup"><span data-stu-id="7a40b-105">How Attribute Groups Change the Display</span></span>  
 <span data-ttu-id="7a40b-106">Les groupes d’attributs sont affichés sous forme d’onglets au-dessus de la grille dans le domaine fonctionnel \*\*Explorateur[!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] de \*\*.</span><span class="sxs-lookup"><span data-stu-id="7a40b-106">Attribute groups are displayed as tabs above the grid in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="7a40b-107">Lorsqu’une entité a un grand nombre d’attributs et vous la consultez dans une grille dans l’ **Explorateur**, vous devez faire défiler le curseur à droite pour consulter tous les attributs.</span><span class="sxs-lookup"><span data-stu-id="7a40b-107">When an entity has a large number of attributes and you view that entity in a grid in **Explorer**, you must scroll to the right to view all of the attributes.</span></span> <span data-ttu-id="7a40b-108">Pour éviter ce défilement, vous pouvez créer des groupes d'attributs.</span><span class="sxs-lookup"><span data-stu-id="7a40b-108">To prevent this scrolling, you can create attribute groups.</span></span>  
  
-   <span data-ttu-id="7a40b-109">Les groupes d'attributs incluent toujours les attributs Name et Code.</span><span class="sxs-lookup"><span data-stu-id="7a40b-109">Attribute groups always include the Name and Code attributes.</span></span>  
  
-   <span data-ttu-id="7a40b-110">Chaque attribut d'une entité peut appartenir à un ou plusieurs groupes d'attributs.</span><span class="sxs-lookup"><span data-stu-id="7a40b-110">Each attribute for an entity can belong to one or more attribute groups.</span></span>  
  
-   <span data-ttu-id="7a40b-111">Tous les attributs sont inclus automatiquement sous l’onglet **Tous les attributs** dans **l’Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="7a40b-111">All attributes are automatically included on the **All Attributes** tab in **Explorer**.</span></span>  
  
-   <span data-ttu-id="7a40b-112">Il n’existe aucun moyen de masquer l’onglet **Tous les attributs** .</span><span class="sxs-lookup"><span data-stu-id="7a40b-112">There is no way to hide the **All Attributes** tab.</span></span>  
  
 <span data-ttu-id="7a40b-113">Les groupes d’attributs sont administrés dans la zone fonctionnelle **Administration de système** de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a40b-113">Attribute groups are administered in the **System Administration** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="show-or-hide-attribute-groups"></a><span data-ttu-id="7a40b-114">Afficher ou masquer les groupes d'attributs</span><span class="sxs-lookup"><span data-stu-id="7a40b-114">Show or Hide Attribute Groups</span></span>  
 <span data-ttu-id="7a40b-115">Lorsque vous créez un groupe d'attributs, il est automatiquement masqué pour tous les utilisateurs, à l'exception de son créateur.</span><span class="sxs-lookup"><span data-stu-id="7a40b-115">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="7a40b-116">Pour plus d’informations sur le fait de rendre visible le groupe, consultez [Rendre un groupe d’attributs visible pour les utilisateurs &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7a40b-116">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
 <span data-ttu-id="7a40b-117">Si vous souhaitez masquer un attribut spécifique dans un groupe, vous pouvez lui affecter une autorisation **Refuser** .</span><span class="sxs-lookup"><span data-stu-id="7a40b-117">If you want to hide a specific attribute within a group, you can assign **Deny** permission to the attribute.</span></span> <span data-ttu-id="7a40b-118">Pour plus d’informations, consultez [Autorisations de feuille &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) ou [Autorisations consolidées &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7a40b-118">For more information, see [Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) or [Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="7a40b-119">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="7a40b-119">Related Tasks</span></span>  
  
|<span data-ttu-id="7a40b-120">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="7a40b-120">Task Description</span></span>|<span data-ttu-id="7a40b-121">Rubrique</span><span class="sxs-lookup"><span data-stu-id="7a40b-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="7a40b-122">Créer un groupe d'attributs et y ajouter des attributs.</span><span class="sxs-lookup"><span data-stu-id="7a40b-122">Create a new attribute group and add attributes to it.</span></span>|[<span data-ttu-id="7a40b-123">Créer un groupe d’attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a40b-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)|  
|<span data-ttu-id="7a40b-124">Rendre un groupe d'attributs visible pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7a40b-124">Make an attribute group visible to users.</span></span>|[<span data-ttu-id="7a40b-125">Rendre un groupe d’attributs visible pour les utilisateurs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a40b-125">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)|  
|<span data-ttu-id="7a40b-126">Modifier le nom d'un groupe d'attributs existant.</span><span class="sxs-lookup"><span data-stu-id="7a40b-126">Change the name of an existing attribute group.</span></span>|[<span data-ttu-id="7a40b-127">Modifier le nom d’un groupe d’attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a40b-127">Change an Attribute Group Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md)|  
|<span data-ttu-id="7a40b-128">Supprimer un groupe d'attributs existant.</span><span class="sxs-lookup"><span data-stu-id="7a40b-128">Delete an existing attribute group.</span></span>|[<span data-ttu-id="7a40b-129">Supprimer un groupe d’attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a40b-129">Delete an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="7a40b-130">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="7a40b-130">Related Content</span></span>  
  
-   [<span data-ttu-id="7a40b-131">Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7a40b-131">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
