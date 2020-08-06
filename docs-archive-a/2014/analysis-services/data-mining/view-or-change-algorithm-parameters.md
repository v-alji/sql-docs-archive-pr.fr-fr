---
title: Afficher ou modifier les paramètres d’algorithme | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- algorithms [data mining]
- mining models [Analysis Services], algorithms
ms.assetid: 151b899b-c27a-4a09-bcf5-5c9f0ec24168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30719cd50e0c473cf2aab5d9689d27dff4f26343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604269"
---
# <a name="view-or-change-algorithm-parameters"></a><span data-ttu-id="05773-102">Afficher ou modifier les paramètres d'algorithme</span><span class="sxs-lookup"><span data-stu-id="05773-102">View or Change Algorithm Parameters</span></span>
  <span data-ttu-id="05773-103">Vous pouvez modifier les paramètres fournis avec les algorithmes que vous utilisez pour générer des modèles d'exploration de données pour personnaliser les résultats du modèle.</span><span class="sxs-lookup"><span data-stu-id="05773-103">You can change the parameters provided with the algorithms that you use to build data mining models to customize the results of the model.</span></span>  
  
 <span data-ttu-id="05773-104">Les paramètres d’algorithme fournis dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] modifient bien plus que simplement les propriétés du modèle : ils peuvent être utilisés pour modifier fondamentalement la manière dont les données sont traitées, regroupées et affichées.</span><span class="sxs-lookup"><span data-stu-id="05773-104">The algorithm parameters provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] change much more than just properties on the model: they can be used to fundamentally alter the way that data is processed, grouped, and displayed.</span></span> <span data-ttu-id="05773-105">Par exemple, vous pouvez utiliser des paramètres d'algorithme pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="05773-105">For example, you can use algorithm parameters to do the following:</span></span>  
  
-   <span data-ttu-id="05773-106">modifier la méthode d'analyse, telle que la méthode de clustering ;</span><span class="sxs-lookup"><span data-stu-id="05773-106">Change the method of analysis, such as the clustering method.</span></span>  
  
-   <span data-ttu-id="05773-107">contrôler le comportement de la sélection des fonctionnalités ;</span><span class="sxs-lookup"><span data-stu-id="05773-107">Control feature selection behavior.</span></span>  
  
-   <span data-ttu-id="05773-108">spécifier la taille des jeux d'éléments ou la probabilité des règles ;</span><span class="sxs-lookup"><span data-stu-id="05773-108">Specify the size of itemsets or the probability of rules.</span></span>  
  
-   <span data-ttu-id="05773-109">contrôler la création de branche et la profondeur des arbres de décision ;</span><span class="sxs-lookup"><span data-stu-id="05773-109">Control branching and depth of decision trees.</span></span>  
  
-   <span data-ttu-id="05773-110">spécifier une valeur de départ ou la taille du jeu de données d'exclusion interne utilisé pour la création de modèle.</span><span class="sxs-lookup"><span data-stu-id="05773-110">Specify a seed value or the size of the internal holdout set used for model creation.</span></span>  
  
 <span data-ttu-id="05773-111">Les paramètres fournis pour chaque algorithme varient considérablement. Pour obtenir la liste des paramètres que vous pouvez définir pour chaque algorithme, consultez les rubriques de références techniques dans cette section : [Algorithmes d’exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="05773-111">The parameters provided for each algorithm vary greatly; for a list of the parameters that you can set for each algorithm, see the technical reference topics in this section: [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="change-an-algorithm-parameter"></a><span data-ttu-id="05773-112">Changer un paramètre d'algorithme</span><span class="sxs-lookup"><span data-stu-id="05773-112">Change an algorithm parameter</span></span>  
  
1.  <span data-ttu-id="05773-113">Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez avec le bouton droit sur le type d’algorithme du modèle d’exploration de données dont vous voulez régler l’algorithme, puis sélectionnez **Définir les paramètres de l’algorithme**.</span><span class="sxs-lookup"><span data-stu-id="05773-113">On the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the algorithm type of the mining model for which you want to tune the algorithm, and select **Set Algorithm Parameters**.</span></span>  
  
     <span data-ttu-id="05773-114">La boîte de dialogue **Paramètres d’algorithme** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="05773-114">The **Algorithm Parameters** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="05773-115">Dans la colonne **Valeur** , définissez une nouvelle valeur pour l’algorithme à modifier.</span><span class="sxs-lookup"><span data-stu-id="05773-115">In the **Value** column, set a new value for the algorithm that you want to change.</span></span>  
  
     <span data-ttu-id="05773-116">Si vous n’entrez pas de valeur dans la colonne **Valeur** , [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilise la valeur de paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="05773-116">If you do not enter a value in the **Value** column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses the default parameter value.</span></span> <span data-ttu-id="05773-117">La colonne **Plage** décrit les valeurs possibles que vous pouvez entrer.</span><span class="sxs-lookup"><span data-stu-id="05773-117">The **Range** column describes the possible values that you can enter.</span></span>  
  
3.  <span data-ttu-id="05773-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="05773-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="05773-119">La nouvelle valeur est affectée à l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="05773-119">The algorithm parameter is set with the new value.</span></span> <span data-ttu-id="05773-120">Pour que la modification soit appliquée au paramètre dans le modèle d'exploration de données, vous devez retraiter le modèle.</span><span class="sxs-lookup"><span data-stu-id="05773-120">The parameter change will not be reflected in the mining model until you reprocess the model.</span></span>  
  
### <a name="view-the-parameters-used-in-an-existing-model"></a><span data-ttu-id="05773-121">Afficher les paramètres utilisés dans un modèle existant</span><span class="sxs-lookup"><span data-stu-id="05773-121">View the parameters used in an existing model</span></span>  
  
1.  <span data-ttu-id="05773-122">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez une fenêtre de requête DMX.</span><span class="sxs-lookup"><span data-stu-id="05773-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window.</span></span>  
  
2.  <span data-ttu-id="05773-123">Tapez une requête semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="05773-123">Type a query like this one:</span></span>  
  
    ```  
    select MINING_PARAMETERS   
    from $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = '<model name>'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="05773-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="05773-124">See Also</span></span>  
 [<span data-ttu-id="05773-125">Tâches du modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="05773-125">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
