---
title: Analyser les influenceurs clés (outils d’analyse de table pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- key influencers
- factor analysis
ms.assetid: 54d7b4ce-7b79-407a-985c-aa655ad19280
author: minewiskan
ms.author: owend
ms.openlocfilehash: f60eb5144059b0976d52eec2329f27553132146c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602633"
---
# <a name="analyze-key-influencers-table-analysis-tools-for-excel"></a><span data-ttu-id="5d2a1-102">Analyser les facteurs d'influence clés (Outils d'analyse de table pour Excel)</span><span class="sxs-lookup"><span data-stu-id="5d2a1-102">Analyze Key Influencers (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="5d2a1-103">![Bouton Analyser les facteurs d'influence clés du ruban](media/tat-aki.gif "Bouton Analyser les facteurs d'influence clés du ruban")</span><span class="sxs-lookup"><span data-stu-id="5d2a1-103">![Analyze Key Influencers button in ribbon](media/tat-aki.gif "Analyze Key Influencers button in ribbon")</span></span>  
  
 <span data-ttu-id="5d2a1-104">Avec l’outil analyser les facteurs d' **influence clés** , vous choisissez une colonne qui contient un résultat cible, et l’algorithme détermine les facteurs qui ont le plus fort impact sur le résultat.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-104">With the **Analyze Key Influencers** tool, you choose a column that contains a target outcome, and the algorithm determines which factors had the strongest influence on the outcome.</span></span>  
  
 <span data-ttu-id="5d2a1-105">L'outil crée de nouvelles tables de données qui signalent les facteurs associés à chaque résultat et qui affichent de manière graphique la probabilité de la relation.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-105">The tool creates new data tables that report the factors associated with each outcome and graphically displays the probability of the relationship.</span></span> <span data-ttu-id="5d2a1-106">Vous pouvez filtrer les tables en fonction de différents facteurs et résultats pour analyser les résultats de manière plus approfondie.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-106">You can filter the tables by different factors and outcomes to explore the results in more depth.</span></span>  
  
 <span data-ttu-id="5d2a1-107">Vous pouvez également sélectionner une paire de résultats possibles et les comparer.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-107">You can also select a pair of possible outcomes and compare them.</span></span> <span data-ttu-id="5d2a1-108">Par exemple, vous pouvez comparer différents groupes de consommateurs pour déterminer les facteurs possibles de prise de décision.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-108">For example, you might compare different groups of consumers to determine possible decision-making factors.</span></span>  
  
## <a name="using-the-analyze-key-influencers-tool"></a><span data-ttu-id="5d2a1-109">Utilisation de l'outil Analyser les facteurs d'influence clés</span><span class="sxs-lookup"><span data-stu-id="5d2a1-109">Using the Analyze Key Influencers Tool</span></span>  
  
1.  <span data-ttu-id="5d2a1-110">Ouvrez une table de données Excel.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-110">Open an Excel data table.</span></span>  
  
2.  <span data-ttu-id="5d2a1-111">Dans **outils de table**, dans le ruban **analyser** , cliquez sur **analyser les influenceurs clés.**</span><span class="sxs-lookup"><span data-stu-id="5d2a1-111">In **Table Tools**, on the **Analyze** ribbon, click **Analyze Key Influencers.**</span></span>  
  
3.  <span data-ttu-id="5d2a1-112">Sélectionnez la seule colonne qui est la cible de l'analyse.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-112">Select the single column that is the target of analysis.</span></span>  
  
4.  <span data-ttu-id="5d2a1-113">Si vous le souhaitez, cliquez sur **choisir les colonnes à utiliser pour l’analyse**.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-113">Optionally, click **Choose columns to be used for analysis**.</span></span> <span data-ttu-id="5d2a1-114">Dans la boîte de dialogue **Sélection avancée de colonnes** , choisissez les colonnes susceptibles de contenir les données pertinentes.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-114">In the **Advanced Columns Selection** dialog box, choose the columns that are most likely to contain relevant data.</span></span> <span data-ttu-id="5d2a1-115">Pour améliorer les performances et la précision, désélectionnez les colonnes telles que ID ou Nom qui ne sont pas importantes pour l'analyse des séquences.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-115">To improve performance and accuracy, deselect columns such as ID or name that are unimportant for pattern analysis.</span></span> <span data-ttu-id="5d2a1-116">Cliquez sur **OK** pour fermer la boîte de dialogue **Sélection avancée de colonnes** .</span><span class="sxs-lookup"><span data-stu-id="5d2a1-116">Click **OK** to close the **Advanced Columns Selection** dialog box.</span></span>  
  
5.  <span data-ttu-id="5d2a1-117">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-117">Click **Run**.</span></span>  
  
     <span data-ttu-id="5d2a1-118">L’outil **analyser les acteurs clés** analyse les données pour déterminer les paramètres optimaux et définit automatiquement tous les paramètres.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-118">The **Analyze Key Influencers** tool conducts an analysis of the data to determine the optimum settings, and sets all parameters automatically.</span></span>  
  
6.  <span data-ttu-id="5d2a1-119">Si aucune séquence n'est détectée, l'Assistant crée une nouvelle feuille de calcul qui contient une description du problème.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-119">If no patterns were detected, the wizard creates a new worksheet that contains a description of the problem.</span></span>  
  
7.  <span data-ttu-id="5d2a1-120">Si des séquences sont détectées, l'Assistant crée un rapport sur une nouvelle feuille de calcul qui affiche les séquences.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-120">If patterns are detected, the wizard creates a report on a new worksheet that shows the patterns.</span></span> <span data-ttu-id="5d2a1-121">Le rapport est nommé \*\*influenceurs clés pour \<column> \*\*.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-121">The report is named **Key Influencers for \<column>**.</span></span> <span data-ttu-id="5d2a1-122">Vous pouvez personnaliser le rapport comme indiqué dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-122">You can customize the report as described in the following procedure.</span></span>  
  
#### <a name="create-a-custom-report"></a><span data-ttu-id="5d2a1-123">Créer un rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="5d2a1-123">Create a custom report</span></span>  
  
1.  <span data-ttu-id="5d2a1-124">Dans la boîte de dialogue **discrimination basée sur** les éléments d’influence clés, choisissez les deux valeurs que vous souhaitez comparer en les sélectionnant dans les listes déroulantes **valeur 1** et **valeur 2** .</span><span class="sxs-lookup"><span data-stu-id="5d2a1-124">In the **Discrimination based on key influencers** dialog box, choose the two values that you want to compare by selecting them from the **Value 1** and **Value 2** dropdown lists.</span></span> <span data-ttu-id="5d2a1-125">Vous pouvez, par exemple, comparer les acheteurs aux non-acheteurs.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-125">For example, you might compare buyers to non-buyers.</span></span>  
  
2.  <span data-ttu-id="5d2a1-126">Cliquez sur **Ajouter un rapport**.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-126">Click **Add Report**.</span></span>  
  
     <span data-ttu-id="5d2a1-127">L'Assistant crée une nouvelle feuille de calcul et ajoute une table pour chaque paire de comparaisons de facteurs clés.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-127">The wizard creates a new worksheet and adds a table for each pair of key factor comparisons.</span></span>  
  
3.  <span data-ttu-id="5d2a1-128">Lorsque vous avez terminé d’effectuer des comparaisons, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-128">When you are done making comparisons, click **Close**.</span></span>  
  
## <a name="understanding-the-key-influencers-report"></a><span data-ttu-id="5d2a1-129">Présentation du rapport des facteurs d'influence clés</span><span class="sxs-lookup"><span data-stu-id="5d2a1-129">Understanding the Key Influencers Report</span></span>  
 <span data-ttu-id="5d2a1-130">Une fois le modèle de données créé, l’outil **analyser les influenceurs clés** crée des rapports qui vous aident à explorer et à comparer les influenceurs clés.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-130">After the data model has been created, the **Analyze Key Influencers** tool creates reports that help you explore and compare key influencers.</span></span>  
  
-   <span data-ttu-id="5d2a1-131">Le rapport à gauche est celui qui est généré par défaut.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-131">The report on the left side is the one generated by default.</span></span> <span data-ttu-id="5d2a1-132">Il affiche les prédicteurs les plus forts de la colonne de résultats (la variable dépendante).</span><span class="sxs-lookup"><span data-stu-id="5d2a1-132">It shows the strongest predictors of the outcome column (the dependent variable).</span></span>  
  
-   <span data-ttu-id="5d2a1-133">Le rapport à droite est facultatif, créez-le en comparant deux valeurs de résultat spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-133">The report on the right side is optional, which you can create by comparing two specific outcome values.</span></span> <span data-ttu-id="5d2a1-134">Ce rapport compare les acheteurs et les non acheteurs.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-134">This report compares buyers and non-buyers.</span></span>  
  
-   <span data-ttu-id="5d2a1-135">Notez qu'une nouvelle feuille de calcul est ajoutée pour chaque rapport que vous créez.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-135">Note that a new worksheet is added for each report that you create.</span></span> <span data-ttu-id="5d2a1-136">Déplacez les tables une fois qu'elles sont créées ; nous les avons placées côte à côte pour la comparaison.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-136">You can move the tables after they are created; we placed them side by side for comparison.</span></span>  
  
 <span data-ttu-id="5d2a1-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span><span class="sxs-lookup"><span data-stu-id="5d2a1-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span></span>  
  
 <span data-ttu-id="5d2a1-138">**Impact relatif**</span><span class="sxs-lookup"><span data-stu-id="5d2a1-138">**Relative Impact**</span></span>  
 <span data-ttu-id="5d2a1-139">La barre grisée dans le premier rapport indique l'intensité de l'association de cet attribut avec le résultat.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-139">The shaded bar in the first report indicates the strength of the association of this attribute with the outcome.</span></span>  
  
 <span data-ttu-id="5d2a1-140">La longueur de la barre indique dans quelle mesure (degré de probabilité) le facteur contribuera au résultat ; par conséquent, plus la barre ombrée est longue, plus l'association est forte.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-140">The length of the bar indicates the probability that the factor contributes to the outcome; therefore, the longer the shaded bar, the stronger the association.</span></span>  
  
 <span data-ttu-id="5d2a1-141">**Privilèges**</span><span class="sxs-lookup"><span data-stu-id="5d2a1-141">**Favors**</span></span>  
 <span data-ttu-id="5d2a1-142">Dans le deuxième rapport, les valeurs cible que vous comparez figurent dans deux colonnes, avec les facteurs connexes répertoriés par ordre de confiance décroissant.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-142">In the second report, the target values that you compare are listed in two columns, with the related factors listed in order of descending confidence.</span></span>  
  
-   <span data-ttu-id="5d2a1-143">La barre **bleue** affiche les attributs qui contribuent au résultat, « non » (= n’a pas été acheté).</span><span class="sxs-lookup"><span data-stu-id="5d2a1-143">The **blue** bar shows attributes contributing to the outcome, "No" (=did not purchase).</span></span>  
  
-   <span data-ttu-id="5d2a1-144">La barre **rouge** affiche les attributs qui contribuent au résultat, « oui » (= acheté un vélo).</span><span class="sxs-lookup"><span data-stu-id="5d2a1-144">The **red** bar shows attributes contributing to the outcome, "Yes" (=purchased a bike).</span></span>  
  
 <span data-ttu-id="5d2a1-145">Les couleurs de la barre d'ombrage sont arbitraires.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-145">The colors in the shading bar are arbitrary.</span></span> <span data-ttu-id="5d2a1-146">Vous pouvez modifier ces couleurs en définissant les options du mode création de table dans Excel.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-146">You can change these colors by setting the options for table design in Excel.</span></span>  
  
 <span data-ttu-id="5d2a1-147">Dans un rapport qui différencie deux valeurs, le deuxième rapport classe les facteurs d'influence clés en fonction de l'impact sur les valeurs cibles.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-147">In a report that contrasts two values, the second report ranks the key influencers by the amount of impact on the target values.</span></span>  
  
 <span data-ttu-id="5d2a1-148">Étant donné que tous les graphiques sont basés sur des tableaux Excel, filtrez et triez pour mettre l'accent sur des facteurs ou résultats spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-148">Because all the charts are based on Excel tables, you can filter and sort to focus on specific factors or outcomes.</span></span>  
  
## <a name="more-about-the-analyze-key-influencers-tool"></a><span data-ttu-id="5d2a1-149">En savoir plus sur l'outil Analyser les facteurs d'influence clés</span><span class="sxs-lookup"><span data-stu-id="5d2a1-149">More About the Analyze Key Influencers Tool</span></span>  
 <span data-ttu-id="5d2a1-150">Lorsque l’outil analyser les éléments d' **influence clés** analyse vos données, il effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5d2a1-150">When the **Analyze Key Influencers** tool analyzes your data, it does the following:</span></span>  
  
-   <span data-ttu-id="5d2a1-151">Il crée une structure de données qui stocke des informations clés à propos de la distribution de vos données.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-151">Creates a data structure that stores key information about the distribution of your data.</span></span>  
  
-   <span data-ttu-id="5d2a1-152">Il crée un modèle d'exploration de données à l'aide de l'algorithme MNB (Microsoft Naïve Bayes).</span><span class="sxs-lookup"><span data-stu-id="5d2a1-152">Creates a model using the Microsoft Naïve Bayes algorithm.</span></span>  
  
-   <span data-ttu-id="5d2a1-153">Il crée des prédictions qui corrèle chaque colonne de données avec les résultats spécifiés.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-153">Creates predictions that correlates each column of data with the specified outcome.</span></span>  
  
-   <span data-ttu-id="5d2a1-154">Il utilise le score de confiance de chacune des prédictions pour identifier les facteurs qui ont le plus d'influence lors de l'obtention du résultat ciblé.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-154">Uses the confidence score for each of the predictions to identify the factors that are the most influential in producing the targeted outcome.</span></span>  
  
-   <span data-ttu-id="5d2a1-155">Il crée un rapport décrivant les facteurs d'influence clés, classés par scores de confiance.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-155">Creates a report describing the key influencers, ordered by confidence scores.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="5d2a1-156">Spécifications</span><span class="sxs-lookup"><span data-stu-id="5d2a1-156">Requirements</span></span>  
 <span data-ttu-id="5d2a1-157">Si la colonne cible contient des valeurs numériques continues, l'outil segmente automatiquement les valeurs numériques dans des groupes.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-157">If the target column contains continuous numeric values, the tool automatically segments the numeric values into groups.</span></span> <span data-ttu-id="5d2a1-158">Ces regroupements représentent des clusters de cas possédant des caractéristiques similaires.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-158">These groupings represent clusters of cases that have similar characteristics.</span></span> <span data-ttu-id="5d2a1-159">Cependant, les valeurs numériques ne peuvent pas être divisées en groupes conviviaux.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-159">However, numeric values might not be divided into user-friendly groups.</span></span> <span data-ttu-id="5d2a1-160">Par exemple, le rapport peut contenir un regroupement tel que « \< 12,85701 », tandis que les utilisateurs du rapport souhaitent généralement voir des regroupements qui utilisent des nombres entiers, tels que 10-19, 20-29, etc.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-160">For example, the report might contain a grouping such as "\<12.85701", whereas report users typically like to see groupings that use whole numbers, such as 10-19, 20-29, and so on.</span></span>  
  
 <span data-ttu-id="5d2a1-161">Si vous voulez regrouper vos données numériques d'une autre manière, vous devez segmenter les données comme vous le souhaitez avant de créer l'analyse.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-161">If you want to group numeric data in a different way, you must segment the data the way you want before creating the analysis.</span></span> <span data-ttu-id="5d2a1-162">Par exemple, vous pouvez utiliser l’outil [réétiqueter](relabel-sql-server-data-mining-add-ins.md) du client d’exploration de données pour Excel pour créer une nouvelle étiquette de regroupement dans une colonne distincte, puis utiliser uniquement cette nouvelle colonne dans l’analyse.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-162">For example, you can use the [Relabel](relabel-sql-server-data-mining-add-ins.md) tool in the Data Mining Client for Excel to create a new grouping label in a separate column, and then use only that new column in analysis.</span></span>  
  
### <a name="related-tools"></a><span data-ttu-id="5d2a1-163">Outils connexes</span><span class="sxs-lookup"><span data-stu-id="5d2a1-163">Related Tools</span></span>  
 <span data-ttu-id="5d2a1-164">Le ruban d' **exploration de données** fournit des outils plus avancés, y compris la possibilité de personnaliser les modèles d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="5d2a1-164">The **Data Mining** ribbon provides more advanced tools, including the ability to customize data mining models</span></span>  
  
 <span data-ttu-id="5d2a1-165">Si vous enregistrez votre modèle à l’aide de l’outil **analyser les influenceurs clés** , vous pouvez utiliser le client d’exploration de données pour parcourir le modèle et explorer les relations plus en détail.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-165">If you save your model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="5d2a1-166">Pour plus d’informations, consultez [navigation dans les modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="5d2a1-166">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span> <span data-ttu-id="5d2a1-167">Vous pouvez également utiliser Microsoft Office Visio pour créer des graphiques et des diagrammes qui présentent les relations sous forme de réseaux de dépendances ou de clusters.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-167">You can also use Microsoft Office Visio to create charts and diagrams that display the relationships as cluster or as dependency networks.</span></span> <span data-ttu-id="5d2a1-168">Pour plus d’informations, consultez [Dépannage des diagrammes d’exploration de données Visio &#40;SQL Server des compléments d’exploration de données&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="5d2a1-168">For more information, see [Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d2a1-169">Les modèles créés lorsque vous utilisez les outils d'analyse de table sont supprimés lorsque vous fermez votre feuille de calcul ou mettez fin à la connexion avec le serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d2a1-169">The models that are created when you use the Table Analysis Tools are deleted when you close your worksheet or terminate the connection with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span> <span data-ttu-id="5d2a1-170">Par conséquent, vous ne pouvez parcourir les modèles que tant que la connexion reste active.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-170">Therefore, you can only browse the models as long as the connection remains open.</span></span> <span data-ttu-id="5d2a1-171">Vous ne pouvez pas restituer les modèles dans Visio si vous désactivez la connexion ou fermez la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-171">You cannot render the models in Visio if you close the connection or close the worksheet.</span></span>  
  
 <span data-ttu-id="5d2a1-172">Pour plus d’informations sur l’algorithme utilisé par l’outil **analyser les influenceurs clés** , consultez « algorithme Microsoft Naïve Bayes » dans documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d2a1-172">For more information about the algorithm used by the **Analyze Key Influencers** tool, see "Microsoft Naïve Bayes Algorithm" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2a1-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d2a1-173">See Also</span></span>  
 <span data-ttu-id="5d2a1-174">[Outils d’analyse de table pour Excel](table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="5d2a1-174">[Table Analysis Tools for Excel](table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="5d2a1-175">Création d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5d2a1-175">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
