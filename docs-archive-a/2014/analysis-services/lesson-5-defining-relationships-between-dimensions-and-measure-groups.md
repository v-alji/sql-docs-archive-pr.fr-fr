---
title: 'Leçon 5 : définition des relations entre les dimensions et les groupes de mesures | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 31aeb271-47a1-433b-a8a5-120bcb4584d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6dbdf20e64e3cd8adc751b69122a380d7b3b3648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604242"
---
# <a name="lesson-5-defining-relationships-between-dimensions-and-measure-groups"></a><span data-ttu-id="cee90-102">Leçon 5 : Définition des relations entre les dimensions et les groupes de mesures</span><span class="sxs-lookup"><span data-stu-id="cee90-102">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>
  <span data-ttu-id="cee90-103">Au cours des leçons précédentes de ce didacticiel, vous avez appris que des dimensions de base de données ajoutées à un cube pouvaient être utilisées comme base pour une ou plusieurs dimensions de cube.</span><span class="sxs-lookup"><span data-stu-id="cee90-103">In the previous lessons in this tutorial, you learned that database dimensions added to a cube can be used as the basis for one or more cube dimensions.</span></span> <span data-ttu-id="cee90-104">Au cours de cette leçon, vous allez apprendre à définir différents types de relations entre des dimensions de cube et des groupes de mesures et à spécifier les propriétés de ces relations.</span><span class="sxs-lookup"><span data-stu-id="cee90-104">In this lesson, you learn to define different types of relationships between cube dimensions and measure groups, and to specify the properties of these relationships.</span></span>  
  
 <span data-ttu-id="cee90-105">Pour plus d’informations, consultez [Relations de dimension](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="cee90-105">For more information, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cee90-106">Les projets achevés de toutes les leçons de ce didacticiel sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="cee90-106">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="cee90-107">Vous pouvez sauter des leçons en utilisant le projet achevé de la leçon précédente comme point de départ.</span><span class="sxs-lookup"><span data-stu-id="cee90-107">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="cee90-108">[Cliquez ici](https://go.microsoft.com/fwlink/?LinkID=221866) pour télécharger les exemples de projet de ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="cee90-108">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="cee90-109">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="cee90-109">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="cee90-110">Définition d’une relation référencée</span><span class="sxs-lookup"><span data-stu-id="cee90-110">Defining a Referenced Relationship</span></span>](lesson-5-1-defining-a-referenced-relationship.md)  
 <span data-ttu-id="cee90-111">Dans cette tâche, vous allez apprendre à lier une dimension à une table de faits indirectement par le biais d’une dimension qui est liée directement par le biais d’une relation clé primaire-clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="cee90-111">In this task, you learn to link a dimension to a fact table indirectly through a dimension that is linked directly through a primary key-foreign key relationship.</span></span>  
  
 [<span data-ttu-id="cee90-112">Définition d'une relation de faits</span><span class="sxs-lookup"><span data-stu-id="cee90-112">Defining a Fact Relationship</span></span>](lesson-5-2-defining-a-fact-relationship.md)  
 <span data-ttu-id="cee90-113">Au cours de cette tâche, vous allez apprendre à définir une dimension basée sur des données de la table de faits et à définir la relation de dimensions comme relation de faits.</span><span class="sxs-lookup"><span data-stu-id="cee90-113">In this task, you learn to define a dimension based on data in the fact table, and to define the dimension relationship as a fact relationship.</span></span>  
  
 [<span data-ttu-id="cee90-114">Définition d’une relation plusieurs-à-plusieurs</span><span class="sxs-lookup"><span data-stu-id="cee90-114">Defining a Many-to-Many Relationship</span></span>](lesson-5-3-defining-a-many-to-many-relationship.md)  
 <span data-ttu-id="cee90-115">Au cours de cette tâche, vous allez apprendre à lier un fait à plusieurs membres de dimensions par la définition d'une relation plusieurs-à-plusieurs entre des tables de dimensions et des tables de faits.</span><span class="sxs-lookup"><span data-stu-id="cee90-115">In this task, you learn to relate a fact to multiple dimension members through the definition of a many-to-many relationship between dimension tables and fact tables.</span></span>  
  
 [<span data-ttu-id="cee90-116">Définition de la granularité des dimensions dans un groupe de mesures</span><span class="sxs-lookup"><span data-stu-id="cee90-116">Defining Dimension Granularity within a Measure Group</span></span>](lesson-5-4-defining-dimension-granularity-within-a-measure-group.md)  
 <span data-ttu-id="cee90-117">Au cours de cette tâche, vous allez apprendre à modifier la granularité d'une dimension pour un groupe de mesures spécifique.</span><span class="sxs-lookup"><span data-stu-id="cee90-117">In this task, you learn to modify the granularity of a dimension for a specific measure group.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="cee90-118">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="cee90-118">Next Lesson</span></span>  
 [<span data-ttu-id="cee90-119">Leçon 6 : définition de calculs</span><span class="sxs-lookup"><span data-stu-id="cee90-119">Lesson 6: Defining Calculations</span></span>](lesson-6-defining-calculations.md)  
  
## <a name="see-also"></a><span data-ttu-id="cee90-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cee90-120">See Also</span></span>  
 <span data-ttu-id="cee90-121">[Scénario du didacticiel Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cee90-121">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="cee90-122">[La modélisation multidimensionnelle &#40;le didacticiel Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="cee90-122">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="cee90-123">Relations de dimension</span><span class="sxs-lookup"><span data-stu-id="cee90-123">Dimension Relationships</span></span>](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md)  
  
  
