---
title: Hiérarchies dérivées avec des niveaux supérieurs d’une hiérarchie dérivée (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], derived hierarchies with explicit caps
- explicit hierarchies, derived hierarchies with explicit caps
- derived hierarchies, derived hierarchies with explicit caps
ms.assetid: 6a82ff66-c137-4757-99bb-787d189b4295
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d2460ddf098f0547c2876dd9689f5d2bf9b461a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602173"
---
# <a name="derived-hierarchies-with-explicit-caps-master-data-services"></a><span data-ttu-id="aa58c-102">Hiérarchies dérivées avec un niveau supérieur composé d'une hiérarchie explicite (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="aa58c-102">Derived Hierarchies with Explicit Caps (Master Data Services)</span></span>
  <span data-ttu-id="aa58c-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], si une hiérarchie dérivée inclut une hiérarchie explicite, les niveaux de la hiérarchie explicite sont utilisés comme niveaux supérieurs de la hiérarchie dérivée.</span><span class="sxs-lookup"><span data-stu-id="aa58c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when the levels from an explicit hierarchy are used as the top levels of a derived hierarchy, this is called a derived hierarchy with an explicit cap.</span></span>

 <span data-ttu-id="aa58c-104">La hiérarchie explicite doit être basée sur la même entité que celle située au sommet de la hiérarchie dérivée.</span><span class="sxs-lookup"><span data-stu-id="aa58c-104">The explicit hierarchy must be based on the same entity as the entity at the top of the derived hierarchy.</span></span>

 <span data-ttu-id="aa58c-105">Dans l’interface utilisateur de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , vous créez ce type de hiérarchie en faisant glisser une hiérarchie explicite au sommet d’une hiérarchie dérivée.</span><span class="sxs-lookup"><span data-stu-id="aa58c-105">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), you create this type of hierarchy by dragging an explicit hierarchy to the top of a derived hierarchy.</span></span>

 <span data-ttu-id="aa58c-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="aa58c-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span></span>

## <a name="derived-hierarchy-with-explicit-cap-example"></a><span data-ttu-id="aa58c-107">Exemple de hiérarchie dérivée avec niveau supérieur</span><span class="sxs-lookup"><span data-stu-id="aa58c-107">Derived Hierarchy with Explicit Cap Example</span></span>
 <span data-ttu-id="aa58c-108">Dans cet exemple, les membres de la hiérarchie explicite proviennent de l'entité Subcategory.</span><span class="sxs-lookup"><span data-stu-id="aa58c-108">In this example, the members in the explicit hierarchy are from the Subcategory entity.</span></span> <span data-ttu-id="aa58c-109">Dans la hiérarchie dérivée, les membres de niveau supérieur proviennent également de l'entité Subcategory.</span><span class="sxs-lookup"><span data-stu-id="aa58c-109">In the derived hierarchy, the top-level members are also from the Subcategory entity.</span></span>

 <span data-ttu-id="aa58c-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span><span class="sxs-lookup"><span data-stu-id="aa58c-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span></span>

 <span data-ttu-id="aa58c-111">En utilisant la hiérarchie explicite au sommet d'une hiérarchie dérivée, la hiérarchie dérivée devient déséquilibrée.</span><span class="sxs-lookup"><span data-stu-id="aa58c-111">By using the explicit hierarchy at the top of a derived hierarchy, the derived hierarchy becomes ragged.</span></span>

## <a name="rules"></a><span data-ttu-id="aa58c-112">Règles</span><span class="sxs-lookup"><span data-stu-id="aa58c-112">Rules</span></span>

-   <span data-ttu-id="aa58c-113">Une hiérarchie dérivée avec un niveau supérieur ne peut inclure qu'une seule hiérarchie explicite.</span><span class="sxs-lookup"><span data-stu-id="aa58c-113">You cannot have more than one explicit hierarchy in a derived hierarchy with explicit cap.</span></span>

-   <span data-ttu-id="aa58c-114">Vous pouvez utiliser la même hiérarchie explicite comme niveau supérieur dans plusieurs hiérarchies dérivées.</span><span class="sxs-lookup"><span data-stu-id="aa58c-114">You can use the same explicit hierarchy as a cap for multiple derived hierarchies.</span></span>

-   <span data-ttu-id="aa58c-115">Vous ne pouvez pas affecter d'autorisations de membre de hiérarchie à des hiérarchies dérivées avec un niveau supérieur d'une hiérarchie dérivée.</span><span class="sxs-lookup"><span data-stu-id="aa58c-115">You cannot assign hierarchy member permissions to derived hierarchies with explicit caps.</span></span> <span data-ttu-id="aa58c-116">Si vous affectez des autorisations individuellement à la hiérarchie explicite ou à la hiérarchie dérivée, les autorisations s'appliquent aux deux hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="aa58c-116">If you assign permissions to either the explicit hierarchy or the derived hierarchy individually, the permissions affect both hierarchies.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="aa58c-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="aa58c-117">Related Tasks</span></span>

|<span data-ttu-id="aa58c-118">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="aa58c-118">Task Description</span></span>|<span data-ttu-id="aa58c-119">Rubrique</span><span class="sxs-lookup"><span data-stu-id="aa58c-119">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="aa58c-120">Créer une hiérarchie dérivée.</span><span class="sxs-lookup"><span data-stu-id="aa58c-120">Create a derived hierarchy.</span></span>|[<span data-ttu-id="aa58c-121">Créer une hiérarchie dérivée &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa58c-121">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="aa58c-122">Créer une hiérarchie explicite.</span><span class="sxs-lookup"><span data-stu-id="aa58c-122">Create an explicit hierarchy.</span></span>|[<span data-ttu-id="aa58c-123">Créer une hiérarchie explicite &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa58c-123">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="aa58c-124">Supprimer une hiérarchie dérivée existante.</span><span class="sxs-lookup"><span data-stu-id="aa58c-124">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="aa58c-125">Supprimer une hiérarchie dérivée &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa58c-125">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="aa58c-126">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="aa58c-126">Related Content</span></span>

-   [<span data-ttu-id="aa58c-127">Hiérarchies dérivées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa58c-127">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="aa58c-128">Hiérarchies explicites &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa58c-128">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)


