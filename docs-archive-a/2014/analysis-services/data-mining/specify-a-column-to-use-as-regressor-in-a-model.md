---
title: Spécifier une colonne à utiliser comme régreseur dans un modèle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8e0cb8e-302a-4166-9ed0-e2d9e2919b0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 86899d3793985b5e3c07618360d7b6a540935a54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600334"
---
# <a name="specify-a-column-to-use-as-regressor-in-a-model"></a><span data-ttu-id="9b2f5-102">Spécifier une colonne à utiliser comme régresseur dans un modèle</span><span class="sxs-lookup"><span data-stu-id="9b2f5-102">Specify a Column to Use as Regressor in a Model</span></span>
  <span data-ttu-id="9b2f5-103">Un modèle de régression linéaire représente la valeur de l'attribut prévisible résultant d'une formule qui combine les entrées de telle façon que les données sont ajustées le mieux possible à une ligne de régression estimée.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-103">A linear regression model represents the value of the predictable attribute as the result of a formula that combines the inputs in such a way that the data is fitted as a closely as possible to an estimated regression line.</span></span> <span data-ttu-id="9b2f5-104">L'algorithme accepte uniquement les valeurs numériques comme entrées, et détecte automatiquement les entrées qui sont le mieux adaptées.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-104">The algorithm accepts only numeric values as inputs, and automatically detects the inputs that provide the best fit.</span></span>  
  
 <span data-ttu-id="9b2f5-105">Vous pouvez toutefois spécifier qu'une colonne soit incluse en tant que régresseur en ajoutant le paramètre FORCE_REGRESSOR au modèle et en spécifiant les régresseurs à utiliser.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-105">However, you can specify that a column be included as a regressor by adding the FORCE_REGRESSOR parameter to the model and specifying the regressors to use.</span></span> <span data-ttu-id="9b2f5-106">Ce peut être le cas lorsque l'attribut a une signification même si l'effet est trop limité pour être détecté par le modèle, ou lorsque vous voulez vous assurer que l'attribut est inclus dans la formule.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-106">You might want to do this in cases where the attribute has meaning even if the effect is too small to be detected by the model, or when you want to ensure that the attribute is included in the formula.</span></span>  
  
 <span data-ttu-id="9b2f5-107">La procédure suivante explique comment créer un modèle de régression linéaire simple, en utilisant le même exemple de données que celui utilisé pour le [didacticiel sur les réseaux neuronaux](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9b2f5-107">The following procedure describes how to create a simple linear regression model, using the same sample data that is used for the [neural networks tutorial](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="9b2f5-108">Le modèle n'est pas nécessairement fiable, mais il montre comment utiliser le Concepteur d'exploration de données pour personnaliser un modèle de régression linéaire.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-108">The model is not necessarily robust, but demonstrates how to use the Data Mining Designer to customize a linear regression model.</span></span>  
  
### <a name="how-to-create-a-simple-linear-regression-model"></a><span data-ttu-id="9b2f5-109">Procédure de création d'un modèle de régression linéaire simple</span><span class="sxs-lookup"><span data-stu-id="9b2f5-109">How to create a simple linear regression model</span></span>  
  
1.  <span data-ttu-id="9b2f5-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], dans l’ **Explorateur de solutions**, développez **Structures d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, expand **Mining Structures**.</span></span>  
  
2.  <span data-ttu-id="9b2f5-111">Double-cliquez sur Call Center.dmm pour l'ouvrir dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-111">Double-click Call Center.dmm to open it in the designer.</span></span>  
  
3.  <span data-ttu-id="9b2f5-112">Dans le menu **Modèle d’exploration de données** , sélectionnez **Nouveau modèle d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-112">From the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="9b2f5-113">Pour l’algorithme, sélectionnez **MLR (Microsoft Linear Regression)**.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-113">For the algorithm, select **Microsoft Linear Regression**.</span></span> <span data-ttu-id="9b2f5-114">Pour le nom, tapez **Call Center Regression**.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-114">For the name, type **Call Center Regression**.</span></span>  
  
5.  <span data-ttu-id="9b2f5-115">Sous l’onglet **Modèles d’exploration de données** , modifiez l’utilisation des colonnes de la façon suivante.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-115">In the **Mining Models** tab, change the column usage as follows.</span></span> <span data-ttu-id="9b2f5-116">La valeur **Ignorer**doit être affectée à toutes les colonnes ne figurant pas dans la liste suivante, si ce n’est pas déjà fait.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-116">All columns not in the following list should be set to **Ignore**, if they are not already.</span></span>  
  
     <span data-ttu-id="9b2f5-117">FactCallCenterID**Key**</span><span class="sxs-lookup"><span data-stu-id="9b2f5-117">FactCallCenterID**Key**</span></span>  
  
     <span data-ttu-id="9b2f5-118">ServiceGrade**PredictOnly**</span><span class="sxs-lookup"><span data-stu-id="9b2f5-118">ServiceGrade**PredictOnly**</span></span>  
  
     <span data-ttu-id="9b2f5-119">Total Operators**Input**</span><span class="sxs-lookup"><span data-stu-id="9b2f5-119">Total Operators**Input**</span></span>  
  
     <span data-ttu-id="9b2f5-120">AverageTimePerIssue**Input**</span><span class="sxs-lookup"><span data-stu-id="9b2f5-120">AverageTimePerIssue**Input**</span></span>  
  
6.  <span data-ttu-id="9b2f5-121">Dans le menu **Modèle d’exploration de données** , sélectionnez **Définir les paramètres du modèle**.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-121">From the **Mining Model** menu, select **Set Model Parameters**.</span></span>  
  
7.  <span data-ttu-id="9b2f5-122">Pour le paramètre FORCE_REGRESSOR, dans la colonne **Valeur** , tapez les noms de colonnes entre crochets et séparés par une virgule, comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b2f5-122">For the parameter, FORCE_REGRESSOR, in the **Value** column, type the column names enclosed in brackets and separated by a comma, as follows:</span></span>  
  
    ```  
    [Average Time Per Issue],[Total Operators]  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b2f5-123">L'algorithme détectera automatiquement les colonnes qui constituent les meilleurs régresseurs.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-123">The algorithm will automatically detect which columns are the best regressors.</span></span> <span data-ttu-id="9b2f5-124">Vous devez uniquement forcer l'utilisation des régresseurs lorsque vous voulez vous assurer qu'une colonne est incluse dans la formule finale.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-124">You only need to force regressors when you want to ensure that a column is included in the final formula.</span></span>  
  
8.  <span data-ttu-id="9b2f5-125">Dans le menu **Modèle d’exploration de données** , sélectionnez **Traiter le modèle**.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-125">From the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="9b2f5-126">Dans la visionneuse, le modèle est représenté sous la forme d'un nœud unique contenant la formule de régression.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-126">In the viewer, the model is represented a single node containing the regression formula.</span></span> <span data-ttu-id="9b2f5-127">Vous pouvez afficher la formule dans la **Légende d’exploration de données**, ou extraire les coefficients de la formule à l’aide de requêtes.</span><span class="sxs-lookup"><span data-stu-id="9b2f5-127">You can view the formula in the **Mining Legend**, or you can extract the coefficients for the formula by using queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b2f5-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b2f5-128">See Also</span></span>  
 <span data-ttu-id="9b2f5-129">[Algorithme de régression linéaire Microsoft](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="9b2f5-129">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="9b2f5-130">[Requêtes d’exploration de données](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="9b2f5-130">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="9b2f5-131">[Référence technique de l’algorithme de régression linéaire Microsoft](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9b2f5-131">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="9b2f5-132">Contenu du modèle d’exploration de données pour les modèles de régression linéaire &#40;Analysis Services – Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="9b2f5-132">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
