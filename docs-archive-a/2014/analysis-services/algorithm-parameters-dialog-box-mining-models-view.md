---
title: Boîte de dialogue Paramètres d’algorithme (vue modèles d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.models.algorithmparameters.f1
helpviewer_keywords:
- Algorithm Parameters dialog box
ms.assetid: 57f9f6f8-8ca4-4a6e-8f18-85f0571b7060
author: minewiskan
ms.author: owend
ms.openlocfilehash: 303d8b5bd3437690c65873e106a94cf2ce8eb9f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602671"
---
# <a name="algorithm-parameters-dialog-box-mining-models-view"></a><span data-ttu-id="e1940-102">Boîte de dialogue Paramètres d'algorithme (Vue Modèles d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="e1940-102">Algorithm Parameters Dialog Box (Mining Models View)</span></span>
  <span data-ttu-id="e1940-103">Utilisez la boîte de dialogue **Paramètres d’algorithme** pour ajuster les paramètres d’algorithme spécifiques du modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e1940-103">Use the **Algorithm Parameters** dialog box to adjust algorithm parameters that are specific to the selected model.</span></span> <span data-ttu-id="e1940-104">Lorsque vous modifiez un paramètre d'algorithme, vous modifiez habituellement les résultats du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e1940-104">When you change an algorithm parameter, you will usually change the results of the mining model.</span></span> <span data-ttu-id="e1940-105">L'influence de chaque paramètre sur les résultats dépend de l'algorithme que vous utilisez et de vos données.</span><span class="sxs-lookup"><span data-stu-id="e1940-105">The way that each parameter affects the results depends on the algorithm you are using, and on your data.</span></span> <span data-ttu-id="e1940-106">Pour plus d’informations, consultez [Personnaliser les modèles et les structures d’exploration de données](data-mining/customize-mining-models-and-structure.md).</span><span class="sxs-lookup"><span data-stu-id="e1940-106">For more information, see [Customize Mining Models and Structure](data-mining/customize-mining-models-and-structure.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e1940-107">Options</span><span class="sxs-lookup"><span data-stu-id="e1940-107">Options</span></span>  
 <span data-ttu-id="e1940-108">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="e1940-108">**Parameters**</span></span>  
 <span data-ttu-id="e1940-109">Affiche la liste des paramètres disponibles pour le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e1940-109">Lists the parameters that are available for the selected mining model.</span></span>  
  
 <span data-ttu-id="e1940-110">La liste suivante décrit les colonnes disponibles.</span><span class="sxs-lookup"><span data-stu-id="e1940-110">The following list describes the available columns.</span></span>  
  
|<span data-ttu-id="e1940-111">Colonne</span><span class="sxs-lookup"><span data-stu-id="e1940-111">Column</span></span>|<span data-ttu-id="e1940-112">Description</span><span class="sxs-lookup"><span data-stu-id="e1940-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e1940-113">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="e1940-113">**Parameter**</span></span>|<span data-ttu-id="e1940-114">Liste le nom du paramètre.</span><span class="sxs-lookup"><span data-stu-id="e1940-114">List the name of the parameter.</span></span>|  
|<span data-ttu-id="e1940-115">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="e1940-115">**Value**</span></span>|<span data-ttu-id="e1940-116">Vous ne devez entrer une valeur que si vous souhaitez remplacer la valeur par défaut du paramètre.</span><span class="sxs-lookup"><span data-stu-id="e1940-116">Enter a value only if you want to change the default value of the parameter.</span></span>|  
|<span data-ttu-id="e1940-117">**Par défaut**</span><span class="sxs-lookup"><span data-stu-id="e1940-117">**Default**</span></span>|<span data-ttu-id="e1940-118">Donne la valeur par défaut du paramètre, qui sera utilisée par l’algorithme si vous n’entrez pas de valeur dans la colonne **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="e1940-118">List the default value of the parameter that the algorithm will use if you do not supply a value in the **Value** column.</span></span>|  
|<span data-ttu-id="e1940-119">**Plage**</span><span class="sxs-lookup"><span data-stu-id="e1940-119">**Range**</span></span>|<span data-ttu-id="e1940-120">Répertorie l’intervalle des valeurs possibles que vous pouvez entrer dans la colonne **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="e1940-120">List the range of possible values that you can enter into the **Value** column.</span></span> <span data-ttu-id="e1940-121">Les plages peuvent être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="e1940-121">The ranges can be one of the following:</span></span><br /><br /> <span data-ttu-id="e1940-122">Liste discrète, telle que 1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="e1940-122">A discrete list, such as 1, 2, 3</span></span><br /><br /> <span data-ttu-id="e1940-123">Une plage inclusive, telle que [0, 100]</span><span class="sxs-lookup"><span data-stu-id="e1940-123">An inclusive range, such as [0, 100]</span></span><br /><br /> <span data-ttu-id="e1940-124">Plage exclusive, telle que (0,...)</span><span class="sxs-lookup"><span data-stu-id="e1940-124">An exclusive range, such as (0,...)</span></span><br /><br /> <span data-ttu-id="e1940-125">Une combinaison, telle que [0,...)</span><span class="sxs-lookup"><span data-stu-id="e1940-125">A combination, such as [0,...)</span></span>|  
  
 <span data-ttu-id="e1940-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="e1940-126">**Description**</span></span>  
 <span data-ttu-id="e1940-127">Décrit le paramètre sélectionné dans la liste **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="e1940-127">Describes the selected parameter in the **Parameters** list.</span></span>  
  
 <span data-ttu-id="e1940-128">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="e1940-128">**Add**</span></span>  
 <span data-ttu-id="e1940-129">Cliquez sur cet élément pour ajouter à la liste des paramètres supplémentaires spécifiques de l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="e1940-129">Click to add additional, algorithm specific-parameters to the list.</span></span> <span data-ttu-id="e1940-130">Après avoir ajouté le paramètre, vous pouvez entrer le nom correct dans la colonne **Paramètre** et donner une valeur dans la colonne **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="e1940-130">After adding the parameter, you can enter the correct name in the **Parameter** column and provide a value in the **Value** column.</span></span>  
  
 <span data-ttu-id="e1940-131">**Remove**</span><span class="sxs-lookup"><span data-stu-id="e1940-131">**Remove**</span></span>  
 <span data-ttu-id="e1940-132">Cliquez sur cet élément pour supprimer un paramètre personnalisé de la liste.</span><span class="sxs-lookup"><span data-stu-id="e1940-132">Click to delete a custom parameter from the list.</span></span>  
  
 <span data-ttu-id="e1940-133">Si vous supprimez l'un des paramètres d'algorithme Analysis Services standard de la liste, le paramètre continue d'être utilisé dans le modèle, mais avec ses valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="e1940-133">If you delete one of the standard Analysis Services algorithm parameters from the list, the parameter will still be used in the model, but with the default values for that parameter.</span></span> <span data-ttu-id="e1940-134">Le paramètre n'est pas supprimé définitivement et apparaîtra la prochaine fois que vous ouvrirez la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e1940-134">The parameter is not permanently deleted and will appear the next time that you open the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1940-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e1940-135">See Also</span></span>  
 <span data-ttu-id="e1940-136">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e1940-136">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="e1940-137">[Vue modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-models-view-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="e1940-137">[Mining Models View &#40;Data Mining Model Designer&#41;](mining-models-view-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="e1940-138">Déplacement d'objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="e1940-138">Moving Data Mining Objects</span></span>](data-mining/moving-data-mining-objects.md)  
  
  
