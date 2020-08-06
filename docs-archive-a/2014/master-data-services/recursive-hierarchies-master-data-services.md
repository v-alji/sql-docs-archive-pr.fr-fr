---
title: Hiérarchies récursives (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- recursive hierarchies [Master Data Services]
- hierarchies [Master Data Services], recursive hierarchies
ms.assetid: 9408c6ea-d9c4-4a0b-8a1b-1457fb6944af
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3c149d500ce1499ad36247d5e32bb6f2d55b4250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613492"
---
# <a name="recursive-hierarchies-master-data-services"></a><span data-ttu-id="26900-102">Hiérarchies récursives (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="26900-102">Recursive Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="26900-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], une hiérarchie récursive est une hiérarchie dérivée qui comporte une relation récursive.</span><span class="sxs-lookup"><span data-stu-id="26900-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a recursive hierarchy is a derived hierarchy that includes a recursive relationship.</span></span> <span data-ttu-id="26900-104">Une relation récursive existe lorsqu'une entité a un attribut basé sur un domaine et sur l'entité elle-même.</span><span class="sxs-lookup"><span data-stu-id="26900-104">A recursive relationship exists when an entity has a domain-based attribute based on the entity itself.</span></span>

## <a name="recursive-hierarchy-example"></a><span data-ttu-id="26900-105">Exemple de hiérarchie récursive</span><span class="sxs-lookup"><span data-stu-id="26900-105">Recursive Hierarchy Example</span></span>
 <span data-ttu-id="26900-106">Un exemple de hiérarchie récursive est une structure d'organisation.</span><span class="sxs-lookup"><span data-stu-id="26900-106">A typical recursive hierarchy example is an organizational structure.</span></span> <span data-ttu-id="26900-107">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous devriez effectuer cette opération en créant une entité Employee avec un attribut basé sur un domaine appelé Manager.</span><span class="sxs-lookup"><span data-stu-id="26900-107">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you would do this by creating an Employee entity with a domain-based attribute called Manager.</span></span> <span data-ttu-id="26900-108">L'attribut Manager est rempli à partir de la liste des employés.</span><span class="sxs-lookup"><span data-stu-id="26900-108">The Manager attribute is populated from the list of employees.</span></span> <span data-ttu-id="26900-109">Dans cet exemple d'organisation, tous les employés peuvent être des responsables.</span><span class="sxs-lookup"><span data-stu-id="26900-109">In this sample organization, all employees can be managers.</span></span>

 <span data-ttu-id="26900-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span><span class="sxs-lookup"><span data-stu-id="26900-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span></span>

 <span data-ttu-id="26900-111">Vous pouvez créer une hiérarchie dérivée qui met en évidence la relation entre l'entité Employee et l'attribut basé sur un domaine Manager.</span><span class="sxs-lookup"><span data-stu-id="26900-111">You can create a derived hierarchy that highlights the relationship between the Employee entity and the Manager domain-based attribute.</span></span>

 <span data-ttu-id="26900-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="26900-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span></span>

 <span data-ttu-id="26900-113">Pour inclure chaque membre dans la hiérarchie une seule fois, vous pouvez ancrer des relations Null.</span><span class="sxs-lookup"><span data-stu-id="26900-113">To include each member in the hierarchy only once, you can anchor null relationships.</span></span> <span data-ttu-id="26900-114">Lorsque vous procédez ainsi, les membres avec des valeurs d'attribut basé sur un domaine vides sont affichés au niveau supérieur de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="26900-114">When you do, members with blank domain-based attribute values are displayed at the top level of the hierarchy.</span></span>

 <span data-ttu-id="26900-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span><span class="sxs-lookup"><span data-stu-id="26900-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span></span>

 <span data-ttu-id="26900-116">Si vous n'ancrez pas de relations Null, les membres sont inclus plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="26900-116">If you do not anchor null relationships, members are included multiple times.</span></span> <span data-ttu-id="26900-117">Tous les membres sont affichés au niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="26900-117">All members are displayed at the top level.</span></span> <span data-ttu-id="26900-118">Ils sont également affichés sous les membres dont ils sont les attributs.</span><span class="sxs-lookup"><span data-stu-id="26900-118">They are also displayed under members of which they are attributes.</span></span>

 <span data-ttu-id="26900-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span><span class="sxs-lookup"><span data-stu-id="26900-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span></span>

 <span data-ttu-id="26900-120">Dans cet exemple, Marcia est située au niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="26900-120">In this example, Marcia is at the top level.</span></span> <span data-ttu-id="26900-121">Elle n'est la responsable d'aucun employé, car elle n'est pas utilisée en tant que valeur d'attribut basé sur un domaine pour les autres membres Employee.</span><span class="sxs-lookup"><span data-stu-id="26900-121">She is not the manager of any employees because she is not used as a domain-based attribute value for any other Employee members.</span></span> <span data-ttu-id="26900-122">Robert, par opposition, dispose d'un niveau au-dessous de lui, car, pour Marcia, la valeur de l'attribut Manager est Robert.</span><span class="sxs-lookup"><span data-stu-id="26900-122">Robert, in contrast, has a level beneath him because Marcia has Robert as her Manager attribute value.</span></span>

## <a name="rules"></a><span data-ttu-id="26900-123">Règles</span><span class="sxs-lookup"><span data-stu-id="26900-123">Rules</span></span>

-   <span data-ttu-id="26900-124">Une hiérarchie dérivée ne peut pas contenir plusieurs relations récursives.</span><span class="sxs-lookup"><span data-stu-id="26900-124">A derived hierarchy cannot contain more than one recursive relationship.</span></span> <span data-ttu-id="26900-125">Elle peut, toutefois, posséder d'autres relations dérivées (par exemple, une hiérarchie dérivée qui contient une relation Responsable à Employé récursive peut également avoir des relations Pays à Responsable et Employé à Magasin).</span><span class="sxs-lookup"><span data-stu-id="26900-125">It can, however, have other derived relationships (for example, a derived hierarchy that contains a recursive Manager to Employee relationship can also have Country to Manager and Employee to Store relationships).</span></span>

-   <span data-ttu-id="26900-126">Vous ne pouvez pas affecter d’autorisations de membre (sous l’onglet **Membres de hiérarchie** ) à des membres dans une hiérarchie récursive.</span><span class="sxs-lookup"><span data-stu-id="26900-126">You cannot assign member permissions (on the **Hierarchy Members** tab) to members in a recursive hierarchy.</span></span>

-   <span data-ttu-id="26900-127">Les hiérarchies récursives ne peuvent pas inclure de relations circulaires.</span><span class="sxs-lookup"><span data-stu-id="26900-127">Recursive hierarchies cannot include circular relationships.</span></span> <span data-ttu-id="26900-128">Par exemple, Katherine ne peut pas être la responsable de Sandeep si Sandeep est déjà la responsable de Katherine.</span><span class="sxs-lookup"><span data-stu-id="26900-128">For example, Katherine cannot be Sandeep's manager if Sandeep is her manager.</span></span> <span data-ttu-id="26900-129">Par ailleurs, Katherine ne peut pas être sa propre responsable.</span><span class="sxs-lookup"><span data-stu-id="26900-129">Also, Katherine cannot manage herself.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="26900-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="26900-130">Related Tasks</span></span>

|<span data-ttu-id="26900-131">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="26900-131">Task Description</span></span>|<span data-ttu-id="26900-132">Rubrique</span><span class="sxs-lookup"><span data-stu-id="26900-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="26900-133">Créer une hiérarchie dérivée.</span><span class="sxs-lookup"><span data-stu-id="26900-133">Create a derived hierarchy.</span></span>|[<span data-ttu-id="26900-134">Créer une hiérarchie dérivée &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="26900-134">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="26900-135">Modifier le nom d'une hiérarchie dérivée existante.</span><span class="sxs-lookup"><span data-stu-id="26900-135">Change the name of an existing derived hierarchy.</span></span>|[<span data-ttu-id="26900-136">Modifier le nom d’une hiérarchie dérivée &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="26900-136">Change a Derived Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-derived-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="26900-137">Supprimer une hiérarchie dérivée existante.</span><span class="sxs-lookup"><span data-stu-id="26900-137">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="26900-138">Supprimer une hiérarchie dérivée &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="26900-138">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="26900-139">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="26900-139">Related Content</span></span>

-   [<span data-ttu-id="26900-140">Attributs basés sur un domaine &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="26900-140">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)

-   [<span data-ttu-id="26900-141">Hiérarchies dérivées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="26900-141">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)


