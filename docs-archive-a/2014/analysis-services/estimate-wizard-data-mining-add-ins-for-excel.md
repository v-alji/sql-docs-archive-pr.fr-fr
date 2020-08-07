---
title: Assistant estimation (compléments d’exploration de données pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- estimation
ms.assetid: 7f2b1d5f-c9b3-4939-b35a-34ae099af15f
author: minewiskan
ms.author: owend
ms.openlocfilehash: ace9fa3a62690061677312d4f7dbb6b8a1d0ea5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703395"
---
# <a name="estimate-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="af5a9-102">Assistant Estimation (Compléments d'exploration de données pour Excel)</span><span class="sxs-lookup"><span data-stu-id="af5a9-102">Estimate Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="af5a9-103">![Assistant Estimation sur le ruban Exploration de données](media/dmc-estimate.gif "Assistant Estimation sur le ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="af5a9-103">![Estimate wizard in Data Mining ribbon](media/dmc-estimate.gif "Estimate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="af5a9-104">L’Assistant **estimation** vous aide à créer un modèle d’estimation.</span><span class="sxs-lookup"><span data-stu-id="af5a9-104">The **Estimate** wizard helps you create an estimation model.</span></span> <span data-ttu-id="af5a9-105">Un modèle d'estimation extrait les séquences remarquables des données et utilise ces séquences pour prédire les facteurs qui affectent les résultats.</span><span class="sxs-lookup"><span data-stu-id="af5a9-105">An estimation model extracts patterns from data and uses the patterns to predict the factors that affect outcomes.</span></span>  
  
 <span data-ttu-id="af5a9-106">L'estimation est utilisée pour prévoir les résultats numériques.</span><span class="sxs-lookup"><span data-stu-id="af5a9-106">Estimation is used for predicting numeric outcomes.</span></span> <span data-ttu-id="af5a9-107">Par exemple, si votre colonne cible contient des taux de diplômes pour les écoles, avec des taux de diplôme exprimés en pourcentage, vous pouvez analyser des facteurs qui augmentent ou diminuent les taux de diplômes, tels que le nombre d’étudiants par école, le ratio étudiant-enseignant et le nombre d’enseignants.</span><span class="sxs-lookup"><span data-stu-id="af5a9-107">For example, if your target column contains graduation rates for schools, with graduation rates expressed as percentages, you could analyze factors that potentially increase or decrease graduation rates, such as the number of students per school, the student-teacher ratio, and the number of teachers.</span></span>  
  
## <a name="using-the-estimate-data-wizard"></a><span data-ttu-id="af5a9-108">Utilisation de l'Assistant Estimation des données</span><span class="sxs-lookup"><span data-stu-id="af5a9-108">Using the Estimate Data Wizard</span></span>  
  
1.  <span data-ttu-id="af5a9-109">Sur le ruban **exploration de données** , cliquez sur **estimation**.</span><span class="sxs-lookup"><span data-stu-id="af5a9-109">On the **Data Mining** ribbon, click **Estimate**.</span></span>  
  
2.  <span data-ttu-id="af5a9-110">Dans la boîte de dialogue **Sélectionner les données source** , sélectionnez les données sources à utiliser.</span><span class="sxs-lookup"><span data-stu-id="af5a9-110">In the **Select Source Data** dialog box, select the source data to use.</span></span> <span data-ttu-id="af5a9-111">Vous pouvez utiliser les données d’une **table**Excel, d’une **plage de données**Excel ou d’une source de **données externe**.</span><span class="sxs-lookup"><span data-stu-id="af5a9-111">You can use data in an Excel **Table**, an Excel **Data Range**, or from an **External data source**.</span></span>  
  
     <span data-ttu-id="af5a9-112">Si vous utilisez une source de données externe, vous pouvez créer des vues personnalisées ou des requêtes et les enregistrer en tant que source de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af5a9-112">If you use an external data source, you can create custom views or queries and save them as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="af5a9-113">Dans la boîte de dialogue **estimation** , sélectionnez la **colonne à analyser**.</span><span class="sxs-lookup"><span data-stu-id="af5a9-113">In the **Estimation** dialog box, select the **Column to analyze**.</span></span>  
  
     <span data-ttu-id="af5a9-114">La colonne cible doit contenir des données numériques continues.</span><span class="sxs-lookup"><span data-stu-id="af5a9-114">The target column must contain continuous numeric data.</span></span>  
  
4.  <span data-ttu-id="af5a9-115">Sélectionnez les colonnes à utiliser comme entrée en activant la case à cocher **colonnes d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="af5a9-115">Select columns to use as input by checking the **Input columns** checkbox.</span></span>  
  
     <span data-ttu-id="af5a9-116">Ces colonnes seront utilisées pour créer les modèles.</span><span class="sxs-lookup"><span data-stu-id="af5a9-116">These columns will be used to create the patterns.</span></span> <span data-ttu-id="af5a9-117">Vous devez éliminer de l'analyse toutes les colonnes qui risquent d'être inutiles, comme les numéros d'identification ou les colonnes qui ne sont pas pertinentes.</span><span class="sxs-lookup"><span data-stu-id="af5a9-117">You should eliminate from analysis any columns that are not likely to help, such as ID numbers, or columns that contain irrelevant data.</span></span>  
  
5.  <span data-ttu-id="af5a9-118">L’Assistant **estimation** sélectionne l’algorithme optimal pour votre jeu de données.</span><span class="sxs-lookup"><span data-stu-id="af5a9-118">The **Estimate** wizard selects the optimum algorithm for your data set.</span></span> <span data-ttu-id="af5a9-119">Toutefois, vous pouvez cliquer sur **paramètres** pour ouvrir la boîte de dialogue **paramètres d’algorithme** et définir des options avancées.</span><span class="sxs-lookup"><span data-stu-id="af5a9-119">However, you can click **Parameters** to open the **Algorithm Parameters** dialog box and set advanced options.</span></span>  
  
6.  <span data-ttu-id="af5a9-120">Si vos données sont numériques et que vous pouvez utiliser la méthode de régression linéaire Microsoft, vous pouvez **Vérifier la zone de regression pour** toutes les colonnes numériques que vous savez (ou fortement suspectes) être corrélées avec la valeur prévisible.</span><span class="sxs-lookup"><span data-stu-id="af5a9-120">If your data is numeric and you can use the Microsoft Linear Regression method, you can check the **Regressor** box for any numeric columns that you know (or strongly suspect) to be correlated with the predictable value.</span></span>  
  
     <span data-ttu-id="af5a9-121">L'algorithme testera ensuite les valeurs dans cette colonne pour déterminer si elles affectent les résultats.</span><span class="sxs-lookup"><span data-stu-id="af5a9-121">The algorithm will then test the values in that column to determine if they affect the outcomes.</span></span> <span data-ttu-id="af5a9-122">Si vous n’en êtes pas sûr, cliquez sur **suggérer** et l’algorithme testera toutes les colonnes et détectera automatiquement les meilleures valeurs à utiliser comme régressions.</span><span class="sxs-lookup"><span data-stu-id="af5a9-122">If you are unsure, click **Suggest** and the algorithm will test all column and automatically detect the best values to use as regressors.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="af5a9-123">Un régresseur est requis pour créer une évaluation.</span><span class="sxs-lookup"><span data-stu-id="af5a9-123">A regressor is required to create an estimate.</span></span> <span data-ttu-id="af5a9-124">L'Assistant recommande toujours le meilleur régresseur, en fonction selon d'une analyse initiale des données.</span><span class="sxs-lookup"><span data-stu-id="af5a9-124">The wizard always recommends the best regressor, based on an initial pass over the data.</span></span> <span data-ttu-id="af5a9-125">Par conséquent, si vous n'êtes pas sûr, il vaut mieux accepter les sélections recommandées.</span><span class="sxs-lookup"><span data-stu-id="af5a9-125">Therefore, if you are not sure, it is best to accept the recommended selections.</span></span>  
  
7.  <span data-ttu-id="af5a9-126">Sur la page **fractionner les données en jeux d’apprentissage et jeux de test** , spécifiez si vous souhaitez créer un petit sous-ensemble de données à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="af5a9-126">On the **Split data into training and testing sets** page, specify whether you want to create a small subset of the data for testing.</span></span>  
  
8.  <span data-ttu-id="af5a9-127">Dans la page **Terminer** , fournissez des noms pour la nouvelle structure d’exploration de données et le mode d’exploration de données, ou acceptez les noms par défaut fournis.</span><span class="sxs-lookup"><span data-stu-id="af5a9-127">On the **Finish** page, provide names for the new mining structure and mining mode, or accept the default names that are provided.</span></span>  
  
9. <span data-ttu-id="af5a9-128">Définissez des options pour utiliser le modèle.</span><span class="sxs-lookup"><span data-stu-id="af5a9-128">Set options for using the model.</span></span>  
  
    -   <span data-ttu-id="af5a9-129">Sélectionnez **Parcourir** pour ouvrir immédiatement le modèle dans une visionneuse.</span><span class="sxs-lookup"><span data-stu-id="af5a9-129">Select **Browse** to immediately open the model in a viewer.</span></span>  
  
         <span data-ttu-id="af5a9-130">Cette visionneuse graphique affiche un graphique du réseau de dépendances et l'arbre de décision généré par l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="af5a9-130">This graphical viewer displays a dependency network graph and the decision tree generated by the algorithm.</span></span> <span data-ttu-id="af5a9-131">En explorant ces informations, vous pouvez mieux comprendre les facteurs qui contribuent aux valeurs estimées.</span><span class="sxs-lookup"><span data-stu-id="af5a9-131">By exploring this information, you can better understand the factors that contribute to the estimated values.</span></span>  
  
    -   <span data-ttu-id="af5a9-132">Sélectionnez **activer l’extraction** pour permettre aux utilisateurs de votre analyse d’afficher les données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="af5a9-132">Select **Enable drillthrough** to let users of your analysis view the underlying data.</span></span>  
  
         <span data-ttu-id="af5a9-133">Cette option est disponible uniquement si vous utilisez les algorithmes MDT ou MLR.</span><span class="sxs-lookup"><span data-stu-id="af5a9-133">This option is available only if you use the Decision Trees opr Linear Regression algorithms.</span></span>  
  
    -   <span data-ttu-id="af5a9-134">**Utilisez le modèle temporaire**.</span><span class="sxs-lookup"><span data-stu-id="af5a9-134">**Use temporary model**.</span></span> <span data-ttu-id="af5a9-135">Si cette option est sélectionnée, le modèle ne sera pas enregistré sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="af5a9-135">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="af5a9-136">Lorsque vous fermez Excel, les modèles temporaires sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="af5a9-136">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-estimation-models"></a><span data-ttu-id="af5a9-137">En savoir plus sur les modèles d'estimation</span><span class="sxs-lookup"><span data-stu-id="af5a9-137">More About Estimation Models</span></span>  
 <span data-ttu-id="af5a9-138">L’Assistant **estimation** prend en charge l’utilisation de l’un des algorithmes suivants :</span><span class="sxs-lookup"><span data-stu-id="af5a9-138">The **Estimate** wizard supports the use of any of the following algorithms:</span></span>  
  
-   <span data-ttu-id="af5a9-139">Algorithme d’arbre de décision Microsoft</span><span class="sxs-lookup"><span data-stu-id="af5a9-139">Microsoft Decision Tree algorithm</span></span>  
  
-   <span data-ttu-id="af5a9-140">Algorithme MLR (Microsoft Linear Regression)</span><span class="sxs-lookup"><span data-stu-id="af5a9-140">Microsoft Linear Regression algorithm</span></span>  
  
-   <span data-ttu-id="af5a9-141">Algorithme MLR (Microsoft Logistic Regression)</span><span class="sxs-lookup"><span data-stu-id="af5a9-141">Microsoft Logistic Regression algorithm</span></span>  
  
-   <span data-ttu-id="af5a9-142">Algorithme de réseau neuronal Microsoft</span><span class="sxs-lookup"><span data-stu-id="af5a9-142">Microsoft Neural network algorithm</span></span>  
  
 <span data-ttu-id="af5a9-143">Dans la boîte de dialogue **paramètres d’algorithme** , vous pouvez définir des options avancées supplémentaires, en fonction de l’algorithme que vous avez choisi.</span><span class="sxs-lookup"><span data-stu-id="af5a9-143">In the **Algorithm Parameters** dialog box, you can set additional advanced options, depending on which algorithm you chose.</span></span> <span data-ttu-id="af5a9-144">Pour plus d'informations sur les options de chaque algorithme, consultez les rubriques de la documentation en ligne de SQL Server :</span><span class="sxs-lookup"><span data-stu-id="af5a9-144">For information on the options for each algorithm see these topics in SQL Server Books Online:</span></span>  
  
 [<span data-ttu-id="af5a9-145">Références techniques relatives à l'algorithme MDT (Microsoft Decision Trees)</span><span class="sxs-lookup"><span data-stu-id="af5a9-145">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="af5a9-146">Références techniques relatives à l'algorithme MLR (Microsoft Linear Regression)</span><span class="sxs-lookup"><span data-stu-id="af5a9-146">Microsoft Linear Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-linear-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="af5a9-147">Références techniques relatives à l’algorithme MLR (Microsoft Logistic Regression)</span><span class="sxs-lookup"><span data-stu-id="af5a9-147">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="af5a9-148">Microsoft Neural Network Algorithm Technical Reference</span><span class="sxs-lookup"><span data-stu-id="af5a9-148">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="af5a9-149">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="af5a9-149">Requirements</span></span>  
 <span data-ttu-id="af5a9-150">Pour utiliser l'Assistant Estimation des données, vous devez être connecté à une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af5a9-150">To use the Estimate Data Wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="af5a9-151">Pour plus d’informations sur la création d’une connexion, consultez [se connecter à des données sources &#40;client d’exploration de données pour Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="af5a9-151">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="af5a9-152">Pour utiliser l'algorithme d'estimation, le résultat que vous tentez de prédire doit être exprimé sous la forme d'une valeur numérique, comme une devise, un montant de vente, une date ou une heure.</span><span class="sxs-lookup"><span data-stu-id="af5a9-152">To use the estimation algorithm, the outcome that you are trying to predict must be expressed as a numeric value, such as a currency, sales amount, date, or time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af5a9-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af5a9-153">See Also</span></span>  
 <span data-ttu-id="af5a9-154">[Création d’un modèle d’exploration de données](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="af5a9-154">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="af5a9-155">Procédure pas à pas du diagramme d’arbre de décision &#40;des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="af5a9-155">Decision Tree Diagram Walkthrough  &#40;Data Mining Add-ins&#41;</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
  
