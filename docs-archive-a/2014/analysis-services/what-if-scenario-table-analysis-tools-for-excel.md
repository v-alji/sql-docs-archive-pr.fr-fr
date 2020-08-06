---
title: Scénario de scénarios (outils d’analyse de table pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- what if scenario
- scenario analysis
ms.assetid: 4df5a5c5-1983-4009-a7c5-cd340649fd2f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4bb5c5e866c1320c297fb4f2760bca58623f6601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710828"
---
# <a name="what-if-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="8caaa-102">Scénario (Outils d'analyse de table pour Excel)</span><span class="sxs-lookup"><span data-stu-id="8caaa-102">What-If Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="8caaa-103">![Bouton Scénarios des Outils d'analyse de table](media/tat-whatif.gif "Bouton Scénarios des Outils d'analyse de table")</span><span class="sxs-lookup"><span data-stu-id="8caaa-103">![What If Scenario button in Table Analysis tools](media/tat-whatif.gif "What If Scenario button in Table Analysis tools")</span></span>

 <span data-ttu-id="8caaa-104">L' **outil scénario analyse** les séquences dans les données existantes, puis vous permet d’évaluer l’effet que les modifications apportées à une colonne ont sur la valeur d’une autre colonne.</span><span class="sxs-lookup"><span data-stu-id="8caaa-104">The **What-If** scenario tool analyzes patterns in existing data, and then enables you to evaluate the effect that changes in one column would have on the value of a different column.</span></span>

 <span data-ttu-id="8caaa-105">Vous pouvez, par exemple, examiner l'effet qu'une augmentation de prix d'un article aurait sur le total de ses ventes.</span><span class="sxs-lookup"><span data-stu-id="8caaa-105">For example, you could explore the effect of raising the price of an item on its total sales.</span></span>

 <span data-ttu-id="8caaa-106">L'outil est flexible quant au nombre de prédictions que vous pouvez créer.</span><span class="sxs-lookup"><span data-stu-id="8caaa-106">The tool is flexible about the number of predictions you can create.</span></span> <span data-ttu-id="8caaa-107">Après l'analyse initiale, vous pouvez choisir de prédire les modifications pour toutes les données de la table ou bien d'entrer les valeurs de test une par une.</span><span class="sxs-lookup"><span data-stu-id="8caaa-107">After the initial analysis is complete, you can either predict changes for all the data in the table, or enter test values one at a time.</span></span>

## <a name="using-the-what-if-scenario-tool"></a><span data-ttu-id="8caaa-108">Utilisation de l'outil Scénario</span><span class="sxs-lookup"><span data-stu-id="8caaa-108">Using the What-If Scenario Tool</span></span>

1.  <span data-ttu-id="8caaa-109">Ouvrez une table de données Excel.</span><span class="sxs-lookup"><span data-stu-id="8caaa-109">Open an Excel data table.</span></span>

2.  <span data-ttu-id="8caaa-110">Cliquez sur **scénarios**, puis sélectionnez **quoi-faire**.</span><span class="sxs-lookup"><span data-stu-id="8caaa-110">Click **Scenarios**, and then select **What-If**.</span></span>

3.  <span data-ttu-id="8caaa-111">Dans la zone **scénario** , sélectionnez la colonne qui contient la valeur que vous allez modifier, puis spécifiez la modification en tant que valeur spécifique ou en pourcentage de modification (augmentée ou diminuée) sur les valeurs actuelles.</span><span class="sxs-lookup"><span data-stu-id="8caaa-111">In the **Scenario** box, select the column that contains the value you will change, and specify the change either as a specific value or as a percentage of change (either increased or decreased) on the current values.</span></span>

4.  <span data-ttu-id="8caaa-112">Dans la zone **qu’est-ce qui se passe** , spécifiez la colonne pour laquelle vous souhaitez évaluer l’effet.</span><span class="sxs-lookup"><span data-stu-id="8caaa-112">In the **What happens to** box, specify the column for which you want to assess the effect.</span></span>

5.  <span data-ttu-id="8caaa-113">Si vous le souhaitez, cliquez sur **choisir les colonnes à utiliser pour l’analyse** pour sélectionner les colonnes qui sont susceptibles d’être utiles pour effectuer la prédiction.</span><span class="sxs-lookup"><span data-stu-id="8caaa-113">Optionally, click **Choose columns to be used for analysis** to select columns that are likely to be useful in making the prediction.</span></span> <span data-ttu-id="8caaa-114">Vous pouvez également désélectionner les colonnes qui risquent de n'avoir aucune ou peu d'utilité pour la détection des séquences de données remarquables, telles que les ID et noms de lignes.</span><span class="sxs-lookup"><span data-stu-id="8caaa-114">You can also deselect columns that are likely to be of little use in detecting patterns, such as row IDs or names.</span></span>

6.  <span data-ttu-id="8caaa-115">Dans la zone **spécifier la ligne ou la table** , indiquez si vous souhaitez que l’impact soit évalué pour la ligne actuellement sélectionnée uniquement ou pour l’ensemble complet de données de la table.</span><span class="sxs-lookup"><span data-stu-id="8caaa-115">In the **Specify row or table** box, choose whether you want the impact assessed for the currently selected row only, or for the complete set of data in the table.</span></span>

7.  <span data-ttu-id="8caaa-116">Si vous sélectionnez **sur cette ligne**, l’outil affiche le résultat dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="8caaa-116">If you select **On this row**, the tool displays the result in the dialog box.</span></span> <span data-ttu-id="8caaa-117">Tant que la boîte de dialogue est ouverte, vous pouvez modifier vos choix pour tester d'autres scénarios.</span><span class="sxs-lookup"><span data-stu-id="8caaa-117">While the dialog box remains open, you can modify your selections to test other scenarios.</span></span>

8.  <span data-ttu-id="8caaa-118">Si vous sélectionnez la **table entière**, l’outil affiche un message d’État dans la boîte de dialogue et ajoute deux nouvelles colonnes à la table de données d’origine.</span><span class="sxs-lookup"><span data-stu-id="8caaa-118">If you select **Entire table**, the tool displays a status message in the dialog box, and adds two new columns to the original data table.</span></span> <span data-ttu-id="8caaa-119">Cliquez sur **Fermer** pour afficher toutes les résultats dans la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="8caaa-119">Click **Close** to view the complete results in the worksheet.</span></span>

### <a name="requirements"></a><span data-ttu-id="8caaa-120">Spécifications</span><span class="sxs-lookup"><span data-stu-id="8caaa-120">Requirements</span></span>
 <span data-ttu-id="8caaa-121">Cet outil utilise l'algorithme MLR (Microsoft Logistic Regression), qui prend en charge la prédiction de valeurs numériques ou discrètes.</span><span class="sxs-lookup"><span data-stu-id="8caaa-121">This tool uses the Microsoft Logistic Regression algorithm, which supports prediction of either numeric or discrete values.</span></span> <span data-ttu-id="8caaa-122">Cependant, nous suggérons les meilleures pratiques suivantes pour maximiser les résultats :</span><span class="sxs-lookup"><span data-stu-id="8caaa-122">However, to achieve the best results, we suggest the following best practices:</span></span>

-   <span data-ttu-id="8caaa-123">Sélectionnez les colonnes contenant des informations utiles à l'analyse.</span><span class="sxs-lookup"><span data-stu-id="8caaa-123">Select columns for analysis that contain useful information.</span></span>

-   <span data-ttu-id="8caaa-124">Si vous ne sélectionnez pas assez de colonnes, il peut être difficile de parvenir à un résultat.</span><span class="sxs-lookup"><span data-stu-id="8caaa-124">If you include too few columns it may be difficult to obtain a result.</span></span>

-   <span data-ttu-id="8caaa-125">Si vous utilisez l’option **to value** , vous devez taper une valeur dans la zone ou sélectionner une valeur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8caaa-125">If you use the **To value** option, you must type a value in the box or select a value from the list.</span></span>

-   <span data-ttu-id="8caaa-126">Si vous utilisez l’option **pourcentage** , définissez la modification comme une augmentation ou une diminution de pourcentage.</span><span class="sxs-lookup"><span data-stu-id="8caaa-126">If you use the **Percentage** option, set the change as a percentage increase or decrease.</span></span> <span data-ttu-id="8caaa-127">La valeur par défaut est de 120 %, ce qui correspond à une augmentation de 20 % par rapport à la valeur actuelle.</span><span class="sxs-lookup"><span data-stu-id="8caaa-127">The default is 120%, meaning a 20% increase over the current value.</span></span>

> [!NOTE]
>  <span data-ttu-id="8caaa-128">Si vous ne définissez pas de valeur, vous risquez de recevoir un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="8caaa-128">If you do not set a value, you might receive an error.</span></span>

## <a name="understanding-the-results-of-what-if-analysis"></a><span data-ttu-id="8caaa-129">Explication des résultats de l'analyse de scénarios</span><span class="sxs-lookup"><span data-stu-id="8caaa-129">Understanding the Results of What-If Analysis</span></span>
 <span data-ttu-id="8caaa-130">Lorsque vous créez un scénario de **simulation** , l’outil effectue trois opérations :</span><span class="sxs-lookup"><span data-stu-id="8caaa-130">When you create a **What-If** scenario, the tool does three things:</span></span>

-   <span data-ttu-id="8caaa-131">il crée une structure d'exploration de données qui stocke des faits clés à propos des données de votre table ;</span><span class="sxs-lookup"><span data-stu-id="8caaa-131">Creates a data mining structure that stores key facts about the data in your table.</span></span>

-   <span data-ttu-id="8caaa-132">il crée un modèle d'exploration de données de régression logistique basé sur vos données ;</span><span class="sxs-lookup"><span data-stu-id="8caaa-132">Creates a logistic regression mining model based on the data.</span></span>

-   <span data-ttu-id="8caaa-133">il crée une requête de prédiction pour chacune des valeurs que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="8caaa-133">Creates a prediction query for each of the values you specify.</span></span>

 <span data-ttu-id="8caaa-134">Vous pouvez générer toutes les prédictions en une seule fois en spécifiant la **table entière**.</span><span class="sxs-lookup"><span data-stu-id="8caaa-134">You can output all the predictions at one time by specifying **Entire table**.</span></span> <span data-ttu-id="8caaa-135">L'outil crée ensuite deux nouvelles colonnes dans la table de données d'origine.</span><span class="sxs-lookup"><span data-stu-id="8caaa-135">The tool then creates two new columns in the original data table.</span></span>

 <span data-ttu-id="8caaa-136">Les colonnes ajoutées à la table contiennent deux types d'informations : la valeur prédite en fonction de la modification et son niveau de confiance.</span><span class="sxs-lookup"><span data-stu-id="8caaa-136">The columns that are added to the table contain two types of information: the predicted value given the change, and its confidence.</span></span> <span data-ttu-id="8caaa-137">La confiance correspond à la probabilité que la prédiction est correcte.</span><span class="sxs-lookup"><span data-stu-id="8caaa-137">Confidence means the probability that the prediction is correct.</span></span>

 <span data-ttu-id="8caaa-138">Vous pouvez également entrer une par une les valeurs à modifier dans la boîte de dialogue et afficher les prédictions de manière interactive.</span><span class="sxs-lookup"><span data-stu-id="8caaa-138">You can also enter change values one by one in the dialog box, and view the predictions interactively.</span></span> <span data-ttu-id="8caaa-139">Cela revient à créer une requête de *prédiction Singleton*.</span><span class="sxs-lookup"><span data-stu-id="8caaa-139">This is the same as creating a *singleton prediction query*.</span></span> <span data-ttu-id="8caaa-140">Les résultats de la requête de prédiction s'affichent avec les informations suivantes : la réussite ou l'échec de la prédiction, la valeur prédite et le niveau de confiance.</span><span class="sxs-lookup"><span data-stu-id="8caaa-140">The results of the prediction query are output with the following information: the success or failure of prediction, the predicted value, and the confidence level.</span></span> <span data-ttu-id="8caaa-141">Le niveau de confiance apparaît sous la forme d'une barre contenant une ligne pointillée.</span><span class="sxs-lookup"><span data-stu-id="8caaa-141">The confidence level is shown as a bar that contains a dotted line.</span></span> <span data-ttu-id="8caaa-142">Plus la ligne pointillée est longue, puis le niveau de confiance du résultat est élevé.</span><span class="sxs-lookup"><span data-stu-id="8caaa-142">The longer the dotted line, the higher the confidence in the result.</span></span>

 <span data-ttu-id="8caaa-143">Par exemple, si vous essayez de déterminer l’effet de l’augmentation de l’âge du client sur la volonté du client d’acheter et d’augmenter l’âge du client à 25, l’outil de **simulation** interroge le modèle d’exploration de données et renvoie le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="8caaa-143">For example, if you are trying to determine the effect of increasing the customer's age on the customer's willingness to buy, and increase the customer's age to 25, the **What-If** tool queries the data mining model and returns the following result:</span></span>

 <span data-ttu-id="8caaa-144">**L'analyse de scénarios pour Achats vélo a trouvé une solution.**</span><span class="sxs-lookup"><span data-stu-id="8caaa-144">**What-If Analysis for Purchases Bicycle has found a solution.**</span></span>

 <span data-ttu-id="8caaa-145">**'Achats vélo' = yes**</span><span class="sxs-lookup"><span data-stu-id="8caaa-145">**'Purchases Bicycle' = yes**</span></span>

 <span data-ttu-id="8caaa-146">**Confiance : Correcte**</span><span class="sxs-lookup"><span data-stu-id="8caaa-146">**Confidence: Fair**</span></span>

 <span data-ttu-id="8caaa-147">Ce résultat étant basé sur une ligne existante de la table de données, cela signifie qu'il y a un client spécifique qui, si tous les facteurs restaient les mêmes sauf son âge qui augmenterait à 25 ans, serait susceptible d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="8caaa-147">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's age was increased to 25, the customer would likely buy a bicycle.</span></span>

 <span data-ttu-id="8caaa-148">La sortie des prédictions dans la table de données d'origine peut vous permettre de déterminer plus facilement si ces prédictions sont utiles.</span><span class="sxs-lookup"><span data-stu-id="8caaa-148">Outputting the predictions to the original data table might make it easier to determine whether the predictions are useful.</span></span>

## <a name="related-tools"></a><span data-ttu-id="8caaa-149">Outils connexes</span><span class="sxs-lookup"><span data-stu-id="8caaa-149">Related Tools</span></span>
 <span data-ttu-id="8caaa-150">Le client d'exploration de données pour Excel, un complément séparé qui fournit des fonctionnalités d'exploration de données plus avancées, comprend des Assistants pour créer des modèles d'exploration de données qui prédisent le comportement.</span><span class="sxs-lookup"><span data-stu-id="8caaa-150">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="8caaa-151">Pour plus d’informations, consultez [création d’un modèle d’exploration de données](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="8caaa-151">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="8caaa-152">Pour plus d’informations sur l’algorithme utilisé par l’outil scénario de **simulation** , consultez la rubrique « algorithme de régression logistique Microsoft » dans documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8caaa-152">For more information about the algorithm used by the **What-If** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in SQL Server Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="8caaa-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8caaa-153">See Also</span></span>
 [<span data-ttu-id="8caaa-154">Outils d'analyse de table pour Excel</span><span class="sxs-lookup"><span data-stu-id="8caaa-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


