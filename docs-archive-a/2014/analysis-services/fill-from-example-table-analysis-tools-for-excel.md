---
title: Remplir à partir de l’exemple (outils d’analyse de table pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- fill from example
ms.assetid: dac57d8f-1c65-4878-8ea0-9c680df5e4fb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 69ff9f554c51240eb6f9151718d30677bfb57996
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700481"
---
# <a name="fill-from-example-table-analysis-tools-for-excel"></a><span data-ttu-id="760b0-102">Remplir à partir de l'exemple (Outils d'analyse de table pour Excel)</span><span class="sxs-lookup"><span data-stu-id="760b0-102">Fill From Example (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="760b0-103">![Bouton Remplir à partir de l'exemple dans les Outils d'analyse de table](media/tat-fillex.gif "Bouton Remplir à partir de l'exemple dans les Outils d'analyse de table")</span><span class="sxs-lookup"><span data-stu-id="760b0-103">![Fill From Example button in Table Analysis Tools](media/tat-fillex.gif "Fill From Example button in Table Analysis Tools")</span></span>  
  
 <span data-ttu-id="760b0-104">L’outil **remplir à partir de l’exemple** vous permet de créer de nouvelles colonnes de données en fonction de valeurs existantes.</span><span class="sxs-lookup"><span data-stu-id="760b0-104">The **Fill From Example** tool helps you build new columns of data based on existing values.</span></span>  
  
 <span data-ttu-id="760b0-105">Par exemple, supposons que vos données contiennent une colonne **montant d’achat** , une colonne **quantité de commandes** et une colonne **client premier** basée sur une formule utilisant les autres colonnes.</span><span class="sxs-lookup"><span data-stu-id="760b0-105">For example, suppose your data contains a **Purchase Amount** column, an **Orders Quantity** column, and a **Premier Customer** column that is based on some formula using the other columns.</span></span> <span data-ttu-id="760b0-106">Si la colonne **client premier** contient de nombreuses lignes vides, vous pouvez utiliser les colonnes **montant des achats** et quantité de **commandes** comme entrées pour déduire les valeurs manquantes.</span><span class="sxs-lookup"><span data-stu-id="760b0-106">If the  **Premier Customer** column contains many blank rows, you could use the **Purchase Amount** and **Orders Quantity** columns as the inputs, to infer the missing values.</span></span> <span data-ttu-id="760b0-107">L'outil analyse les modèles existants dans les données conjointement avec les exemples entrés, et prédit quelle catégorie affecter à chaque client.</span><span class="sxs-lookup"><span data-stu-id="760b0-107">The tool analyzes existing patterns in the data together with the examples you entered, and predicts which category to assign to each customer.</span></span>  
  
 <span data-ttu-id="760b0-108">Si vous n'êtes pas satisfait des résultats, vous pouvez les affiner en fournissant des exemples supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="760b0-108">If you are not satisfied with the results, you can refine the results by providing more examples.</span></span>  
  
## <a name="using-the-fill-from-example-tool"></a><span data-ttu-id="760b0-109">Utilisation de l'outil Remplir à partir de l'exemple</span><span class="sxs-lookup"><span data-stu-id="760b0-109">Using the Fill From Example Tool</span></span>  
  
1.  <span data-ttu-id="760b0-110">Dans le ruban **analyser** , cliquez sur **remplir à partir de l’exemple**.</span><span class="sxs-lookup"><span data-stu-id="760b0-110">In the **Analyze** ribbon, click **Fill From Example**.</span></span>  
  
2.  <span data-ttu-id="760b0-111">L'outil choisit automatiquement une colonne à remplir en fonction de l'analyse des données et vous pouvez accepter ou ignorer cette suggestion.</span><span class="sxs-lookup"><span data-stu-id="760b0-111">The tool will automatically pick a column to fill based on analysis of the data, and you can either accept or override this suggestion.</span></span>  
  
3.  <span data-ttu-id="760b0-112">Créez une colonne pour les nouvelles données, puis tapez des exemples de données que vous souhaitez prédire.</span><span class="sxs-lookup"><span data-stu-id="760b0-112">Create a column for the new data, and type in examples of the data that you want to predict.</span></span> <span data-ttu-id="760b0-113">Veillez à ce qu'il existe au moins un exemple pour chaque valeur à prédire.</span><span class="sxs-lookup"><span data-stu-id="760b0-113">Make sure that there is at least one example for every value that you want to predict.</span></span> <span data-ttu-id="760b0-114">Si vous remplissez une colonne existante de données, sélectionnez celle dans laquelle il manque des valeurs.</span><span class="sxs-lookup"><span data-stu-id="760b0-114">If you are filling in data in an existing column, select the column that has missing values.</span></span>  
  
4.  <span data-ttu-id="760b0-115">Si vous le souhaitez, cliquez sur **choisir les colonnes à utiliser dans l’analyse**.</span><span class="sxs-lookup"><span data-stu-id="760b0-115">Optionally, click **Choose columns to be used in analysis**.</span></span> <span data-ttu-id="760b0-116">Dans la boîte de dialogue **Sélection avancée des colonnes** , spécifiez les colonnes qui sont les plus susceptibles d’être utiles lors du remplissage des données manquantes.</span><span class="sxs-lookup"><span data-stu-id="760b0-116">In the **Advanced Columns Selection** dialog box, specify the columns that are most likely to be useful when filling in the missing data.</span></span>  
  
     <span data-ttu-id="760b0-117">Par exemple, si vous savez par expérience qu'il existe un lien de cause à effet entre une colonne déterminée et une autre dans laquelle il manque des valeurs, vous pouvez désélectionner les autres colonnes pour obtenir de meilleurs résultats.</span><span class="sxs-lookup"><span data-stu-id="760b0-117">For example, if you know from experience that there is a causal effect between one column and the column that has missing values, you can deselect other columns to get better results.</span></span>  
  
     <span data-ttu-id="760b0-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="760b0-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="760b0-119">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="760b0-119">Click **Run**.</span></span>  
  
     <span data-ttu-id="760b0-120">Une fois l’analyse terminée, l’outil crée une nouvelle feuille de calcul **patterns** qui contient les résultats de l’analyse.</span><span class="sxs-lookup"><span data-stu-id="760b0-120">When analysis is complete, the tool creates a new **Patterns** worksheet that contains the results of analysis.</span></span> <span data-ttu-id="760b0-121">Le rapport répertorie les règles, ou facteurs d'influence clés, qui ont été trouvés, et montre la probabilité de chaque règle.</span><span class="sxs-lookup"><span data-stu-id="760b0-121">The report lists the rules, or key influencers, that were found, and shows the probability for each rule.</span></span>  
  
     <span data-ttu-id="760b0-122">L'outil ajoute également automatiquement une colonne contenant les nouvelles valeurs à la table de données d'origine.</span><span class="sxs-lookup"><span data-stu-id="760b0-122">The tool also automatically adds a column that contains the new values to the original data table.</span></span> <span data-ttu-id="760b0-123">Vous pouvez examiner les valeurs et les comparer à celles d'origine.</span><span class="sxs-lookup"><span data-stu-id="760b0-123">You can review the values and compare them against the original.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="760b0-124">Spécifications</span><span class="sxs-lookup"><span data-stu-id="760b0-124">Requirements</span></span>  
 <span data-ttu-id="760b0-125">Vous ne pouvez utiliser que des données de colonnes.</span><span class="sxs-lookup"><span data-stu-id="760b0-125">You can only work with data in columns.</span></span> <span data-ttu-id="760b0-126">Si la série que vous souhaitez remplir est stockée dans une ligne, vous pouvez utiliser la fonction de collage, transposition d'Excel pour mettre les données sous forme de colonne.</span><span class="sxs-lookup"><span data-stu-id="760b0-126">If the series that you want to fill is stored in a row, you can use the Paste, Transpose function in Excel to change the data to a columnar format.</span></span>  
  
## <a name="understanding-the-pattern-report"></a><span data-ttu-id="760b0-127">Présentation du rapport de séquence</span><span class="sxs-lookup"><span data-stu-id="760b0-127">Understanding the Pattern Report</span></span>  
 <span data-ttu-id="760b0-128">Lorsque vous exécutez l’outil **remplir à partir de l’exemple** , un rapport est créé et fournit des informations supplémentaires sur les modèles qui ont été détectés.</span><span class="sxs-lookup"><span data-stu-id="760b0-128">When you run the **Fill From Example** tool, a report is created that provides more information about the patterns that were detected.</span></span> <span data-ttu-id="760b0-129">Ces séquences servent à extrapoler les nouvelles valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="760b0-129">These patterns are used for extrapolating new data values.</span></span>  
  
 <span data-ttu-id="760b0-130">Le rapport de séquence présente les facteurs d'influence clés de chaque valeur qui a été prédite.</span><span class="sxs-lookup"><span data-stu-id="760b0-130">The Pattern Report shows the key influencers for each value that was predicted.</span></span> <span data-ttu-id="760b0-131">Chaque facteur d'influence (ou règle) est décrit comme étant la combinaison d'une colonne, de la valeur de cette colonne et de l'impact relatif de la règle sur la prédiction.</span><span class="sxs-lookup"><span data-stu-id="760b0-131">Each influencer or rule is described as a combination of a column, the value in that column, and the relative impact of the rule on the prediction.</span></span>  
  
 <span data-ttu-id="760b0-132">Par exemple, si vous essayez de remplir une feuille de calcul indiquant la distance de transport des marchandises commandées, vous pouvez vous attendre en toute logique à ce que la destination ait un fort impact sur cette valeur de distance.</span><span class="sxs-lookup"><span data-stu-id="760b0-132">For example, if you were trying to fill in a worksheet that shows the shipping distance for orders, you might logically expect the destination to have a strong impact on the value for shipping distance.</span></span> <span data-ttu-id="760b0-133">Dans ce cas, la requête peut contenir la ligne suivante :</span><span class="sxs-lookup"><span data-stu-id="760b0-133">In this case, the report might contain the following row:</span></span>  
  
|<span data-ttu-id="760b0-134">Colonne</span><span class="sxs-lookup"><span data-stu-id="760b0-134">Column</span></span>|<span data-ttu-id="760b0-135">Valeur</span><span class="sxs-lookup"><span data-stu-id="760b0-135">Value</span></span>|<span data-ttu-id="760b0-136">Privilèges</span><span class="sxs-lookup"><span data-stu-id="760b0-136">Favors</span></span>|<span data-ttu-id="760b0-137">Impact relatif</span><span class="sxs-lookup"><span data-stu-id="760b0-137">Relative Impact</span></span>|  
|------------|-----------|------------|---------------------|  
|<span data-ttu-id="760b0-138">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="760b0-138">StateProvinceCode</span></span>|<span data-ttu-id="760b0-139">AB</span><span class="sxs-lookup"><span data-stu-id="760b0-139">AB</span></span>|<span data-ttu-id="760b0-140">>500 kilomètres</span><span class="sxs-lookup"><span data-stu-id="760b0-140">>500 kilometers</span></span>|<span data-ttu-id="760b0-141">80 %</span><span class="sxs-lookup"><span data-stu-id="760b0-141">80%</span></span>|  
  
 <span data-ttu-id="760b0-142">Cela signifie que la valeur AB dans la colonne **StateProvinceCode** prédit fortement une distance d’expédition de >500 kilomètres.</span><span class="sxs-lookup"><span data-stu-id="760b0-142">This means that the value AB in the **StateProvinceCode** column strongly predicts a shipping distance of >500 kilometers.</span></span>  
  
 <span data-ttu-id="760b0-143">En règle générale, les prédictions reposent sur des séquences bien plus complexes que celles présentées dans cet exemple, et le rapport peut contenir de nombreuses lignes de règles pour chaque prédiction.</span><span class="sxs-lookup"><span data-stu-id="760b0-143">Typically, predictions are based on patterns that are far more complex than this example, and the report may contain many rows of rules for each prediction.</span></span> <span data-ttu-id="760b0-144">L'effet de toutes les règles se combine pour dériver la valeur prédite.</span><span class="sxs-lookup"><span data-stu-id="760b0-144">The effect of all the rules are combined to derive the predicted value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="760b0-145">L' **impact relatif** est représenté sous la forme d’une barre ombrée.</span><span class="sxs-lookup"><span data-stu-id="760b0-145">**Relative Impact** is shown as a shaded bar.</span></span> <span data-ttu-id="760b0-146">Plus la barre est longue, plus grande est la probabilité que cette règle est prédictive de la valeur de remplissage.</span><span class="sxs-lookup"><span data-stu-id="760b0-146">The longer the bar, the greater the probability that this rule is predictive of the filled-in value.</span></span>  
  
 <span data-ttu-id="760b0-147">L’outil ajoute également une nouvelle colonne à la table de données d’origine nommée \<column name> Extended.</span><span class="sxs-lookup"><span data-stu-id="760b0-147">The tool also adds a new column to the original data table, named \<column name> Extended.</span></span>  
  
 <span data-ttu-id="760b0-148">Si la colonne de données d'origine contenait une valeur, celle-ci est copiée dans la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="760b0-148">If the original data column contained a value, that value is copied into the new column.</span></span> <span data-ttu-id="760b0-149">En revanche, si la colonne d'origine contenait une cellule vide, la nouvelle colonne contient la valeur qui a été prédite par l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="760b0-149">However, if the original column contained a blank cell, the new column contains the value that was predicted by the wizard.</span></span>  
  
## <a name="related-tools-and-information"></a><span data-ttu-id="760b0-150">Outils et informations connexes</span><span class="sxs-lookup"><span data-stu-id="760b0-150">Related Tools and Information</span></span>  
 <span data-ttu-id="760b0-151">Vous pouvez également utiliser l’Assistant [Explorer les données](explore-data-sql-server-data-mining-add-ins.md) , disponible dans le client d’exploration de données pour Excel, pour examiner la distribution des valeurs dans une colonne Excel.</span><span class="sxs-lookup"><span data-stu-id="760b0-151">You can also use the [Explore Data](explore-data-sql-server-data-mining-add-ins.md) wizard, available in the Data Mining Client for Excel, to examine the distribution of values in an Excel column.</span></span> <span data-ttu-id="760b0-152">Pour plus d’informations, consultez [exploration et nettoyage des données](exploring-and-cleaning-data.md).</span><span class="sxs-lookup"><span data-stu-id="760b0-152">For more information, see [Exploring and Cleaning Data](exploring-and-cleaning-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760b0-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="760b0-153">See Also</span></span>  
 [<span data-ttu-id="760b0-154">Outils d'analyse de table pour Excel</span><span class="sxs-lookup"><span data-stu-id="760b0-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
