---
title: Hiérarchies (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services]
- hierarchies [Master Data Services], about hierarchies
ms.assetid: 70dbb1fc-ead7-45be-9552-a45e3ccd8d21
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 126a01c03134c6859426c09fda398408694795f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611137"
---
# <a name="hierarchies-master-data-services"></a><span data-ttu-id="7dc10-102">Hiérarchies (services de données de référence)</span><span class="sxs-lookup"><span data-stu-id="7dc10-102">Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="7dc10-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], une hiérarchie est une arborescence qui vous permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7dc10-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a hierarchy is a tree structure that you can use to:</span></span>

-   <span data-ttu-id="7dc10-104">regrouper des membres semblables à des fins d'organisation ;</span><span class="sxs-lookup"><span data-stu-id="7dc10-104">Group similar members for organizational purposes.</span></span>

-   <span data-ttu-id="7dc10-105">consolider et synthétiser des membres pour la création de rapports et l'analyse.</span><span class="sxs-lookup"><span data-stu-id="7dc10-105">Consolidate and summarize members for reporting and analysis.</span></span>

## <a name="what-hierarchies-contain"></a><span data-ttu-id="7dc10-106">Les hiérarchies contiennent</span><span class="sxs-lookup"><span data-stu-id="7dc10-106">What Hierarchies Contain</span></span>
 <span data-ttu-id="7dc10-107">Chaque hiérarchie contient les membres d'une ou de plusieurs entités.</span><span class="sxs-lookup"><span data-stu-id="7dc10-107">Each hierarchy contains members from one or more entities.</span></span> <span data-ttu-id="7dc10-108">Lorsqu'un membre est ajouté, modifié ou supprimé, toutes les hiérarchies sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="7dc10-108">When a member is added, changed, or deleted, all hierarchies are updated.</span></span> <span data-ttu-id="7dc10-109">Cela garantit l'exactitude de vos données dans toutes les hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="7dc10-109">This ensures that the data is accurate in all hierarchies.</span></span> <span data-ttu-id="7dc10-110">Les hiérarchies permettent aussi de garantir que chaque membre est compté une seule fois.</span><span class="sxs-lookup"><span data-stu-id="7dc10-110">Hierarchies also help ensure that each member is counted once and only once.</span></span>

 <span data-ttu-id="7dc10-111">Si vous souhaitez créer un regroupement d'un sous-ensemble de membres, envisagez d'utiliser une collection.</span><span class="sxs-lookup"><span data-stu-id="7dc10-111">If you want to create a grouping of a subset of members, consider using a collection.</span></span> <span data-ttu-id="7dc10-112">Pour plus d’informations, consultez [Collections &#40;Master Data Services&#41;](collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7dc10-112">For more information, see [Collections &#40;Master Data Services&#41;](collections-master-data-services.md).</span></span>

## <a name="kinds-of-hierarchies"></a><span data-ttu-id="7dc10-113">Types de hiérarchies</span><span class="sxs-lookup"><span data-stu-id="7dc10-113">Kinds of Hierarchies</span></span>
 <span data-ttu-id="7dc10-114">Vous pouvez créer plusieurs hiérarchies pour afficher et organiser vos membres de différentes façons.</span><span class="sxs-lookup"><span data-stu-id="7dc10-114">You can create multiple hierarchies to view and organize your members in different ways.</span></span> <span data-ttu-id="7dc10-115">Vous pouvez créer :</span><span class="sxs-lookup"><span data-stu-id="7dc10-115">You can create:</span></span>

-   <span data-ttu-id="7dc10-116">Des hiérarchies déséquilibrées d'une entité unique, appelées hiérarchies explicites.</span><span class="sxs-lookup"><span data-stu-id="7dc10-116">Ragged hierarchies from a single entity, which are called explicit hierarchies.</span></span> <span data-ttu-id="7dc10-117">Pour plus d’informations, consultez [Hiérarchies explicites &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7dc10-117">For more information, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>

-   <span data-ttu-id="7dc10-118">Des hiérarchies basées sur le niveau à partir de plusieurs entités selon les relations existantes entre les entités et leurs attributs, appelées hiérarchies dérivées.</span><span class="sxs-lookup"><span data-stu-id="7dc10-118">Level-based hierarchies from multiple entities, based on the existing relationships between entities and their attributes, which are called derived hierarchies.</span></span> <span data-ttu-id="7dc10-119">Pour plus d’informations, consultez [Hiérarchies dérivées &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7dc10-119">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="7dc10-120">Tous les membres dans une hiérarchie doivent figurer dans le même modèle.</span><span class="sxs-lookup"><span data-stu-id="7dc10-120">All members in a hierarchy must be within the same model.</span></span>

## <a name="hierarchies-are-not-taxonomies"></a><span data-ttu-id="7dc10-121">Les hiérarchies ne sont pas des taxonomies</span><span class="sxs-lookup"><span data-stu-id="7dc10-121">Hierarchies Are Not Taxonomies</span></span>
 <span data-ttu-id="7dc10-122">Une hiérarchie est différente d'une taxonomie.</span><span class="sxs-lookup"><span data-stu-id="7dc10-122">A hierarchy is different from a taxonomy.</span></span> <span data-ttu-id="7dc10-123">Une taxonomie classe des membres selon plusieurs attributs en même temps, alors qu'une hiérarchie les organise selon un attribut à la fois.</span><span class="sxs-lookup"><span data-stu-id="7dc10-123">A taxonomy organizes members by multiple attributes at the same time, while a hierarchy organizes members by one attribute at a time.</span></span> <span data-ttu-id="7dc10-124">Une taxonomie peut inclure le même membre plusieurs fois, alors qu'une hiérarchie inclut un membre une seule fois.</span><span class="sxs-lookup"><span data-stu-id="7dc10-124">A taxonomy can include the same member multiple times, while a hierarchy includes a member only once.</span></span>

 <span data-ttu-id="7dc10-125">Par exemple, le même vélo peut être inclus deux fois dans une taxonomie : une fois parce qu'il est de couleur rouge et une fois parce que sa taille est égale à 38.</span><span class="sxs-lookup"><span data-stu-id="7dc10-125">For example, the same bike can be included in a taxonomy twice: once because it's red, and once because it's a size 38.</span></span> <span data-ttu-id="7dc10-126">Dans une hiérarchie, le vélo n’étant inclus qu’une seule fois, vous devez décider de l’afficher en fonction de sa couleur ou de sa taille.</span><span class="sxs-lookup"><span data-stu-id="7dc10-126">In a hierarchy, the bike is included only once, so you must decide whether to show it in relation to its color or its size.</span></span>

## <a name="hierarchy-example"></a><span data-ttu-id="7dc10-127">Exemple de hiérarchie</span><span class="sxs-lookup"><span data-stu-id="7dc10-127">Hierarchy Example</span></span>
 <span data-ttu-id="7dc10-128">Dans l'exemple suivant, les membres de produit sont regroupés par membres de sous-catégorie.</span><span class="sxs-lookup"><span data-stu-id="7dc10-128">In the following example, product members are grouped by subcategory members.</span></span>

 <span data-ttu-id="7dc10-129">![Exemple de hiérarchie regroupée par sous-catégorie](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Exemple de hiérarchie regroupée par sous-catégorie")</span><span class="sxs-lookup"><span data-stu-id="7dc10-129">![Hierarchy Grouped by Subcategory Example](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Hierarchy Grouped by Subcategory Example")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="7dc10-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="7dc10-130">Related Tasks</span></span>

|<span data-ttu-id="7dc10-131">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="7dc10-131">Task Description</span></span>|<span data-ttu-id="7dc10-132">Rubrique</span><span class="sxs-lookup"><span data-stu-id="7dc10-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="7dc10-133">Activer une entité pour les hiérarchies explicites et les collections.</span><span class="sxs-lookup"><span data-stu-id="7dc10-133">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="7dc10-134">Activez une entité pour les hiérarchies explicites et les collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc10-134">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="7dc10-135">Créer une hiérarchie explicite.</span><span class="sxs-lookup"><span data-stu-id="7dc10-135">Create a explicit hierarchy.</span></span>|[<span data-ttu-id="7dc10-136">Créer une hiérarchie explicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc10-136">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="7dc10-137">Créer une hiérarchie dérivée.</span><span class="sxs-lookup"><span data-stu-id="7dc10-137">Create a derived hierarchy.</span></span>|[<span data-ttu-id="7dc10-138">Créer une hiérarchie dérivée &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc10-138">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="7dc10-139">Masquer ou supprimer des niveaux dans une hiérarchie dérivée existante.</span><span class="sxs-lookup"><span data-stu-id="7dc10-139">Hide or delete levels in an existing derived hierarchy.</span></span>|[<span data-ttu-id="7dc10-140">Masquer ou supprimer des niveaux dans une hiérarchie dérivée &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc10-140">Hide or Delete Levels in a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hide-or-delete-levels-in-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="7dc10-141">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="7dc10-141">Related Content</span></span>

-   [<span data-ttu-id="7dc10-142">Hiérarchies explicites &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc10-142">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)

-   [<span data-ttu-id="7dc10-143">Hiérarchies dérivées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc10-143">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="7dc10-144">Hiérarchies récursives &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc10-144">Recursive Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/recursive-hierarchies-master-data-services.md)

-   [<span data-ttu-id="7dc10-145">Hiérarchies dérivées avec un niveau supérieur composé d’une hiérarchie explicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc10-145">Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md)

-   [<span data-ttu-id="7dc10-146">Collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc10-146">Collections &#40;Master Data Services&#41;</span></span>](collections-master-data-services.md)


