---
title: Choisir la colonne à utiliser pour tester un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], predictable mining columns
- Mining Accuracy Chart [Analysis Services], columns
- predictable mining columns [Analysis Services]
ms.assetid: c6a8f23a-da21-4f31-9521-99460d624649
author: minewiskan
ms.author: owend
ms.openlocfilehash: 326a7084600695d95d3a132f633041e9abad045b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611413"
---
# <a name="choose-the-column-to-use-for-testing-a-mining-model"></a><span data-ttu-id="1e826-102">Choisir la colonne à utiliser pour tester un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="1e826-102">Choose the Column to Use for Testing a Mining Model</span></span>
  <span data-ttu-id="1e826-103">Avant de pouvoir mesurer la précision d'un modèle d'exploration de données, vous devez déterminer le résultat que vous voulez évaluer.</span><span class="sxs-lookup"><span data-stu-id="1e826-103">Before you can measure the accuracy of a mining model, you must decide which outcome it is that you want to assess.</span></span> <span data-ttu-id="1e826-104">La plupart des modèles d'exploration de données requièrent que vous choisissiez au moins une colonne à utiliser comme attribut prédictible lorsque vous créez le modèle.</span><span class="sxs-lookup"><span data-stu-id="1e826-104">Most data mining models require that you choose at least one column to use as the predictable attribute when you create the model.</span></span> <span data-ttu-id="1e826-105">Par conséquent, lorsque vous testez la précision du modèle, vous devez généralement sélectionner cet attribut comme devant être testé.</span><span class="sxs-lookup"><span data-stu-id="1e826-105">Therefore, when you test the accuracy of the model, you generally must select that attribute to test.</span></span>  
  
 <span data-ttu-id="1e826-106">La liste suivante décrit des points supplémentaires à prendre en considération pour choisir l'attribut prédictible à utiliser dans le test :</span><span class="sxs-lookup"><span data-stu-id="1e826-106">The following list describes some additional considerations for choosing the predictable attribute to use in testing:</span></span>  
  
-   <span data-ttu-id="1e826-107">Certains types de modèles d’exploration de données peuvent prédire plusieurs attributs, tels que les réseaux neuronaux, qui peuvent explorer les relations entre de nombreux attributs.</span><span class="sxs-lookup"><span data-stu-id="1e826-107">Some types of data mining models can predict multiple attributes-such as neural networks, which can explore the relationships between many attributes.</span></span>  
  
-   <span data-ttu-id="1e826-108">D’autres types de modèles d’exploration de données, tels que les modèles de clustering, n’ont pas nécessairement d’attribut prévisible.</span><span class="sxs-lookup"><span data-stu-id="1e826-108">Other types of mining models-such as clustering models-do not necessarily have a predictable attribute.</span></span> <span data-ttu-id="1e826-109">Les modèles de clustering ne peuvent être testés que s'ils ont un attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="1e826-109">Clustering models cannot be tested unless they have a predictable attribute.</span></span>  
  
-   <span data-ttu-id="1e826-110">Créer un nuage de points ou mesurer la précision d'un modèle de régression requiert que vous choisissiez un attribut prédictible continu comme résultat.</span><span class="sxs-lookup"><span data-stu-id="1e826-110">To create a scatter plot or measure the accuracy of a regression model requires that you choose a continuous predictable attribute as the outcome.</span></span> <span data-ttu-id="1e826-111">Dans ce cas, vous ne pouvez pas spécifier une valeur cible.</span><span class="sxs-lookup"><span data-stu-id="1e826-111">In that case, you cannot specify a target value.</span></span> <span data-ttu-id="1e826-112">Si vous créez autre chose qu’un nuage de points, la colonne de structure d’exploration de données sous-jacente doit également avoir un type de contenu **Discret** ou **Discrétisé**.</span><span class="sxs-lookup"><span data-stu-id="1e826-112">If you are creating anything other than a scatter plot, the underlying mining structure column must also have a content type of **Discrete** or **Discretized**.</span></span>  
  
-   <span data-ttu-id="1e826-113">Si vous choisissez un attribut discret comme résultat prédictible, vous pouvez également spécifier une valeur cible, ou vous pouvez laisser le champ **Prédire la valeur** vide.</span><span class="sxs-lookup"><span data-stu-id="1e826-113">If you choose a discrete attribute as the predictable outcome, you can also specify a target value, or you can leave the **Predict Value** field blank.</span></span> <span data-ttu-id="1e826-114">Si vous incluez une **valeur de prédiction**, le graphique mesurera uniquement l’efficacité du modèle lors de la prédiction de la valeur cible.</span><span class="sxs-lookup"><span data-stu-id="1e826-114">If you include a **Predict Value**, the chart will measure only the model's effectiveness at predicting the target value.</span></span> <span data-ttu-id="1e826-115">Si vous ne spécifiez pas de résultat cible, le modèle est mesuré pour sa précision dans la prédiction de tous les résultats.</span><span class="sxs-lookup"><span data-stu-id="1e826-115">If you do not specify a target outcome, the model is measured for its accuracy in predicting all outcomes.</span></span>  
  
