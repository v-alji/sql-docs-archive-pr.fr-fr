---
title: 'Leçon 7 : définition d’indicateurs de performance clés (KPI) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 36d53770-294f-43ab-8850-15d5351ff60c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87df6fd91a66505f124144cafd9a44c6e5e70e85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698729"
---
# <a name="lesson-7-defining-key-performance-indicators-kpis"></a><span data-ttu-id="80bac-102">Leçon 7 : Définition d'indicateurs de performance clés</span><span class="sxs-lookup"><span data-stu-id="80bac-102">Lesson 7: Defining Key Performance Indicators (KPIs)</span></span>
  <span data-ttu-id="80bac-103">Dans cette leçon, vous allez apprendre à définir des indicateurs de performance clés (KPI, Key Performance Indicator) dans votre projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80bac-103">In this lesson, you learn to define Key Performance Indicators (KPIs) in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="80bac-104">Les indicateurs de performance clés fournissent une infrastructure pour définir des calculs côté serveur qui mesurent votre activité, et ils standardisent la façon d'afficher les informations résultantes.</span><span class="sxs-lookup"><span data-stu-id="80bac-104">KPIs provide a framework for defining server-side calculations that measure your business, and they standardize how the resulting information is displayed.</span></span> <span data-ttu-id="80bac-105">Les indicateurs de performance clés peuvent être affichés dans des rapports, des portails et des tableaux de bord, à travers des API d'accès aux données, des outils [!INCLUDE[msCoName](../includes/msconame-md.md)] et des outils de fournisseurs tiers.</span><span class="sxs-lookup"><span data-stu-id="80bac-105">KPIs can be displayed in reports, portals, and dashboards, through data access APIs, and through [!INCLUDE[msCoName](../includes/msconame-md.md)] tools and third-party tools.</span></span> <span data-ttu-id="80bac-106">Les indicateurs de performance clés sont des wrappers de métadonnées autour de mesures ordinaires et d'autres expressions MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="80bac-106">KPIs are metadata wrappers around regular measures and other Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="80bac-107">Pour plus d’informations, consultez [Indicateurs de performance clés &#40;KPI&#41; dans les modèles multidimensionnels](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="80bac-107">For more information, see [Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80bac-108">Les projets achevés de toutes les leçons de ce didacticiel sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="80bac-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="80bac-109">Vous pouvez sauter des leçons en utilisant le projet achevé de la leçon précédente comme point de départ.</span><span class="sxs-lookup"><span data-stu-id="80bac-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="80bac-110">[Cliquez ici](https://go.microsoft.com/fwlink/?LinkID=221866) pour télécharger les exemples de projet de ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="80bac-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="80bac-111">Cette leçon contient la tâche suivante :</span><span class="sxs-lookup"><span data-stu-id="80bac-111">This lesson contains the following task:</span></span>  
  
 [<span data-ttu-id="80bac-112">Définition et exploration d’indicateurs de performance clés</span><span class="sxs-lookup"><span data-stu-id="80bac-112">Defining and Browsing KPIs</span></span>](lesson-7-1-defining-and-browsing-kpis.md)  
 <span data-ttu-id="80bac-113">Dans cette tâche, vous définissez des indicateurs de performance clés en mode Formulaire, puis vous passez au mode Navigateur pour parcourir les données du cube en utilisant les indicateurs de performance clés.</span><span class="sxs-lookup"><span data-stu-id="80bac-113">In this task, you define KPIs in the Form view and then switch to the Browser view to browse the cube data by using the KPIs.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="80bac-114">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="80bac-114">Next Lesson</span></span>  
 [<span data-ttu-id="80bac-115">Leçon 8 : Définition des actions</span><span class="sxs-lookup"><span data-stu-id="80bac-115">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)  
  
## <a name="see-also"></a><span data-ttu-id="80bac-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80bac-116">See Also</span></span>  
 <span data-ttu-id="80bac-117">[Scénario du didacticiel Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="80bac-117">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="80bac-118">[La modélisation multidimensionnelle &#40;le didacticiel Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="80bac-118">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="80bac-119">Indicateurs de performance clés &#40;KPI&#41; dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="80bac-119">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)  
  
  
