---
title: Hiérarchies explicites (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, about explicit hierarchies
- hierarchies [Master Data Services], explicit hierarchies
- explicit hierarchies
ms.assetid: e6f44e37-e1f0-4c38-a816-1935a856d5a4
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f37f341dc2c003683e696f2767a6b644047d5a0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699941"
---
# <a name="explicit-hierarchies-master-data-services"></a><span data-ttu-id="5c2ca-102">Hiérarchies explicites (services de données de référence)</span><span class="sxs-lookup"><span data-stu-id="5c2ca-102">Explicit Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="5c2ca-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], une hiérarchie explicite organise les membres d'une seule entité comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], an explicit hierarchy organizes members from a single entity in any way you specify.</span></span> <span data-ttu-id="5c2ca-104">La structure peut être déséquilibrée et contrairement aux hiérarchies dérivées, les hiérarchies explicites ne sont pas basées sur des relations d'attributs basés sur un domaine.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-104">The structure can be ragged and unlike derived hierarchies, explicit hierarchies are not based on domain-based attribute relationships.</span></span>

## <a name="consolidated-members-group-other-members"></a><span data-ttu-id="5c2ca-105">Les membres consolidés regroupent d'autres membres</span><span class="sxs-lookup"><span data-stu-id="5c2ca-105">Consolidated Members Group Other Members</span></span>
 <span data-ttu-id="5c2ca-106">Une hiérarchie explicite utilise des membres consolidés que vous créez en vue de regrouper d'autres membres.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-106">An explicit hierarchy uses consolidated members that you create for the purpose of grouping other members.</span></span> <span data-ttu-id="5c2ca-107">Ces membres consolidés ne peuvent appartenir qu'à une seule hiérarchie explicite à la fois.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-107">These consolidated members can belong to only one explicit hierarchy at a time.</span></span> <span data-ttu-id="5c2ca-108">Une hiérarchie explicite inclut également tous les membres feuille de l'entité associée.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-108">An explicit hierarchy also includes all of the leaf members from the associated entity.</span></span>

 <span data-ttu-id="5c2ca-109">Une hiérarchie explicite peut être déséquilibrée, ce qui signifie qu'elle peut se terminer à des niveaux différents simultanément.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-109">An explicit hierarchy can be ragged, which means that the hierarchy can end at different levels simultaneously.</span></span> <span data-ttu-id="5c2ca-110">Chaque membre consolidé peut avoir un nombre illimité de membres consolidés et feuille en dessous, ou n'en avoir aucun.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-110">Each consolidated member can have an unlimited number of consolidated and leaf members underneath, or can have none.</span></span> <span data-ttu-id="5c2ca-111">Les membres feuille peuvent se trouver sous un membre consolidé unique ou sous plusieurs niveaux de membres consolidés.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-111">The leaf members can be under a single consolidated member or under multiple levels of consolidated members.</span></span>

> [!NOTE]
>  <span data-ttu-id="5c2ca-112">Avant de pouvoir créer une hiérarchie explicite, l'entité doit être activée pour les hiérarchies explicites.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-112">Before you can create an explicit hierarchy, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="5c2ca-113">Pour plus d’informations, consultez [activer une entité pour les hiérarchies explicites et les Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5c2ca-113">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>

## <a name="types-of-explicit-hierarchies"></a><span data-ttu-id="5c2ca-114">Types de hiérarchies explicites</span><span class="sxs-lookup"><span data-stu-id="5c2ca-114">Types of Explicit Hierarchies</span></span>
 <span data-ttu-id="5c2ca-115">Il existe deux types de hiérarchies explicites : obligatoire et non obligatoire.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-115">There are two types of explicit hierarchies: mandatory and non-mandatory.</span></span>

### <a name="mandatory-explicit-hierarchy"></a><span data-ttu-id="5c2ca-116">Hiérarchie explicite obligatoire</span><span class="sxs-lookup"><span data-stu-id="5c2ca-116">Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="5c2ca-117">Une hiérarchie explicite obligatoire est une hiérarchie dans laquelle tous les membres feuille doivent être inclus dans l'arborescence hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-117">A mandatory explicit hierarchy is a hierarchy in which all leaf members must be included in the hierarchy tree.</span></span> <span data-ttu-id="5c2ca-118">Par défaut, tous les membres sont inclus à la racine de l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-118">By default, all members are included at the root of the tree.</span></span> <span data-ttu-id="5c2ca-119">Vous pouvez réorganiser les membres autant que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-119">You can rearrange the members as needed.</span></span>

### <a name="non-mandatory-explicit-hierarchy"></a><span data-ttu-id="5c2ca-120">Hiérarchie explicite non obligatoire</span><span class="sxs-lookup"><span data-stu-id="5c2ca-120">Non-Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="5c2ca-121">Une hiérarchie explicite non obligatoire est une hiérarchie dans laquelle tous les membres feuille se trouvent dans un nœud **Inutilisé** créé par le système.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-121">A non-mandatory explicit hierarchy is a hierarchy in which all leaf members are in a system-created **Unused** node.</span></span> <span data-ttu-id="5c2ca-122">Vous pouvez déplacer des membres hors de ce nœud lorsque vous en avez besoin.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-122">You can move members out of this node as you need them.</span></span> <span data-ttu-id="5c2ca-123">Le reste des membres peut rester dans le nœud **Inutilisé** .</span><span class="sxs-lookup"><span data-stu-id="5c2ca-123">The rest of the members can remain in the **Unused** node.</span></span>

 <span data-ttu-id="5c2ca-124">Lorsque vous utilisez des hiérarchies explicites non obligatoires, toute création de rapports ou analyse faites sur la hiérarchie peuvent ne pas correspondre à celles effectuées sur les hiérarchies obligatoires.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-124">When you use non-mandatory explicit hierarchies, any reporting or analysis done on the hierarchy may not match reporting or analysis done on mandatory hierarchies.</span></span>

## <a name="rules"></a><span data-ttu-id="5c2ca-125">Règles</span><span class="sxs-lookup"><span data-stu-id="5c2ca-125">Rules</span></span>
 <span data-ttu-id="5c2ca-126">Les règles suivantes s'appliquent aux hiérarchies explicites (à la fois obligatoire et non obligatoire).</span><span class="sxs-lookup"><span data-stu-id="5c2ca-126">The following rules apply to explicit hierarchies (both mandatory and non-mandatory).</span></span>

-   <span data-ttu-id="5c2ca-127">Chaque membre feuille ne peut être inclus dans la hiérarchie qu'une fois.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-127">Each leaf member can be included in the hierarchy only once.</span></span>

-   <span data-ttu-id="5c2ca-128">Tous les membres consolidés doivent être inclus dans une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-128">All consolidated members must be included in a hierarchy.</span></span>

-   <span data-ttu-id="5c2ca-129">Les membres consolidés ne peuvent pas être dans plusieurs hiérarchies explicites.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-129">Consolidated members cannot be in more than one explicit hierarchy.</span></span>

-   <span data-ttu-id="5c2ca-130">Les membres consolidés dans l'arborescence hiérarchique n'ont pas à contenir des membres feuille en dessous.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-130">Consolidated members in the hierarchy tree do not have to contain leaf members underneath them.</span></span>

-   <span data-ttu-id="5c2ca-131">Si vous supprimez une hiérarchie explicite, tous les membres consolidés utilisés dans la hiérarchie sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-131">If you delete an explicit hierarchy, all consolidated members that were used in the hierarchy are deleted.</span></span>

-   <span data-ttu-id="5c2ca-132">Si vous supprimez un membre consolidé qui était dans une hiérarchie explicite, tous les membres feuille regroupés selon ce membre consolidé sont déplacés vers la racine.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-132">If you delete a consolidated member that was in an explicit hierarchy, all leaf members that were grouped by that consolidated member are moved to the root.</span></span>

## <a name="explicit-hierarchies-versus-derived-hierarchies"></a><span data-ttu-id="5c2ca-133">Hiérarchies explicites et hiérarchies dérivées</span><span class="sxs-lookup"><span data-stu-id="5c2ca-133">Explicit Hierarchies versus Derived Hierarchies</span></span>
 <span data-ttu-id="5c2ca-134">Le tableau suivant répertorie certaines différences entre les hiérarchies explicites et dérivées.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-134">The following table shows some of the differences between explicit and derived hierarchies.</span></span>

|<span data-ttu-id="5c2ca-135">Hiérarchies explicites</span><span class="sxs-lookup"><span data-stu-id="5c2ca-135">Explicit Hierarchies</span></span>|<span data-ttu-id="5c2ca-136">Hiérarchies dérivées</span><span class="sxs-lookup"><span data-stu-id="5c2ca-136">Derived Hierarchies</span></span>|
|--------------------------|-------------------------|
|<span data-ttu-id="5c2ca-137">La structure est définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5c2ca-137">Structure is defined by the user</span></span>|<span data-ttu-id="5c2ca-138">La structure est dérivée des relations entre les attributs basés sur un domaine</span><span class="sxs-lookup"><span data-stu-id="5c2ca-138">Structure is derived from the relationships between domain-based attributes</span></span>|
|<span data-ttu-id="5c2ca-139">Contient les membres d'une seule entité</span><span class="sxs-lookup"><span data-stu-id="5c2ca-139">Contains members from a single entity</span></span>|<span data-ttu-id="5c2ca-140">Contient les membres de plusieurs entités</span><span class="sxs-lookup"><span data-stu-id="5c2ca-140">Contains members from multiple entities</span></span>|
|<span data-ttu-id="5c2ca-141">Utilise les membres consolidés pour regrouper d'autres membres</span><span class="sxs-lookup"><span data-stu-id="5c2ca-141">Uses consolidated members to group other members</span></span>|<span data-ttu-id="5c2ca-142">Utilise des membres feuille d'une entité pour regrouper des membres feuille d'une autre entité</span><span class="sxs-lookup"><span data-stu-id="5c2ca-142">Uses leaf members from one entity to group leaf members from another entity</span></span>|
|<span data-ttu-id="5c2ca-143">Peut être déséquilibré</span><span class="sxs-lookup"><span data-stu-id="5c2ca-143">Can be ragged</span></span>|<span data-ttu-id="5c2ca-144">Contient toujours un nombre cohérent de niveaux</span><span class="sxs-lookup"><span data-stu-id="5c2ca-144">Always contains a consistent number of levels</span></span>|

## <a name="explicit-hierarchy-example"></a><span data-ttu-id="5c2ca-145">Exemple de hiérarchie explicite</span><span class="sxs-lookup"><span data-stu-id="5c2ca-145">Explicit Hierarchy Example</span></span>
 <span data-ttu-id="5c2ca-146">Dans l'exemple suivant, l'entité Product contient les membres feuille suivants : BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450} et BK-R650 {Road-650}.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-146">In the following example, the Product entity contains these leaf members: BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450}, and BK-R650 {Road-650}.</span></span>

 <span data-ttu-id="5c2ca-147">Pour synthétiser ces membres feuille à des points de consolidation spécifiques, vous pouvez créer des membres consolidés dans l'entité Product.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-147">To summarize these leaf members at specific consolidation points, you can create consolidated members in the Product entity.</span></span> <span data-ttu-id="5c2ca-148">Insérez les membres consolidés à des niveaux de l'arborescence hiérarchique où vous souhaitez synthétiser les membres feuille.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-148">Insert the consolidated members at levels in the hierarchy tree where you want to summarize the leaf members.</span></span> <span data-ttu-id="5c2ca-149">Il n'existe aucune limitation quant à l'emplacement où vous insérez vos membres consolidés ; toutefois, chaque membre (feuille ou consolidé) ne peut être utilisé qu'une fois.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-149">There is no limitation on where you insert your consolidated members; however, each member (leaf or consolidated) can be used only once.</span></span>

 <span data-ttu-id="5c2ca-150">![Exemple de hiérarchie explicite Mountain Bike](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Exemple de hiérarchie explicite Mountain Bike")</span><span class="sxs-lookup"><span data-stu-id="5c2ca-150">![Mountain Bike Explicit Hierarchy Example](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Mountain Bike Explicit Hierarchy Example")</span></span>

 <span data-ttu-id="5c2ca-151">Les membres consolidés peuvent être utilisés pour regrouper des membres à tout niveau, et les membres feuille et consolidés sont triés dans l'ordre que vous déterminez.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-151">Consolidated members can be used to group members at any level, and leaf and consolidated members are sorted in the order you determine.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="5c2ca-152">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="5c2ca-152">Related Tasks</span></span>

