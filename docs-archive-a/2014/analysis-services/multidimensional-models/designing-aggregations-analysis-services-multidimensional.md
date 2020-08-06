---
title: Conception d’agrégations (Analysis Services, multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- aggregations [Analysis Services], partitions
- partitions [Analysis Services], aggregations
ms.assetid: 3072b7e0-6961-42ad-a287-16f391f2cec4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 18d8ea1adb645868a11b70966ba3be2ed1764fbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614204"
---
# <a name="designing-aggregations-analysis-services---multidimensional"></a><span data-ttu-id="4de5b-102">Conception d'agrégations (Analysis Services - Multidimensionnel)</span><span class="sxs-lookup"><span data-stu-id="4de5b-102">Designing Aggregations (Analysis Services - Multidimensional)</span></span>
  <span data-ttu-id="4de5b-103">Les agrégations sont des résumés précalculés de données de cubes qui permettent à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de fournir des réponses rapides à des requêtes.</span><span class="sxs-lookup"><span data-stu-id="4de5b-103">Aggregations are precalculated summaries of cube data that help enable [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to provide rapid query responses.</span></span>  
  
 <span data-ttu-id="4de5b-104">Pour définir des options de stockage et concevoir des agrégations pour une partition, utilisez l'Assistant Conception d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="4de5b-104">To set storage options and design aggregations for a partition, use the Aggregation Design Wizard.</span></span> <span data-ttu-id="4de5b-105">Cet Assistant agit sur une seule partition d'un groupe de mesures à la fois, ce qui vous permet de sélectionner différentes options et configurations pour chaque partition.</span><span class="sxs-lookup"><span data-stu-id="4de5b-105">The wizard operates on a single partition of a measure group at a time so that you can select different options and designs for each partition.</span></span> <span data-ttu-id="4de5b-106">L'Assistant vous aide à configurer les options de stockage et à concevoir des agrégations pour une partition.</span><span class="sxs-lookup"><span data-stu-id="4de5b-106">The wizard takes you through steps to configure storage and design aggregation for a partition.</span></span> <span data-ttu-id="4de5b-107">Pour plus d'informations sur la configuration du stockage, consultez.</span><span class="sxs-lookup"><span data-stu-id="4de5b-107">For more information about configuring storage, see.</span></span>  
  
 <span data-ttu-id="4de5b-108">Sélectionnez une méthode pour contrôler le nombre d'agrégations que l'Assistant va concevoir, puis laissez celui-ci créer les agrégations.</span><span class="sxs-lookup"><span data-stu-id="4de5b-108">Select a method for controlling the number of aggregations the wizard will design, and then let the wizard design the aggregations.</span></span>  
  
 <span data-ttu-id="4de5b-109">L'objectif est de concevoir le nombre d'agrégations optimal.</span><span class="sxs-lookup"><span data-stu-id="4de5b-109">The goal is to design the optimal number of aggregations.</span></span> <span data-ttu-id="4de5b-110">Non seulement ce nombre doit fournir un temps de réponse satisfaisant, mais il doit également empêcher la formation de partitions de trop grande taille.</span><span class="sxs-lookup"><span data-stu-id="4de5b-110">This number should not only provide satisfactory response time, but also prevent excessive partition size.</span></span> <span data-ttu-id="4de5b-111">Un plus grand nombre d'agrégations permet des temps de réponse plus rapides, mais requiert aussi plus d'espace de stockage et peut mettre plus de temps à calculer.</span><span class="sxs-lookup"><span data-stu-id="4de5b-111">A greater number of aggregations produces faster response times but it also requires more storage space and may take longer to compute.</span></span> <span data-ttu-id="4de5b-112">De plus, comme l'Assistant conçoit de plus en plus d'agrégations, les agrégations créées antérieurement produisent des gains de performance beaucoup plus importants par rapport à celles qui sont créées plus tard.</span><span class="sxs-lookup"><span data-stu-id="4de5b-112">Moreover, as the wizard designs more and more aggregations, earlier aggregations produce considerably larger performance gains than later aggregations.</span></span> <span data-ttu-id="4de5b-113">La réduction des agrégations moins utiles augmente aussi les performances.</span><span class="sxs-lookup"><span data-stu-id="4de5b-113">Reduction in less useful aggregations increases performance as well.</span></span> <span data-ttu-id="4de5b-114">Vous pouvez contrôler le nombre d'agrégations que l'Assistant conçoit à l'aide de l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4de5b-114">You can control the number of aggregations the wizard designs by one of the following methods available in the wizard:</span></span>  
  
-   <span data-ttu-id="4de5b-115">spécifiez une limite pour l'espace de stockage réservé aux agrégations ;</span><span class="sxs-lookup"><span data-stu-id="4de5b-115">Specify a storage space limit for the aggregations.</span></span>  
  
-   <span data-ttu-id="4de5b-116">spécifiez une limite pour les gains de performance ;</span><span class="sxs-lookup"><span data-stu-id="4de5b-116">Specify a performance gain limit.</span></span>  
  
-   <span data-ttu-id="4de5b-117">arrêtez manuellement l'Assistant lorsque la courbe Performance/Taille affichée commence à présenter un niveau de gain de performance acceptable ;</span><span class="sxs-lookup"><span data-stu-id="4de5b-117">Stop the wizard manually when the displayed performance versus size curve starts to level off at an acceptable performance gain.</span></span>  
  
-   <span data-ttu-id="4de5b-118">décidez de ne pas concevoir d'agrégations.</span><span class="sxs-lookup"><span data-stu-id="4de5b-118">Choose not to design aggregations.</span></span>  
  
 <span data-ttu-id="4de5b-119">Pour configurer les options de stockage, l'Assistant doit être en mesure de se connecter à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="4de5b-119">To design storage, the wizard must be able to connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on the target server.</span></span> <span data-ttu-id="4de5b-120">L'Assistant renvoie un message d'erreur si [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] n'est pas en cours d'exécution sur le serveur cible ou si le processus de configuration du stockage ne parvient pas à se connecter au serveur cible.</span><span class="sxs-lookup"><span data-stu-id="4de5b-120">The wizard will display an error message if [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not running on the target server or if the storage design process is otherwise unable to connect to the target server.</span></span>  
  
 <span data-ttu-id="4de5b-121">L'étape finale de l'Assistant vous permet de lancer le traitement ou de le différer.</span><span class="sxs-lookup"><span data-stu-id="4de5b-121">The final step of the wizard allows you to process or defer processing.</span></span> <span data-ttu-id="4de5b-122">Le traitement crée les agrégations conçues avec l'Assistant, tandis que l'ajournement du traitement enregistre les agrégations conçues en vue d'un traitement ultérieur, ce qui permet de poursuivre le travail de conception sans devoir effectuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="4de5b-122">Processing creates the aggregations you design with the wizard, while deferring processing saves the designed aggregations for future processing, thus allowing design activities to continue without processing.</span></span> <span data-ttu-id="4de5b-123">Selon la taille de la partition, le traitement peut durer très longtemps.</span><span class="sxs-lookup"><span data-stu-id="4de5b-123">Depending on the size of the partition, processing may take considerable time.</span></span> <span data-ttu-id="4de5b-124">Si vous le souhaitez, vous pouvez interrompre le traitement d'une partition.</span><span class="sxs-lookup"><span data-stu-id="4de5b-124">If you choose, you can interrupt processing a partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de5b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4de5b-125">See Also</span></span>  
 [<span data-ttu-id="4de5b-126">Agrégations et conceptions d'agrégation</span><span class="sxs-lookup"><span data-stu-id="4de5b-126">Aggregations and Aggregation Designs</span></span>](../multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
