---
title: 'Leçon 4 : définition des attributs avancés et des propriétés de dimension | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e86b9be-e47d-4bb4-87eb-136ff3a61aef
author: minewiskan
ms.author: owend
ms.openlocfilehash: deb2d9c40ad5024f6cc4ba6e9148df41a168c6e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703387"
---
# <a name="lesson-4-defining-advanced-attribute-and-dimension-properties"></a><span data-ttu-id="b961c-102">Leçon 4 : Définition des attributs avancés et des propriétés de dimension</span><span class="sxs-lookup"><span data-stu-id="b961c-102">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>
  <span data-ttu-id="b961c-103">Au cours de cette leçon, vous allez apprendre à utiliser certaines propriétés avancées des attributs, hiérarchies d'attributs et propriétés de dimensions.</span><span class="sxs-lookup"><span data-stu-id="b961c-103">In this lesson, you will learn how to use some of the advanced properties of attributes, attribute hierarchies, and dimension properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b961c-104">Cette leçon est basée sur une version améliorée du projet de didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que vous avez créé au cours des trois premières leçons de ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="b961c-104">This lesson is based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons of this tutorial.</span></span> <span data-ttu-id="b961c-105">La première tâche de cette leçon explique où vous pouvez trouver l'exemple de projet à utiliser pour cette leçon et la différence qu'il existe entre ce projet et le projet que vous avez créé au cours des trois premières leçons.</span><span class="sxs-lookup"><span data-stu-id="b961c-105">The first task in this lesson describes where to locate the appropriate sample project to use for the lesson, and the difference between this project and the project that you created in the first three lessons.</span></span>  
  
 <span data-ttu-id="b961c-106">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="b961c-106">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="b961c-107">Utilisation d'une version modifiée du projet du didacticiel Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b961c-107">Using a Modified Version of the Analysis Services Tutorial Project</span></span>](lesson-4-1-using-a-modified-version-of-the-analysis-services-tutorial-project.md)  
 <span data-ttu-id="b961c-108">Au cours de cette tâche, vous allez ouvrir, vérifier et déployer une version modifiée du projet de didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , qui contient plusieurs groupes de mesures et dimensions supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="b961c-108">In this task, you open, review, and deploy a modified version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, which has multiple measure groups and additional dimensions.</span></span>  
  
 [<span data-ttu-id="b961c-109">Définition des propriétés d'attribut parent dans une hiérarchie parent-enfant</span><span class="sxs-lookup"><span data-stu-id="b961c-109">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md)  
 <span data-ttu-id="b961c-110">Au cours de cette tâche, vous allez définir des noms de niveaux dans une dimension parent-enfant et spécifier si les données associées aux membres parents doivent être affichées ou non.</span><span class="sxs-lookup"><span data-stu-id="b961c-110">In this task, you define level names in a parent-child dimension and specify whether data related to parent members is displayed.</span></span> <span data-ttu-id="b961c-111">Pour plus d’informations, consultez [hiérarchie parent-enfant](multidimensional-models/parent-child-dimension.md) et [attributs dans des hiérarchies de parent-enfant](multidimensional-models/parent-child-dimension-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b961c-111">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) and [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md).</span></span>  
  
 [<span data-ttu-id="b961c-112">Regroupement automatique des membres d'attribut</span><span class="sxs-lookup"><span data-stu-id="b961c-112">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)  
 <span data-ttu-id="b961c-113">Au cours de cette tâche, vous allez créer automatiquement des groupements de membres d'attributs en fonction de la distribution des membres dans la hiérarchie d'attributs.</span><span class="sxs-lookup"><span data-stu-id="b961c-113">In this task, you automatically create groupings of attribute members based on the distribution of the members within the attribute hierarchy.</span></span> <span data-ttu-id="b961c-114">Pour plus d’informations, consultez [Regrouper des membres d’un attribut &#40;discrétisation&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="b961c-114">For more information, see [Group Attribute Members &#40;Discretization&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span></span>  
  
 [<span data-ttu-id="b961c-115">Masquage et désactivation des hiérarchies d’attributs</span><span class="sxs-lookup"><span data-stu-id="b961c-115">Hiding and Disabling Attribute Hierarchies</span></span>](lesson-4-4-hiding-and-disabling-attribute-hierarchies.md)  
 <span data-ttu-id="b961c-116">Au cours de cette tâche, vous allez apprendre à désactiver ou à masquer les hiérarchies d'attributs et à quel moment le faire.</span><span class="sxs-lookup"><span data-stu-id="b961c-116">In this task, you learn how and when to disable or hide attribute hierarchies.</span></span>  
  
 [<span data-ttu-id="b961c-117">Tri des membres d’attribut sur la base d’un attribut secondaire</span><span class="sxs-lookup"><span data-stu-id="b961c-117">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)  
 <span data-ttu-id="b961c-118">Au cours de cette tâche, vous allez apprendre à trier les membres de la dimension sur la base d'un attribut secondaire, pour obtenir l'ordre de tri souhaité.</span><span class="sxs-lookup"><span data-stu-id="b961c-118">In this task, you learn how to sort dimension members based on a secondary attribute, to achieve the sort order that you want.</span></span>  
  
 [<span data-ttu-id="b961c-119">Spécification des relations d’attribut dans une hiérarchie définie par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="b961c-119">Specifying Attribute Relationships Between Attributes in a User-Defined Hierarchy</span></span>](4-6-specifying-attribute-relationships-in-user-defined-hierarchy.md)  
 <span data-ttu-id="b961c-120">Au cours de cette tâche, vous allez apprendre à définir les propriétés des membres pour les attributs et à spécifier les relations d’agrégation qui existent entre eux.</span><span class="sxs-lookup"><span data-stu-id="b961c-120">In this task, you learn how to define member properties for attributes and to specify aggregation relationships between them.</span></span> <span data-ttu-id="b961c-121">Pour plus d’informations, consultez [définir des relations d’attributs](multidimensional-models/attribute-relationships-define.md) et des propriétés de [hiérarchie utilisateur](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b961c-121">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [User Hierarchy Properties](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span></span>  
  
 [<span data-ttu-id="b961c-122">Définition du membre inconnu et des propriétés de traitement Null</span><span class="sxs-lookup"><span data-stu-id="b961c-122">Defining the Unknown Member and Null Processing Properties</span></span>](lesson-4-7-defining-the-unknown-member-and-null-processing-properties.md)  
 <span data-ttu-id="b961c-123">Au cours de cette tâche, vous allez configurer les propriétés UnknownMember et UnknownMemberName pour gérer les conditions d’erreur causées par des membres de la dimension NULL.</span><span class="sxs-lookup"><span data-stu-id="b961c-123">In this task, you configure the UnknownMember and UnknownMemberName properties to handle error conditions caused by null dimension members.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b961c-124">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="b961c-124">Next Lesson</span></span>  
 [<span data-ttu-id="b961c-125">Leçon 5 : définition des relations entre les dimensions et les groupes de mesures</span><span class="sxs-lookup"><span data-stu-id="b961c-125">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>](lesson-5-defining-relationships-between-dimensions-and-measure-groups.md)  
  
## <a name="see-also"></a><span data-ttu-id="b961c-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b961c-126">See Also</span></span>  
 <span data-ttu-id="b961c-127">[Scénario du didacticiel Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b961c-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="b961c-128">[La modélisation multidimensionnelle &#40;le didacticiel Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="b961c-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="b961c-129">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="b961c-129">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