|<span data-ttu-id="5c2ca-153">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="5c2ca-153">Task Description</span></span>|<span data-ttu-id="5c2ca-154">Rubrique</span><span class="sxs-lookup"><span data-stu-id="5c2ca-154">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="5c2ca-155">Activer une entité pour les hiérarchies explicites et les collections.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-155">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="5c2ca-156">Activez une entité pour les hiérarchies explicites et les collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c2ca-156">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="5c2ca-157">Créer une hiérarchie explicite.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-157">Create a new explicit hierarchy.</span></span>|[<span data-ttu-id="5c2ca-158">Créer une hiérarchie explicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c2ca-158">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="5c2ca-159">Modifier le nom d'une hiérarchie explicite existante.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-159">Change the name of an existing explicity hierarchy.</span></span>|[<span data-ttu-id="5c2ca-160">Modifier le nom d’une hiérarchie explicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c2ca-160">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="5c2ca-161">Supprimer une hiérarchie explicite existante.</span><span class="sxs-lookup"><span data-stu-id="5c2ca-161">Delete an existing explicit hierarchy.</span></span>|[<span data-ttu-id="5c2ca-162">Supprimer une hiérarchie explicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c2ca-162">Delete an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-explicit-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="5c2ca-163">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="5c2ca-163">Related Content</span></span>

-   [<span data-ttu-id="5c2ca-164">Hiérarchies dérivées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c2ca-164">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="5c2ca-165">Collections &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5c2ca-165">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)


