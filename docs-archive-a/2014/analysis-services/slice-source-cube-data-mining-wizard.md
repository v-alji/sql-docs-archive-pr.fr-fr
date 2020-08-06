---
title: Découper le cube source (Assistant Exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.slicesourcecube.f1
ms.assetid: 16485608-d3b9-49ee-8baa-948038cdd7ec
author: minewiskan
ms.author: owend
ms.openlocfilehash: 762248d4c2a268ac36b0dfa3ffeba20123017017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705483"
---
# <a name="slice-source-cube-data-mining-wizard"></a><span data-ttu-id="8b00a-102">Découper le cube source (Assistant Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="8b00a-102">Slice Source Cube (Data Mining Wizard)</span></span>
  <span data-ttu-id="8b00a-103">Utilisez la boîte de dialogue **Découper le cube source** afin de limiter les données utilisées pour effectuer l'apprentissage du modèle.</span><span class="sxs-lookup"><span data-stu-id="8b00a-103">You can use the **Slice Source Cube** dialog box to restrict the data used to train the model.</span></span> <span data-ttu-id="8b00a-104">Généralement, un cube contient les données relatives à plusieurs dimensions et attributs différents, tels que tous les magasins, toutes les régions et tous les produits.</span><span class="sxs-lookup"><span data-stu-id="8b00a-104">Typically a cube contains data related to many different dimensions and attributes, such as all stores, all regions, and all products.</span></span> <span data-ttu-id="8b00a-105">Il n'est pas pratique d'effectuer l'apprentissage d'un modèle sur des combinaisons illimitées d'attributs. C'est pourquoi, vous utilisez cette boîte de dialogue pour choisir un ensemble spécifique à utiliser dans l'apprentissage d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="8b00a-105">It is not practical to train a model on unlimited combinations of attributes, so you use this dialog box to choose a specific set to use in training a model.</span></span>  
  
 <span data-ttu-id="8b00a-106">Par exemple, dans le cube AdventureWorks, vous pouvez segmenter par ligne de produits, région ou année, pour obtenir une partie des données.</span><span class="sxs-lookup"><span data-stu-id="8b00a-106">For example, in the AdventureWorks cube, you might slice by a particular product line, region, or year, to get a portion of the data.</span></span>  
  
 <span data-ttu-id="8b00a-107">Si vous n'êtes pas familiarisé avec les tranches et les cubes, nous vous recommandons de consulter les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="8b00a-107">If you are unfamiliar with slices and cubes, we recommend that you review these articles:</span></span>  
  
-   [<span data-ttu-id="8b00a-108">Définissez la propriété tranche de partition &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8b00a-108">Set the Partition Slice Property &#40;Analysis Services&#41;</span></span>](multidimensional-models/set-the-partition-slice-property-analysis-services.md)  
  
-   [<span data-ttu-id="8b00a-109">Créer et gérer une partition locale &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8b00a-109">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](multidimensional-models/create-and-manage-a-local-partition-analysis-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="8b00a-110">Notez que les fonctions MDX dynamiques (telles que [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) ou [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) ne sont pas prises en charge dans la propriété Slice des partitions.</span><span class="sxs-lookup"><span data-stu-id="8b00a-110">Note that dynamic MDX functions (such as [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) or [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) are not supported in the Slice property for partitions.</span></span> <span data-ttu-id="8b00a-111">Vous devez définir la tranche à l'aide de tuples explicites ou de références à des membres.</span><span class="sxs-lookup"><span data-stu-id="8b00a-111">You must define the slice by using explicit tuples or member references.</span></span>  
>   
>  <span data-ttu-id="8b00a-112">Par exemple, plutôt que d’utiliser [: &#40;plage&#41; &#40;&#41;MDX](/sql/mdx/range-mdx) pour définir une plage, vous devez énumérer chaque membre par année spécifique.</span><span class="sxs-lookup"><span data-stu-id="8b00a-112">For example, rather than using  [: &#40;Range&#41; &#40;MDX&#41;](/sql/mdx/range-mdx) to define a range, you would need to enumerate each member by the specific years.</span></span>  
>   
>  <span data-ttu-id="8b00a-113">Si vous devez définir une tranche complexe, nous vous recommandons de définir les tuples de la tranche en utilisant un script XMLA Alter.</span><span class="sxs-lookup"><span data-stu-id="8b00a-113">If you need to define a complex slice, we recommend that you define the tuples in the slice by using an XMLA Alter script.</span></span> <span data-ttu-id="8b00a-114">Ensuite, vous pouvez utiliser l'outil en ligne de commande ascmd ou la [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) SSIS pour exécuter le script et créer le jeu de membres spécifié juste avant de traiter la partition.</span><span class="sxs-lookup"><span data-stu-id="8b00a-114">Then, you can use either the ascmd command-line tool or the SSIS [Analysis Services Execute DDL Task](../integration-services/control-flow/analysis-services-execute-ddl-task.md) to run the script and create the specified set of members immediately before you process the partition.</span></span>  
  
 <span data-ttu-id="8b00a-115">**Pour plus d’informations :** [Assistant Exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Créer une structure d’exploration de données relationnelle](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="8b00a-115">**For More Information:** [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="8b00a-116">Options</span><span class="sxs-lookup"><span data-stu-id="8b00a-116">Options</span></span>  
 <span data-ttu-id="8b00a-117">**Dimension**</span><span class="sxs-lookup"><span data-stu-id="8b00a-117">**Dimension**</span></span>  
 <span data-ttu-id="8b00a-118">Sélectionnez la dimension que vous voulez découper.</span><span class="sxs-lookup"><span data-stu-id="8b00a-118">Select the dimension that you want to slice.</span></span>  
  
 <span data-ttu-id="8b00a-119">**Hierarchy**</span><span class="sxs-lookup"><span data-stu-id="8b00a-119">**Hierarchy**</span></span>  
 <span data-ttu-id="8b00a-120">Sélectionnez la hiérarchie que vous voulez découper.</span><span class="sxs-lookup"><span data-stu-id="8b00a-120">Select the hierarchy that you want to slice.</span></span> <span data-ttu-id="8b00a-121">Choisissez n'importe quel niveau d'une hiérarchie, mais les attributs utilisés dans le modèle seront uniquement au niveau choisi.</span><span class="sxs-lookup"><span data-stu-id="8b00a-121">You can choose any level of a hierarchy, but the attributes used in the model will be only at the level that you choose.</span></span>  
  
 <span data-ttu-id="8b00a-122">Par exemple, si vous choisissez la hiérarchie Geography, et sélectionnez le niveau Country, vous ne pouvez pas créer de modèle qui utilise City comme attribut.</span><span class="sxs-lookup"><span data-stu-id="8b00a-122">For example, if you choose the Geography hierarchy, and select Country as the level, you cannot build a model that uses City as the attributes.</span></span> <span data-ttu-id="8b00a-123">À l'inverse, si vous choisissez City comme niveau de la hiérarchie sur laquelle vous souhaitez découper, vous ne pouvez pas créer de modèle d'exploration de données reposant sur Country.</span><span class="sxs-lookup"><span data-stu-id="8b00a-123">Conversely, if you choose City as the level of the hierarchy on which to slice, you cannot create a mining model based on Country.</span></span>  
  
 <span data-ttu-id="8b00a-124">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="8b00a-124">**Operator**</span></span>  
 <span data-ttu-id="8b00a-125">Sélectionner l'opérateur à utiliser lors de la création une expression de tranche.</span><span class="sxs-lookup"><span data-stu-id="8b00a-125">Select the operator to use in building a slice expression.</span></span>  
  
 <span data-ttu-id="8b00a-126">Par exemple, si vous choisissez la hiérarchie Geography, vous pouvez sélectionner l’opérateur =, puis taper « Europe » comme filtre, pour obtenir les données du cube pour l’Europe uniquement.</span><span class="sxs-lookup"><span data-stu-id="8b00a-126">For example, if you chose Geography as the hierarchy, you could select the operator = and then type "Europe" as the filter, to get cube data for Europe only.</span></span>  
  
 <span data-ttu-id="8b00a-127">**Expression de filtre**</span><span class="sxs-lookup"><span data-stu-id="8b00a-127">**Filter Expression**</span></span>  
 <span data-ttu-id="8b00a-128">Entrez une expression à utiliser comme critère lors du filtrage du cube sur la dimension sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8b00a-128">Type an expression to use as a criterion when filtering the cube on the selected dimension.</span></span>  
  
 <span data-ttu-id="8b00a-129">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="8b00a-129">**Parameters**</span></span>  
 <span data-ttu-id="8b00a-130">Cette option n'est pas utilisée pour les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="8b00a-130">This option is not used for data mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b00a-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b00a-131">See Also</span></span>  
 <span data-ttu-id="8b00a-132">[Fin de l’Assistant &#40;l’Assistant Exploration de données&#41;](completing-the-wizard-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="8b00a-132">[Completing the Wizard &#40;Data Mining Wizard&#41;](completing-the-wizard-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="8b00a-133">[Aide (F1) de l’Assistant Exploration de données &#40;Analysis Services-exploration de données&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="8b00a-133">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="8b00a-134">Spécifier l’utilisation des colonnes du modèle d’exploration de données &#40;l’Assistant Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="8b00a-134">Specify Mining Model Column Usage &#40;Data Mining Wizard&#41;</span></span>](specify-mining-model-column-usage-data-mining-wizard.md)  
  
  