-   <span data-ttu-id="1e826-116">Si vous voulez inclure plusieurs modèles et les comparer dans un graphique d'analyse de précision unique, tous les modèles doivent utiliser la même colonne prédictible.</span><span class="sxs-lookup"><span data-stu-id="1e826-116">If you want to include multiple models and compare them in a single accuracy chart, all models must use the same predictable column.</span></span>  
  
-   <span data-ttu-id="1e826-117">Quand vous créez un rapport de validation croisée, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] analyse automatiquement tous les modèles qui ont le même attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="1e826-117">When you create a cross-validation report, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will automatically analyze all models that have the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="1e826-118">Quand l’option **Synchroniser les colonnes de prédiction et les valeurs**est sélectionnée, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] choisit automatiquement les colonnes prédictibles ayant le même nom et des types de données correspondants.</span><span class="sxs-lookup"><span data-stu-id="1e826-118">When the option, **Synchronize Prediction columns and Values**, is selected, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automatically chooses predictable columns that have the same names and matching data types.</span></span> <span data-ttu-id="1e826-119">Si vos colonnes ne répondent pas à ces critères, vous pouvez désactiver cette option et choisir manuellement une colonne prédictible.</span><span class="sxs-lookup"><span data-stu-id="1e826-119">If your columns do not meet these criteria, you can turn off this option and manually choose a predictable column.</span></span> <span data-ttu-id="1e826-120">Vous devrez peut-être le faire si vous testez le modèle avec un jeu de données externes qui n'a pas les mêmes colonnes que le modèle.</span><span class="sxs-lookup"><span data-stu-id="1e826-120">You might need to do this if you are testing the model with an external data set that has different columns than the model.</span></span> <span data-ttu-id="1e826-121">Toutefois, si vous choisissez une colonne dont le type de données est incorrect, vous obtiendrez une erreur ou des résultats incorrects.</span><span class="sxs-lookup"><span data-stu-id="1e826-121">However, if you choose a column with the wrong the type of data you will either get an error or bad results.</span></span>  
  
### <a name="specify-the-outcome-to-predict"></a><span data-ttu-id="1e826-122">Spécifier le résultat à prédire</span><span class="sxs-lookup"><span data-stu-id="1e826-122">Specify the outcome to predict</span></span>  
  
1.  <span data-ttu-id="1e826-123">Double-cliquez sur la structure d'exploration de données pour l'ouvrir dans le Concepteur d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="1e826-123">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="1e826-124">Sélectionnez l’onglet **Graphique d’analyse de précision de l’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="1e826-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="1e826-125">Sélectionnez l’onglet **Sélection d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="1e826-125">Select the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="1e826-126">Sous l’onglet **Sélection d’entrée** , sous **Nom de la colonne prédictible**, sélectionnez une colonne prédictible pour chaque modèle que vous incluez dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="1e826-126">On the **Input Selection** tab, under **Predictable Column Name**, select a predictable column for each model that you include in the chart.</span></span>  
  
     <span data-ttu-id="1e826-127">Les colonnes du modèle d’exploration de données qui sont disponibles dans la zone **Nom de la colonne prédictible** sont uniquement celles dont le type d’utilisation est **Prédire** ou **Prédire uniquement**.</span><span class="sxs-lookup"><span data-stu-id="1e826-127">The mining model columns that are available in the **Predictable Column Name** box are only those with the usage type set to **Predict** or **Predict Only**.</span></span>  
  
5.  <span data-ttu-id="1e826-128">Si vous souhaitez déterminer l’élévation pour un modèle, vous devez sélectionner une valeur de résultat spécifique à mesurer dans la liste **Prédire la valeur** .</span><span class="sxs-lookup"><span data-stu-id="1e826-128">If you want to determine the lift for a model, you must select a specific outcome value to measure, for by choosing from the **Predict Value** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e826-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e826-129">See Also</span></span>  
 <span data-ttu-id="1e826-130">[Choisir et mapper les données de test du modèle](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="1e826-130">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="1e826-131">Choisir un type de graphique d'analyse de précision et définir des options de graphique</span><span class="sxs-lookup"><span data-stu-id="1e826-131">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
