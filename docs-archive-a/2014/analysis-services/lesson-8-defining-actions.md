---
title: 'Leçon 8 : définition des actions | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 15459396-83c9-48a0-b10a-99ae38768c79
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4d4daaed3f1992478b309529fc15e2e903a27920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705687"
---
# <a name="lesson-8-defining-actions"></a><span data-ttu-id="b0a06-102">Leçon 8 : Définition des actions</span><span class="sxs-lookup"><span data-stu-id="b0a06-102">Lesson 8: Defining Actions</span></span>
  <span data-ttu-id="b0a06-103">Dans cette leçon, vous allez apprendre à définir des actions dans votre projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0a06-103">In this lesson, you will learn to define actions in your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="b0a06-104">Une action est simplement une instruction MDX (Multidimensional Expressions) qui est stockée dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et peut être incorporée dans des applications clientes et démarrée par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b0a06-104">An action is just a Multidimensional Expressions (MDX) statement that is stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and which can be incorporated into client applications and started by a user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0a06-105">Les projets achevés de toutes les leçons de ce didacticiel sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="b0a06-105">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="b0a06-106">Vous pouvez sauter des leçons en utilisant le projet achevé de la leçon précédente comme point de départ.</span><span class="sxs-lookup"><span data-stu-id="b0a06-106">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="b0a06-107">[Cliquez ici](https://go.microsoft.com/fwlink/?LinkID=221866) pour télécharger les exemples de projet de ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="b0a06-107">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="b0a06-108">prend en charge les types d’actions décrits dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="b0a06-108">supports the types of actions that are described in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b0a06-109">CommandLine</span><span class="sxs-lookup"><span data-stu-id="b0a06-109">CommandLine</span></span>|<span data-ttu-id="b0a06-110">Exécute une commande à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="b0a06-110">Executes a command at the command prompt</span></span>|  
|<span data-ttu-id="b0a06-111">Dataset</span><span class="sxs-lookup"><span data-stu-id="b0a06-111">Dataset</span></span>|<span data-ttu-id="b0a06-112">Renvoie un groupe de données à une application cliente.</span><span class="sxs-lookup"><span data-stu-id="b0a06-112">Returns a dataset to a client application.</span></span>|  
|<span data-ttu-id="b0a06-113">Extraction</span><span class="sxs-lookup"><span data-stu-id="b0a06-113">Drillthrough</span></span>|<span data-ttu-id="b0a06-114">Retourne une instruction d'extraction comme expression que le client exécute pour retourner un ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="b0a06-114">Returns a drillthrough statement as an expression, which the client executes to return a rowset</span></span>|  
|<span data-ttu-id="b0a06-115">Html</span><span class="sxs-lookup"><span data-stu-id="b0a06-115">Html</span></span>|<span data-ttu-id="b0a06-116">Exécute un script HTML dans un navigateur Internet.</span><span class="sxs-lookup"><span data-stu-id="b0a06-116">Executes an HTML script in an Internet browser</span></span>|  
|<span data-ttu-id="b0a06-117">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="b0a06-117">Proprietary</span></span>|<span data-ttu-id="b0a06-118">Effectue une opération en utilisant une interface différente de celles répertoriées dans ce tableau.</span><span class="sxs-lookup"><span data-stu-id="b0a06-118">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="b0a06-119">Rapport</span><span class="sxs-lookup"><span data-stu-id="b0a06-119">Report</span></span>|<span data-ttu-id="b0a06-120">Soumet une demande paramétrable basée sur une URL à un serveur de rapports et renvoie un rapport à une application cliente.</span><span class="sxs-lookup"><span data-stu-id="b0a06-120">Submits a parameterized URL-based request to a report server and returns a report to a client application.</span></span>|  
|<span data-ttu-id="b0a06-121">Ensemble de lignes</span><span class="sxs-lookup"><span data-stu-id="b0a06-121">Rowset</span></span>|<span data-ttu-id="b0a06-122">Renvoie un ensemble de lignes à une application cliente.</span><span class="sxs-lookup"><span data-stu-id="b0a06-122">Returns a rowset to a client application.</span></span>|  
|<span data-ttu-id="b0a06-123">Instruction</span><span class="sxs-lookup"><span data-stu-id="b0a06-123">Statement</span></span>|<span data-ttu-id="b0a06-124">Exécute une commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="b0a06-124">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="b0a06-125">URL</span><span class="sxs-lookup"><span data-stu-id="b0a06-125">URL</span></span>|<span data-ttu-id="b0a06-126">Affiche une page web dynamique dans un navigateur Internet.</span><span class="sxs-lookup"><span data-stu-id="b0a06-126">Displays a dynamic Web page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="b0a06-127">Les actions permettent aux utilisateurs de démarrer une application ou d'effectuer d'autres étapes dans le contexte d'un élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b0a06-127">Actions let users start an application or perform other steps within the context of a selected item.</span></span> <span data-ttu-id="b0a06-128">Pour plus d’informations, consultez [Actions &#40;Analysis Services - Données multidimensionnelles&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Actions dans les modèles multidimensionnels](multidimensional-models/actions-in-multidimensional-models.md)</span><span class="sxs-lookup"><span data-stu-id="b0a06-128">For more information, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md), [Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0a06-129">Pour obtenir des exemples d'actions, consultez les exemples d'action de l'onglet Modèles du volet Outils de calcul ou dans les exemples de l'entrepôt de données [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW.</span><span class="sxs-lookup"><span data-stu-id="b0a06-129">For examples of actions, see the action examples on the Templates tab in the Calculation Tools pane or in the examples in the [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW sample data warehouse.</span></span> <span data-ttu-id="b0a06-130">Pour plus d’informations sur l’installation de cette base de données, consultez [Installer les exemples de données et de projets pour le didacticiel sur la modélisation multidimensionnelle Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="b0a06-130">For more information about installing this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>  
  
 <span data-ttu-id="b0a06-131">Cette leçon inclut la tâche suivante :</span><span class="sxs-lookup"><span data-stu-id="b0a06-131">This lesson includes the following task:</span></span>  
  
 [<span data-ttu-id="b0a06-132">Définition et utilisation d'une action d'extraction</span><span class="sxs-lookup"><span data-stu-id="b0a06-132">Defining and Using a Drillthrough Action</span></span>](lesson-8-1-defining-and-using-a-drillthrough-action.md)  
 <span data-ttu-id="b0a06-133">Dans cette tâche, vous définissez, utilisez puis modifiez une action d'extraction à travers la relation de dimension de fait que vous avez définie antérieurement dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="b0a06-133">In this task, you define, use, and then modify a drillthrough action through the fact dimension relationship that you defined earlier in this tutorial.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b0a06-134">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="b0a06-134">Next Lesson</span></span>  
 [<span data-ttu-id="b0a06-135">Leçon 9 : Définition de perspectives et de traductions</span><span class="sxs-lookup"><span data-stu-id="b0a06-135">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="b0a06-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0a06-136">See Also</span></span>  
 <span data-ttu-id="b0a06-137">[Scénario du didacticiel Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b0a06-137">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="b0a06-138">[La modélisation multidimensionnelle &#40;le didacticiel Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="b0a06-138">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="b0a06-139">[Actions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b0a06-139">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b0a06-140">Actions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="b0a06-140">Actions in Multidimensional Models</span></span>](multidimensional-models/actions-in-multidimensional-models.md)  
  
  
