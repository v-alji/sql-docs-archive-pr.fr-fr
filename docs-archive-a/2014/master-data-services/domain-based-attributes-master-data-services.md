---
title: Attributs basés sur un domaine (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], about domain-based attributes
- domain-based attributes [Master Data Services]
- attributes [Master Data Services], domain-based attributes
ms.assetid: df6f33ff-97f6-466c-af74-9780b2247473
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9182974923848d49ed3e9ecfb58a14949784a2c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615170"
---
# <a name="domain-based-attributes-master-data-services"></a><span data-ttu-id="f9492-102">Attributs basés sur un domaine (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f9492-102">Domain-Based Attributes (Master Data Services)</span></span>
  <span data-ttu-id="f9492-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], un attribut basé sur un domaine est un attribut dont les valeurs sont remplies par les membres d'une autre entité.</span><span class="sxs-lookup"><span data-stu-id="f9492-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a domain-based attribute is an attribute with values that are populated by members from another entity.</span></span> <span data-ttu-id="f9492-104">Vous pouvez considérer un attribut basé sur un domaine sous la forme d'une liste contrainte ; les attributs basés sur un domaine empêchent les utilisateurs d'entrer des valeurs d'attribut qui sont valides.</span><span class="sxs-lookup"><span data-stu-id="f9492-104">You can think of a domain-based attribute as a constrained list; domain-based attributes prevent users from entering attribute values that are not valid.</span></span> <span data-ttu-id="f9492-105">Pour sélectionner une valeur d'attribut, l'utilisateur doit choisir dans une liste.</span><span class="sxs-lookup"><span data-stu-id="f9492-105">To select an attribute value, the user must pick from a list.</span></span>

## <a name="domain-based-attribute-example"></a><span data-ttu-id="f9492-106">Exemple d'attribut basé sur un domaine</span><span class="sxs-lookup"><span data-stu-id="f9492-106">Domain-Based Attribute Example</span></span>
 <span data-ttu-id="f9492-107">Dans l'image suivante, l'entité Product a un attribut basé sur un domaine appelé Subcategory.</span><span class="sxs-lookup"><span data-stu-id="f9492-107">In the following image, the Product entity has a domain-based attribute called Subcategory.</span></span> <span data-ttu-id="f9492-108">L'attribut Subcategory est rempli par les valeurs de l'entité Subcategory.</span><span class="sxs-lookup"><span data-stu-id="f9492-108">The Subcategory attribute is populated by values from the Subcategory entity.</span></span>

 <span data-ttu-id="f9492-109">L'entité Subcategory a un attribut basé sur un domaine appelé Category.</span><span class="sxs-lookup"><span data-stu-id="f9492-109">The Subcategory entity has a domain-based attribute called Category.</span></span> <span data-ttu-id="f9492-110">L'attribut Category est rempli par les valeurs de l'entité Category.</span><span class="sxs-lookup"><span data-stu-id="f9492-110">The Category attribute is populated by values from the Category entity.</span></span>

 <span data-ttu-id="f9492-111">![Attributs basés sur un domaine à une entité](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Attributs basés sur un domaine à une entité")</span><span class="sxs-lookup"><span data-stu-id="f9492-111">![Domain-Based Attributes in an Entity](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Domain-Based Attributes in an Entity")</span></span>

## <a name="use-same-entity-for-multiple-domain-based-attributes"></a><span data-ttu-id="f9492-112">Utiliser des attributs basés sur un domaine dans la même entité</span><span class="sxs-lookup"><span data-stu-id="f9492-112">Use Same Entity for Multiple Domain-Based Attributes</span></span>
 <span data-ttu-id="f9492-113">Vous pouvez utiliser la même entité en tant qu'attribut basé sur un domaine de plusieurs entités.</span><span class="sxs-lookup"><span data-stu-id="f9492-113">You can use the same entity as a domain-based attribute of multiple entities.</span></span> <span data-ttu-id="f9492-114">Par exemple, vous pouvez créer une entité appelée YesNoIndicator avec les membres : Yes, No et Maybe.</span><span class="sxs-lookup"><span data-stu-id="f9492-114">For example, you can create an entity called YesNoIndicator with the members: Yes, No, and Maybe.</span></span> <span data-ttu-id="f9492-115">Vous pouvez créer un attribut basé sur un domaine nommé InStock et utiliser l'entité YesNoIndicator comme source.</span><span class="sxs-lookup"><span data-stu-id="f9492-115">You can create a domain-based attribute named InStock and use the YesNoIndicator entity as the source.</span></span> <span data-ttu-id="f9492-116">Vous pouvez également créer un autre attribut basé sur un domaine nommé Approved et utiliser l'entité YesNoIndicator comme source.</span><span class="sxs-lookup"><span data-stu-id="f9492-116">You can also create another domain-based attribute named Approved and use the YesNoIndicator entity as a source.</span></span> <span data-ttu-id="f9492-117">Lorsque vous voulez que les utilisateurs choisissent dans une liste des membres de l'entité YesNoIndicator, vous pouvez utiliser l'entité comme attribut basé sur un domaine.</span><span class="sxs-lookup"><span data-stu-id="f9492-117">Any time you want users to choose from a list of the YesNoIndicator entity's members, you can use the entity as a domain-based attribute.</span></span>

## <a name="domain-based-attributes-form-derived-hierarchies"></a><span data-ttu-id="f9492-118">Les attributs basés sur un domaine forment les hiérarchies dérivées</span><span class="sxs-lookup"><span data-stu-id="f9492-118">Domain-Based Attributes Form Derived Hierarchies</span></span>
 <span data-ttu-id="f9492-119">Les relations d'attributs basés sur un domaine sont à la base des hiérarchies dérivées.</span><span class="sxs-lookup"><span data-stu-id="f9492-119">Domain-based attribute relationships are the basis for derived hierarchies.</span></span> <span data-ttu-id="f9492-120">Pour plus d’informations, consultez [Hiérarchies dérivées &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f9492-120">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span></span>

## <a name="related-tasks"></a><span data-ttu-id="f9492-121">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="f9492-121">Related Tasks</span></span>

|<span data-ttu-id="f9492-122">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="f9492-122">Task Description</span></span>|<span data-ttu-id="f9492-123">Rubrique</span><span class="sxs-lookup"><span data-stu-id="f9492-123">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="f9492-124">Créer un attribut basé sur un domaine qui provient d'une entité existante.</span><span class="sxs-lookup"><span data-stu-id="f9492-124">Create a new domain-based attribute that is sourced from an existing entity.</span></span>|[<span data-ttu-id="f9492-125">Créer un attribut basé sur un domaine &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f9492-125">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)|
|<span data-ttu-id="f9492-126">Créez une entité.</span><span class="sxs-lookup"><span data-stu-id="f9492-126">Create a new entity.</span></span>|[<span data-ttu-id="f9492-127">Créer une entité &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f9492-127">Create an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-entity-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="f9492-128">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="f9492-128">Related Content</span></span>

-   [<span data-ttu-id="f9492-129">Hiérarchies dérivées &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f9492-129">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="f9492-130">Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f9492-130">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="f9492-131">Entités &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f9492-131">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)


