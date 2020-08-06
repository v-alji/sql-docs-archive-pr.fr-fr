---
title: 'Leçon 3 : ajout et traitement de modèles | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: cc29927a-c368-4b8a-bbd0-af89a9f54dc9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 5da034089d8bbe7f1a967258d195a56ddbf13c03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601197"
---
# <a name="lesson-3-adding-and-processing-models"></a><span data-ttu-id="ba21c-102">Leçon 3 : Ajout et traitement des modèles</span><span class="sxs-lookup"><span data-stu-id="ba21c-102">Lesson 3: Adding and Processing Models</span></span>
  <span data-ttu-id="ba21c-103">La structure d'exploration de données initiale que vous avez créée au cours de la leçon précédente contient un modèle d'exploration de données unique qui est basé sur l'algorithme MDT ([!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees).</span><span class="sxs-lookup"><span data-stu-id="ba21c-103">The mining structure that you created in the previous lesson contains a single mining model that is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="ba21c-104">Vous pouvez utiliser ce modèle pour identifier les clients pour la campagne de publipostage ciblée.</span><span class="sxs-lookup"><span data-stu-id="ba21c-104">You can use this model to identify customers for the targeted mailing campaign.</span></span> <span data-ttu-id="ba21c-105">Cependant, pour garantir que votre analyse est complète, il est recommandé de créer des modèles associés à l'aide de différents algorithmes et de comparer leurs résultats.</span><span class="sxs-lookup"><span data-stu-id="ba21c-105">However, to ensure that your analysis is thorough, it is a common practice to create related models using different algorithms and compare their results.</span></span> <span data-ttu-id="ba21c-106">De cette façon vous pouvez également obtenir différentes analyses.</span><span class="sxs-lookup"><span data-stu-id="ba21c-106">That way you can get different insights as well.</span></span> <span data-ttu-id="ba21c-107">Par conséquent, vous allez créer deux modèles, puis les traiter et les déployer.</span><span class="sxs-lookup"><span data-stu-id="ba21c-107">Therefore, you will create two additional models, then process and deploy the models.</span></span>  
  
 <span data-ttu-id="ba21c-108">Dans cette leçon, vous allez créer un ensemble de modèles d'exploration de données qui aideront à trouver les clients probables parmi la liste des clients potentiels.</span><span class="sxs-lookup"><span data-stu-id="ba21c-108">In this lesson, you will create a set of mining models that will suggest the most likely customers from a list of potential customers.</span></span>  
  
 <span data-ttu-id="ba21c-109">Pour effectuer les tâches de cette leçon, vous allez utiliser l’algorithme de gestion de [clusters Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) et l' [algorithme Microsoft Naive Bayes](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="ba21c-109">To complete the tasks in this lesson, you will use the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and the [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="ba21c-110">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba21c-110">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="ba21c-111">Ajout de nouveaux modèles à la structure de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ba21c-111">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="ba21c-112">Traitement des modèles dans la structure de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ba21c-112">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="ba21c-113">Première tâche de la leçon</span><span class="sxs-lookup"><span data-stu-id="ba21c-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="ba21c-114">Ajout de nouveaux modèles à la structure de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ba21c-114">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="ba21c-115">Leçon précédente</span><span class="sxs-lookup"><span data-stu-id="ba21c-115">Previous Lesson</span></span>  
 [<span data-ttu-id="ba21c-116">Leçon 2 : création d’une structure de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ba21c-116">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="ba21c-117">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="ba21c-117">Next Lesson</span></span>  
 [<span data-ttu-id="ba21c-118">Leçon 4 : exploration des modèles de publipostage ciblés &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ba21c-118">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba21c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba21c-119">See Also</span></span>  
 [<span data-ttu-id="ba21c-120">Ajouter des modèles d’exploration de données à une structure &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="ba21c-120">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md)  
  
  
