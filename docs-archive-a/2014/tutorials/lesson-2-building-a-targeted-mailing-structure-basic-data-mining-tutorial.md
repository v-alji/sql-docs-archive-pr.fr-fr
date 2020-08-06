---
title: 'Leçon 2 : création d’une structure de publipostage ciblée (didacticiel sur l’exploration de données de base) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d0d6ceb-49b5-47c7-9ee6-464da43cc1f6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 005baa09e802a9ffe98f87239070401f170ddfa9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600414"
---
# <a name="lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="ed917-102">Leçon 2 : création d'une structure de publipostage ciblé (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="ed917-102">Lesson 2: Building a Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="ed917-103">Le service marketing de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] souhaite augmenter les ventes en destinant à des clients spécifiques une campagne de publipostage.</span><span class="sxs-lookup"><span data-stu-id="ed917-103">The Marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to increase sales by targeting specific customers for a mailing campaign.</span></span> <span data-ttu-id="ed917-104">La base de données de l'entreprise contient une liste des clients passés et une liste des nouveaux clients potentiels.</span><span class="sxs-lookup"><span data-stu-id="ed917-104">The company's database contains a list of past customers and a list of potential new customers.</span></span> <span data-ttu-id="ed917-105">En étudiant les attributs de précédents clients, l'entreprise espère révéler des modèles, qu'elle pourra alors appliquer aux clients potentiels.</span><span class="sxs-lookup"><span data-stu-id="ed917-105">By investigating the attributes of previous customers, the company hopes to discover patterns that they can then apply to potential customers.</span></span> <span data-ttu-id="ed917-106">Par exemple, ils peuvent utiliser des tendances passées pour prédire quels clients potentiels sont les plus susceptibles d’acheter un vélo [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] , ou créer des segments de clientèle pour les futures campagnes marketing.</span><span class="sxs-lookup"><span data-stu-id="ed917-106">For example, they might use past trends to predict which potential customers are most likely to purchase a bike from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], or create customer segments for future marketing campaigns.</span></span>  
  
 <span data-ttu-id="ed917-107">Dans cette leçon, vous allez utiliser l' **Assistant Exploration de données** pour créer la structure de publipostage ciblée.</span><span class="sxs-lookup"><span data-stu-id="ed917-107">In this lesson you will use the **Data Mining Wizard** to create the targeted mailing structure.</span></span> <span data-ttu-id="ed917-108">Une fois les tâches de cette leçon complétées, vous aurez une structure d'exploration de données avec un modèle unique.</span><span class="sxs-lookup"><span data-stu-id="ed917-108">After you complete the tasks in this lesson, you will have a mining structure with a single model.</span></span> <span data-ttu-id="ed917-109">En raison des nombreuses étapes et concepts importants impliqués dans la création d'une structure, nous avons réparti ce processus dans les trois tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed917-109">Because there are many steps and important concepts involved in creating a structure, we have separated this process into the following three tasks:</span></span>  
  
 [<span data-ttu-id="ed917-110">Création d’une structure de modèle d’exploration de données de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ed917-110">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ed917-111">Spécification du type de données et du type de contenu &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ed917-111">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ed917-112">Spécification d’un jeu de données de test pour la structure &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ed917-112">Specifying a Testing Data Set for the Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="ed917-113">Première tâche de la leçon</span><span class="sxs-lookup"><span data-stu-id="ed917-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="ed917-114">Création d’une structure de modèle d’exploration de données de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ed917-114">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="ed917-115">Leçon précédente</span><span class="sxs-lookup"><span data-stu-id="ed917-115">Previous Lesson</span></span>  
 [<span data-ttu-id="ed917-116">Leçon 1 : préparation de la base de données Analysis Services &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ed917-116">Lesson 1: Preparing the Analysis Services Database &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial.md)  
  
## <a name="next--lesson"></a><span data-ttu-id="ed917-117">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="ed917-117">Next  Lesson</span></span>  
 [<span data-ttu-id="ed917-118">Leçon 3 : Ajout et traitement des modèles</span><span class="sxs-lookup"><span data-stu-id="ed917-118">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="ed917-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed917-119">See Also</span></span>  
 <span data-ttu-id="ed917-120">[Créer la structure d’exploration de données &#40;l’Assistant Exploration de données&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="ed917-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="ed917-121">Créer une structure d’exploration de données relationnelle</span><span class="sxs-lookup"><span data-stu-id="ed917-121">Create a Relational Mining Structure</span></span>](../../2014/analysis-services/data-mining/create-a-relational-mining-structure.md)  
  
  
