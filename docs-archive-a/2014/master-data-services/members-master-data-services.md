---
title: Membres (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services]
- consolidated members [Master Data Services]
- consolidated members [Master Data Services], about consolidated members
- members [Master Data Services], about members
- leaf members [Master Data Services], about leaf members
- members [Master Data Services]
ms.assetid: 0fda32b9-677d-4ba2-bb28-f76f2383a30f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 89d2edb21b58575dffc21d9a6470171251889cc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698412"
---
# <a name="members-master-data-services"></a><span data-ttu-id="0370a-102">Membres (services de données de référence)</span><span class="sxs-lookup"><span data-stu-id="0370a-102">Members (Master Data Services)</span></span>
  <span data-ttu-id="0370a-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], les membres sont les données de référence physiques.</span><span class="sxs-lookup"><span data-stu-id="0370a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], members are the physical master data.</span></span> <span data-ttu-id="0370a-104">Par exemple, un membre peut être un vélo Road-150 spécifique dans une entité Product ou un client spécifique dans une entité Customer.</span><span class="sxs-lookup"><span data-stu-id="0370a-104">For example, a member can be a Road-150 bike in a Product entity or a specific customer in a Customer entity.</span></span>

## <a name="how-members-relate-to-other-model-objects"></a><span data-ttu-id="0370a-105">Relations entre les membres et les autres objets de modèle</span><span class="sxs-lookup"><span data-stu-id="0370a-105">How Members Relate to Other Model Objects</span></span>
 <span data-ttu-id="0370a-106">Vous pouvez considérer les membres comme les lignes d'une table.</span><span class="sxs-lookup"><span data-stu-id="0370a-106">You can think of members as rows in a table.</span></span> <span data-ttu-id="0370a-107">Les membres associés sont contenus dans une entité et chaque membre est défini par des valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="0370a-107">Related members are contained in an entity, and each member is defined by attribute values.</span></span>

 <span data-ttu-id="0370a-108">Dans cet exemple, la table représente une entité, les lignes de la table des membres et les colonnes de la table des attributs.</span><span class="sxs-lookup"><span data-stu-id="0370a-108">In this example, the table represents an entity, the rows in the table represent members, and the columns in the table represent attributes.</span></span> <span data-ttu-id="0370a-109">Chaque cellule représente une valeur d'attribut pour un membre spécifique.</span><span class="sxs-lookup"><span data-stu-id="0370a-109">Each cell represents an attribute value for a specific member.</span></span>

 <span data-ttu-id="0370a-110">![Entité Master Data Services représentée en tant que table](../../2014/master-data-services/media/mds-conc-entity-table.gif "Entité Master Data Services représentée en tant que table")</span><span class="sxs-lookup"><span data-stu-id="0370a-110">![Master Data Services Entity Represented as Table](../../2014/master-data-services/media/mds-conc-entity-table.gif "Master Data Services Entity Represented as Table")</span></span>

## <a name="member-types"></a><span data-ttu-id="0370a-111">Types de membres</span><span class="sxs-lookup"><span data-stu-id="0370a-111">Member Types</span></span>
 <span data-ttu-id="0370a-112">Il existe trois types de membres : les membres feuille, les membres consolidés et les membres de collection.</span><span class="sxs-lookup"><span data-stu-id="0370a-112">There are three types of members: leaf members, consolidated members, and collection members.</span></span>

 <span data-ttu-id="0370a-113">Les membres feuille sont les membres par défaut d'une entité.</span><span class="sxs-lookup"><span data-stu-id="0370a-113">Leaf members are the default members in an entity.</span></span>

-   <span data-ttu-id="0370a-114">Dans les hiérarchies dérivées, les membres feuille sont le seul type de membre.</span><span class="sxs-lookup"><span data-stu-id="0370a-114">In derived hierarchies, leaf members are the only type of member.</span></span> <span data-ttu-id="0370a-115">Les membres feuille d'une entité sont utilisés comme parents des membres feuille d'une autre entité.</span><span class="sxs-lookup"><span data-stu-id="0370a-115">Leaf members from one entity are used as parents of leaf members from another entity.</span></span>

-   <span data-ttu-id="0370a-116">Dans les hiérarchies explicites, les membres feuille représentent le niveau le plus bas et ils ne peuvent pas avoir d'enfants.</span><span class="sxs-lookup"><span data-stu-id="0370a-116">In explicit hierarchies, leaf members are the lowest level and cannot have children.</span></span>

 <span data-ttu-id="0370a-117">Les membres consolidés existent uniquement quand les hiérarchies explicites et les collections sont activées pour une entité.</span><span class="sxs-lookup"><span data-stu-id="0370a-117">Consolidated members exist only when explicit hierarchies and collections are enabled for the entity.</span></span>

-   <span data-ttu-id="0370a-118">Les hiérarchies dérivées ne contiennent pas de membres consolidés.</span><span class="sxs-lookup"><span data-stu-id="0370a-118">Derived hierarchies do not contain consolidated members.</span></span>

