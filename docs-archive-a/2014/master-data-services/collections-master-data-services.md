---
title: Collections (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services]
- collections [Master Data Services], about collections
ms.assetid: 5aa1d1e0-b4e5-4897-8e74-01dcf418df73
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce49c57aad5da52dabba32a0f3fb9b6f4f45b209
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699996"
---
# <a name="collections-master-data-services"></a><span data-ttu-id="ec0e6-102">Collections (services de données de référence)</span><span class="sxs-lookup"><span data-stu-id="ec0e6-102">Collections (Master Data Services)</span></span>
  <span data-ttu-id="ec0e6-103">Une collection est un groupe de membres feuille et de membres consolidés d'une entité unique.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-103">A collection is a group of leaf and consolidated members from a single entity.</span></span> <span data-ttu-id="ec0e6-104">Utilisez des collections lorsque vous n'avez pas besoin d'une hiérarchie complète et que vous souhaitez afficher des regroupements différents de vos membres pour la création de rapports ou l'analyse, ou lorsque vous devez créer une taxonomie.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-104">Use collections when you do not need a complete hierarchy and you want to view different groupings of members for reporting or analysis, or when you need to create a taxonomy.</span></span>  
  
## <a name="what-collections-contain"></a><span data-ttu-id="ec0e6-105">Contenu des collections</span><span class="sxs-lookup"><span data-stu-id="ec0e6-105">What Collections Contain</span></span>  
 <span data-ttu-id="ec0e6-106">Les collections ne limitent pas le nombre ou le type de membres que vous pouvez inclure, tant que les membres se trouvent dans la même entité.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-106">Collections do not limit the number or type of members you can include, as long as the members are within the same entity.</span></span> <span data-ttu-id="ec0e6-107">Une collection peut contenir des membres feuille et consolidés de plusieurs hiérarchies explicites obligatoires et non obligatoires.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-107">A collection can contain leaf and consolidated members from multiple mandatory and non-mandatory explicit hierarchies.</span></span>  
  
 <span data-ttu-id="ec0e6-108">Lorsque vous créez une collection, vous ne créez pas une structure hiérarchique ; vous créez une liste plate de membres.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-108">When you create a collection, you are not creating a hierarchical structure; you are creating a flat list of members.</span></span> <span data-ttu-id="ec0e6-109">Lorsque vous sélectionnez un nœud d'une hiérarchie et l'ajouter à la collection, le membre consolidé sélectionné est le seul membre ajouté à la collection.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-109">When you select a node from a hierarchy and add it to the collection, the consolidated member you selected is the only member added to the collection.</span></span>  
  
 <span data-ttu-id="ec0e6-110">Une collection peut également contenir d'autres collections.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-110">A collection can also contain other collections.</span></span> <span data-ttu-id="ec0e6-111">Vous pouvez utiliser des collections de collections pour créer des taxonomies.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-111">You can use collections of collections to create taxonomies.</span></span>  
  
 <span data-ttu-id="ec0e6-112">Lorsque vous créez une collection, vous apparaissez automatiquement comme propriétaire.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-112">When you create a collection you are automatically listed as the owner.</span></span> <span data-ttu-id="ec0e6-113">Si vous êtes administrateur, vous pouvez créer d'autres attributs pour votre collection si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-113">If you are an administrator, you can create other attributes for your collection as needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec0e6-114">Avant de pouvoir créer une collection, l'entité doit être activée pour les hiérarchies explicites.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-114">Before you can create a collection, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="ec0e6-115">Pour plus d’informations, consultez [activer une entité pour les hiérarchies explicites et les Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ec0e6-115">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
## <a name="subscription-views-for-collections"></a><span data-ttu-id="ec0e6-116">Vues d'abonnement pour les collections</span><span class="sxs-lookup"><span data-stu-id="ec0e6-116">Subscription Views for Collections</span></span>  
 <span data-ttu-id="ec0e6-117">Il existe deux types de vues d'abonnement qui affichent des collections.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-117">There are two types of subscription views that show collections.</span></span> <span data-ttu-id="ec0e6-118">Le format **Attributs de collection** affiche la liste des collections et des attributs associés aux collections (comme la description ou le propriétaire).</span><span class="sxs-lookup"><span data-stu-id="ec0e6-118">The **Collection attributes** format shows a list of collections and any attributes related to the collections (like description or owner).</span></span> <span data-ttu-id="ec0e6-119">Le format **Collections** affiche tous les membres de toutes les collections, ainsi que chaque poids et ordre de tri des membres.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-119">The **Collections** format shows all members in all collections, as well as each members weight and sort order.</span></span> <span data-ttu-id="ec0e6-120">Pour plus d’informations, consultez [exportation de données &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ec0e6-120">For more information, see [Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span></span>  
  
 <span data-ttu-id="ec0e6-121">Si vous définissez des valeurs de pondération pour des membres spécifiques d'une collection, ces valeurs sont disponibles dans les vues associées d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-121">If you set weight values for specific members in a collection, these values are available in related subscription views.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ec0e6-122">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ec0e6-122">Related Tasks</span></span>  
  
|<span data-ttu-id="ec0e6-123">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="ec0e6-123">Task Description</span></span>|<span data-ttu-id="ec0e6-124">Rubrique</span><span class="sxs-lookup"><span data-stu-id="ec0e6-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="ec0e6-125">Activer une entité pour les hiérarchies explicites et les collections.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-125">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="ec0e6-126">Activez une entité pour les hiérarchies explicites et les collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ec0e6-126">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|  
|<span data-ttu-id="ec0e6-127">Créer une collection.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-127">Create a new collection.</span></span>|[<span data-ttu-id="ec0e6-128">Créer une collection &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ec0e6-128">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)|  
|<span data-ttu-id="ec0e6-129">Ajouter des membres à une collection existante.</span><span class="sxs-lookup"><span data-stu-id="ec0e6-129">Add members to an existing collection.</span></span>|[<span data-ttu-id="ec0e6-130">Ajouter des membres à une collection &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ec0e6-130">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="ec0e6-131">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="ec0e6-131">Related Content</span></span>  
  
-   [<span data-ttu-id="ec0e6-132">Hiérarchies explicites &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ec0e6-132">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
-   [<span data-ttu-id="ec0e6-133">Exportation de données &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ec0e6-133">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
