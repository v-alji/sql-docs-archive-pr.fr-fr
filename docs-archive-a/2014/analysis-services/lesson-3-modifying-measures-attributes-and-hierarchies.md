---
title: 'Leçon 3 : modification des mesures, des attributs et des hiérarchies | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 17d243cb-9bfb-43d7-8e6f-4d601fd62150
author: minewiskan
ms.author: owend
ms.openlocfilehash: c410136540a0ba85d50fbabc8b2d3c52be1823f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611382"
---
# <a name="lesson-3-modifying-measures-attributes-and-hierarchies"></a><span data-ttu-id="adf1e-102">Leçon 3 : Modification des mesures, des attributs et des hiérarchies</span><span class="sxs-lookup"><span data-stu-id="adf1e-102">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>
  <span data-ttu-id="adf1e-103">Après avoir défini votre cube initial, vous êtes prêt à améliorer son utilité et sa convivialité.</span><span class="sxs-lookup"><span data-stu-id="adf1e-103">After defining your initial cube, you are ready to improve the usefulness and friendliness of the cube.</span></span> <span data-ttu-id="adf1e-104">Pour ce faire, ajoutez des hiérarchies qui prennent en charge la navigation et l'agrégation à différents niveaux, appliquez des formats à la mesure spécifique et définissez des calculs et des relations.</span><span class="sxs-lookup"><span data-stu-id="adf1e-104">You can do this by adding hierarchies that support navigation and aggregation at various levels, by applying formats to specific measure, and by defining calculations and relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="adf1e-105">Les projets achevés de toutes les leçons de ce didacticiel sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="adf1e-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="adf1e-106">Vous pouvez sauter des leçons en utilisant le projet achevé de la leçon précédente comme point de départ.</span><span class="sxs-lookup"><span data-stu-id="adf1e-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="adf1e-107">[Cliquez ici](https://go.microsoft.com/fwlink/?LinkID=221866) pour télécharger les exemples de projet de ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="adf1e-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="adf1e-108">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="adf1e-108">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="adf1e-109">Modification des mesures</span><span class="sxs-lookup"><span data-stu-id="adf1e-109">Modifying Measures</span></span>](lesson-3-1-modifying-measures.md)  
 <span data-ttu-id="adf1e-110">Au cours de cette tâche, vous allez spécifier des propriétés de formatage pour les mesures relatives aux devises et aux pourcentages dans le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="adf1e-110">In this task, you specify formatting properties for the currency and percentage measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
 [<span data-ttu-id="adf1e-111">Modification de la dimension Customer</span><span class="sxs-lookup"><span data-stu-id="adf1e-111">Modifying the Customer Dimension</span></span>](lesson-3-2-modifying-the-customer-dimension.md)  
 <span data-ttu-id="adf1e-112">Au cours de cette tâche, vous allez définir une hiérarchie utilisateur, créer des calculs nommés, modifier des attributs pour utiliser des calculs nommés et grouper des hiérarchies d'attributs et des hiérarchies utilisateur dans des dossiers d'affichage.</span><span class="sxs-lookup"><span data-stu-id="adf1e-112">In this task, you define a user hierarchy, create named calculations, modify attributes to use named calculations, and group attributes and user hierarchies into display folders.</span></span>  
  
 [<span data-ttu-id="adf1e-113">Modification de la dimension Product</span><span class="sxs-lookup"><span data-stu-id="adf1e-113">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
 <span data-ttu-id="adf1e-114">Au cours de cette tâche, vous allez définir une nouvelle hiérarchie utilisateur, créer des calculs nommés, définir le nom de membre All et définir des dossiers d'affichage.</span><span class="sxs-lookup"><span data-stu-id="adf1e-114">In this task, you define a user hierarchy, create named calculations, define the All member name, and define display folders.</span></span>  
  
 [<span data-ttu-id="adf1e-115">Modification de la dimension Date</span><span class="sxs-lookup"><span data-stu-id="adf1e-115">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
 <span data-ttu-id="adf1e-116">Au cours de cette tâche, vous allez définir une hiérarchie utilisateur, modifier des noms de membres d'attribut et utiliser des clés composites pour spécifier des membres d'attribut unique.</span><span class="sxs-lookup"><span data-stu-id="adf1e-116">In this task, you define a user hierarchy, modify attribute member names, and use composite keys to specify unique attribute members.</span></span>  
  
 [<span data-ttu-id="adf1e-117">Exploration du cube déployé</span><span class="sxs-lookup"><span data-stu-id="adf1e-117">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
 <span data-ttu-id="adf1e-118">Au cours de cette tâche, vous allez parcourir les données du cube à l'aide du navigateur du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="adf1e-118">In this task, you browse cube data by using the browser in Cube Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adf1e-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="adf1e-119">See Also</span></span>  
 <span data-ttu-id="adf1e-120">[Scénario du didacticiel Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="adf1e-120">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="adf1e-121">Modélisation multidimensionnelle &#40;didacticiel Adventure Works&#41;</span><span class="sxs-lookup"><span data-stu-id="adf1e-121">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