-   <span data-ttu-id="0370a-119">Dans les hiérarchies explicites, les membres consolidés peuvent être les parents d'autres membres de la hiérarchie, ou être les enfants.</span><span class="sxs-lookup"><span data-stu-id="0370a-119">In explicit hierarchies, consolidated members can be parents of other members within the hierarchy, or they can be children.</span></span>

## <a name="use-hierarchies-and-collections-to-organize-members"></a><span data-ttu-id="0370a-120">Utiliser des hiérarchies et des collections pour organiser des membres</span><span class="sxs-lookup"><span data-stu-id="0370a-120">Use Hierarchies and Collections to Organize Members</span></span>
 <span data-ttu-id="0370a-121">Les hiérarchies et les collections permettent de regrouper des membres pour la création de rapports ou l'analyse.</span><span class="sxs-lookup"><span data-stu-id="0370a-121">Hierarchies and collections can be used to group members for reporting or analysis.</span></span> <span data-ttu-id="0370a-122">Pour plus d’informations, consultez [Hiérarchies &#40;Master Data Services&#41;](hierarchies-master-data-services.md) et [Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0370a-122">For more information, see [Hierarchies &#40;Master Data Services&#41;](hierarchies-master-data-services.md) and [Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span></span>

## <a name="member-example"></a><span data-ttu-id="0370a-123">Exemple de membre</span><span class="sxs-lookup"><span data-stu-id="0370a-123">Member Example</span></span>
 <span data-ttu-id="0370a-124">Dans l'exemple suivant, chaque membre est constitué d'une valeur d'attribut : Name, Code, Subcategory, StandardCost, ListPrice et FilePhoto.</span><span class="sxs-lookup"><span data-stu-id="0370a-124">In the following example, each member is made up of a Name, Code, Subcategory, StandardCost, ListPrice, and FilePhoto attribute value.</span></span>

 <span data-ttu-id="0370a-125">![Table de l'entité Bike Product](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Table de l'entité Bike Product")</span><span class="sxs-lookup"><span data-stu-id="0370a-125">![Bike Product Entity Table](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Bike Product Entity Table")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="0370a-126">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="0370a-126">Related Tasks</span></span>

|<span data-ttu-id="0370a-127">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="0370a-127">Task Description</span></span>|<span data-ttu-id="0370a-128">Rubrique</span><span class="sxs-lookup"><span data-stu-id="0370a-128">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="0370a-129">Créez un membre feuille.</span><span class="sxs-lookup"><span data-stu-id="0370a-129">Create a new leaf member.</span></span>|[<span data-ttu-id="0370a-130">Créer un membre feuille &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-130">Create a Leaf Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)|
|<span data-ttu-id="0370a-131">Créez un membre consolidé.</span><span class="sxs-lookup"><span data-stu-id="0370a-131">Create a new consolidated member.</span></span>|[<span data-ttu-id="0370a-132">Créer un membre consolidé &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-132">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)|
|<span data-ttu-id="0370a-133">Supprimez une collection ou un membre existant.</span><span class="sxs-lookup"><span data-stu-id="0370a-133">Delete an existing member or collection.</span></span>|[<span data-ttu-id="0370a-134">Supprimer un membre ou une collection &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-134">Delete a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="0370a-135">Réactivez une collection ou un membre supprimé.</span><span class="sxs-lookup"><span data-stu-id="0370a-135">Reactivate a deleted member or collection.</span></span>|[<span data-ttu-id="0370a-136">Réactiver un membre ou une collection &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-136">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="0370a-137">Mettez à jour les valeurs d'attribut d'un membre.</span><span class="sxs-lookup"><span data-stu-id="0370a-137">Update the attribute values of a member.</span></span>|[<span data-ttu-id="0370a-138">Modifier le type d’attribut &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-138">Change the Attribute Type &#40;MDS Add-in for Excel&#41;</span></span>](microsoft-excel-add-in/change-the-attribute-type-mds-add-in-for-excel.md)|
|<span data-ttu-id="0370a-139">Déplacez des membres au sein d'une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="0370a-139">Move members within a hierarchy.</span></span>|[<span data-ttu-id="0370a-140">Déplacer des membres au sein d’une hiérarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-140">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="0370a-141">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="0370a-141">Related Content</span></span>

-   [<span data-ttu-id="0370a-142">Vue d'ensemble de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="0370a-142">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)

-   [<span data-ttu-id="0370a-143">Entités &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-143">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)

-   [<span data-ttu-id="0370a-144">Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-144">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="0370a-145">Hiérarchies &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-145">Hierarchies &#40;Master Data Services&#41;</span></span>](hierarchies-master-data-services.md)

-   [<span data-ttu-id="0370a-146">Collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-146">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)

-   [<span data-ttu-id="0370a-147">Autorisations de feuille &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-147">Leaf Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-permissions-master-data-services.md)

-   [<span data-ttu-id="0370a-148">Autorisations consolidées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-148">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)

-   [<span data-ttu-id="0370a-149">Opérateurs de filtre &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0370a-149">Filter Operators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/filter-operators-master-data-services.md)


