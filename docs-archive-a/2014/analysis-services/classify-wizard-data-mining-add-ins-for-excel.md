---
title: Assistant de classification (compléments d’exploration de données pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- classification [data mining]
ms.assetid: 409c5076-c4c3-4f09-8f30-d3297df45f13
author: minewiskan
ms.author: owend
ms.openlocfilehash: b82fc98df10ae2e6754a378dacea108f9f3379ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602520"
---
# <a name="classify-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="54598-102">Assistant Classification (Compléments d'exploration de données pour Excel)</span><span class="sxs-lookup"><span data-stu-id="54598-102">Classify Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="54598-103">![Assistant Classification sur le ruban Exploration de données](media/dmc-classify.gif "Assistant Classification sur le ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="54598-103">![Classify wizard in Data Mining ribbon](media/dmc-classify.gif "Classify wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="54598-104">L’Assistant **classification** vous aide à créer un modèle de classification basé sur des données existantes dans une table Excel, une plage Excel ou une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="54598-104">The **Classify** wizard helps you build a classification model based on existing data in an Excel table, an Excel range, or an external data source.</span></span>  
  
 <span data-ttu-id="54598-105">Un modèle de classification extrait des séquences de vos données qui indiquent des similarités et vous aide à faire des prédictions basées sur des groupements de valeurs.</span><span class="sxs-lookup"><span data-stu-id="54598-105">A classification model extracts patterns in your data that indicate similarities and helps you make predictions based on groupings of values.</span></span> <span data-ttu-id="54598-106">Par exemple, un modèle de classification peut être utilisé pour prédire un risque en fonction des caractéristiques des revenus ou des dépenses.</span><span class="sxs-lookup"><span data-stu-id="54598-106">For example, a classification model might be used to predict risk based on income or spending patterns.</span></span>  
  
## <a name="using-the-classify-wizard"></a><span data-ttu-id="54598-107">Utilisation de l'Assistant Classification</span><span class="sxs-lookup"><span data-stu-id="54598-107">Using the Classify Wizard</span></span>  
  
1.  <span data-ttu-id="54598-108">Dans le ruban **exploration de données** , cliquez sur **classifier**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="54598-108">In the **Data Mining** ribbon, click **Classify**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="54598-109">Dans la page **Sélectionner les données sources** , choisissez les données à analyser.</span><span class="sxs-lookup"><span data-stu-id="54598-109">In the **Select Source Data** page, choose the data to analyze.</span></span>  
  
     <span data-ttu-id="54598-110">L'Assistant prend en charge plusieurs types de données : tables Excel, plages Excel et sources de données externes.</span><span class="sxs-lookup"><span data-stu-id="54598-110">This wizard supports multiple kinds of data: Excel tables, Excel ranges, and external data sources.</span></span> <span data-ttu-id="54598-111">Les données externes peuvent être ajoutées à Excel, ou bien vous pouvez choisir un ensemble de tables ou vues dans une source de données Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="54598-111">With external data, you can either add it into Excel, or choose a set of tables or views in an Analysis Services data source.</span></span> <span data-ttu-id="54598-112">Vous pouvez également ajouter des tables et changer les colonnes pour créer une source de données ad hoc.</span><span class="sxs-lookup"><span data-stu-id="54598-112">You can also add tables and change columns to create ad hoc data sources.</span></span>  
  
3.  <span data-ttu-id="54598-113">Dans la page **classification** , choisissez la colonne que vous souhaitez classifier.</span><span class="sxs-lookup"><span data-stu-id="54598-113">On the **Classification** page, choose the column that you want to classify.</span></span>  
  
     <span data-ttu-id="54598-114">Passez en revue les colonnes de la liste, les **colonnes d’entrée**et désélectionnez toutes les colonnes qui ont des valeurs uniques et, par conséquent, ne sont pas utiles pour créer des modèles, tels que des numéros d’identification, des noms de clients, etc.</span><span class="sxs-lookup"><span data-stu-id="54598-114">Review the columns in the list, **Input columns**, and deselect any columns that have unique values and thus aren't useful for creating patterns, such as ID numbers, customer names, and so on.</span></span> <span data-ttu-id="54598-115">Vous devez également supprimer les colonnes qui sont des doublons de la colonne à classer.</span><span class="sxs-lookup"><span data-stu-id="54598-115">You should also remove columns that essentially duplicate the classifiable column.</span></span>  
  
     <span data-ttu-id="54598-116">Par exemple, si vous classez en fonction de la catégorie d'un produit, vous devez exclure le champ de sous-catégorie s'il existe une règle d'entreprise connue, ou bien la force de cette règle peut vous empêcher de découvrir d'autres corrélations.</span><span class="sxs-lookup"><span data-stu-id="54598-116">For example, if you are classifying predicting the category of a product, you should exclude the subcategory field if there is a known business rule, or else the strength of that rule might prevent you from discovering other correlations.</span></span>  
  
4.  <span data-ttu-id="54598-117">Si vous le souhaitez, cliquez sur **paramètres** pour modifier les paramètres d’algorithme et personnaliser le comportement du modèle de clustering.</span><span class="sxs-lookup"><span data-stu-id="54598-117">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="54598-118">Dans la page **fractionner les données en jeux d’apprentissage et jeux de test** , spécifiez la quantité de données à conserver pour le test.</span><span class="sxs-lookup"><span data-stu-id="54598-118">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="54598-119">Le reste est toujours utilisé pour l'apprentissage du modèle.</span><span class="sxs-lookup"><span data-stu-id="54598-119">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="54598-120">Le paramètre par défaut est 30 % de données de test et 70 % de données de formation.</span><span class="sxs-lookup"><span data-stu-id="54598-120">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="54598-121">Dans la page **Terminer** , indiquez un nom descriptif pour votre jeu de données et votre modèle, puis définissez les options suivantes qui contrôlent la façon dont vous travaillez avec le modèle terminé :</span><span class="sxs-lookup"><span data-stu-id="54598-121">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="54598-122">**Parcourir le modèle**.</span><span class="sxs-lookup"><span data-stu-id="54598-122">**Browse model**.</span></span> <span data-ttu-id="54598-123">Lorsque cette option est sélectionnée, dès que l’Assistant a terminé de traiter le modèle, il ouvre une fenêtre **Parcourir** pour vous aider à explorer les résultats.</span><span class="sxs-lookup"><span data-stu-id="54598-123">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="54598-124">Le contenu de la visionneuse dépend du type de modèle que vous créez.</span><span class="sxs-lookup"><span data-stu-id="54598-124">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="54598-125">Pour plus d’informations, consultez [exploration d’un modèle d’arbre de décision](browsing-a-decision-trees-model.md) et [exploration d’un modèle de réseau neuronal](browsing-a-neural-network-model.md).</span><span class="sxs-lookup"><span data-stu-id="54598-125">For more information, see [Browsing a Decision Trees Model](browsing-a-decision-trees-model.md) and [Browsing a Neural Network Model](browsing-a-neural-network-model.md).</span></span>  
  
    -   <span data-ttu-id="54598-126">**Activer l’extraction**.</span><span class="sxs-lookup"><span data-stu-id="54598-126">**Enable drillthrough**.</span></span> <span data-ttu-id="54598-127">Sélectionnez cette option pour examiner les données sous-jacentes du modèle terminé.</span><span class="sxs-lookup"><span data-stu-id="54598-127">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="54598-128">Cette option est disponible uniquement si vous créez un modèle d'arbre de décision.</span><span class="sxs-lookup"><span data-stu-id="54598-128">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="54598-129">**Utilisez le modèle temporaire**.</span><span class="sxs-lookup"><span data-stu-id="54598-129">**Use temporary model**.</span></span> <span data-ttu-id="54598-130">Si cette option est sélectionnée, le modèle ne sera pas enregistré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="54598-130">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="54598-131">Lorsque vous fermez Excel, les modèles temporaires sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="54598-131">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-classification-models"></a><span data-ttu-id="54598-132">En savoir plus sur les modèles de classification</span><span class="sxs-lookup"><span data-stu-id="54598-132">More About Classification Models</span></span>  
 <span data-ttu-id="54598-133">Dans la boîte de dialogue **paramètres d’algorithme** , vous pouvez également choisir la méthode de classification parmi les algorithmes fournis dans Analysis Services :</span><span class="sxs-lookup"><span data-stu-id="54598-133">In the **Algorithm Parameters** dialog box, you can also choose the classification method from among these algorithms provided in Analysis Services:</span></span>  
  
-   <span data-ttu-id="54598-134">Microsoft Decision Tree</span><span class="sxs-lookup"><span data-stu-id="54598-134">Microsoft Decision Tree</span></span>  
  
-   <span data-ttu-id="54598-135">Microsoft Logistic Regression</span><span class="sxs-lookup"><span data-stu-id="54598-135">Microsoft Logistic Regression</span></span>  
  
-   <span data-ttu-id="54598-136">Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="54598-136">Microsoft Naïve Bayes</span></span>  
  
-   <span data-ttu-id="54598-137">Microsoft Neural Network</span><span class="sxs-lookup"><span data-stu-id="54598-137">Microsoft Neural Network</span></span>  
  
 <span data-ttu-id="54598-138">Bien que les algorithmes puissent donner des résultats similaires, ils analysent les données différemment, par conséquent nous vous recommandons d'essayer plusieurs algorithmes et de comparer les résultats.</span><span class="sxs-lookup"><span data-stu-id="54598-138">Although the algorithms might yield similar results, they analyze the data differently, so we recommend trying several algorithms and comparing the results.</span></span> <span data-ttu-id="54598-139">La méthode par défaut est Microsoft Decision Tree.</span><span class="sxs-lookup"><span data-stu-id="54598-139">The default method is Microsoft Decision Trees.</span></span>  
  
 <span data-ttu-id="54598-140">Dans la liste **paramètres** , vous pouvez modifier les options avancées, qui dépendent du type d’algorithme que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="54598-140">In the **Parameters** list, you can change advanced options, which depend on the type of algorithm you choose.</span></span> <span data-ttu-id="54598-141">Les paramètres de chaque algorithme sont décrits de façon plus détaillée dans la Documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54598-141">The parameters for each algorithm are described in more detail in SQL Server Books Online.</span></span>  
  
 [<span data-ttu-id="54598-142">Références techniques relatives à l'algorithme MDT (Microsoft Decision Trees)</span><span class="sxs-lookup"><span data-stu-id="54598-142">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="54598-143">Références techniques relatives à l’algorithme MLR (Microsoft Logistic Regression)</span><span class="sxs-lookup"><span data-stu-id="54598-143">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="54598-144">Références techniques relatives à l'algorithme MNB (Microsoft Naive Bayes)</span><span class="sxs-lookup"><span data-stu-id="54598-144">Microsoft Naive Bayes Algorithm Technical Reference</span></span>](data-mining/microsoft-naive-bayes-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="54598-145">Microsoft Neural Network Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="54598-145">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="54598-146">Spécifications</span><span class="sxs-lookup"><span data-stu-id="54598-146">Requirements</span></span>  
 <span data-ttu-id="54598-147">Pour utiliser l’Assistant **classification** , vous devez être connecté à une [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="54598-147">To use the **Classify** wizard, you must be connected to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="54598-148">Pour plus d’informations sur la création d’une connexion, consultez [se connecter à des données sources &#40;client d’exploration de données pour Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="54598-148">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54598-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54598-149">See Also</span></span>  
 [<span data-ttu-id="54598-150">Création d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="54598-150">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
