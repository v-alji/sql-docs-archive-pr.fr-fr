---
title: Création de prédictions (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a8410ed2-bb98-4d51-a9eb-b239be1201c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 456aec6c6b9d0d1a5d0ee1d9949507a37577130c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694884"
---
# <a name="creating-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="4cf87-102">Création de prédictions (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="4cf87-102">Creating Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="4cf87-103">Une fois que vous avez testé la précision de vos modèles d’exploration de données et décidé que vous êtes satisfait des résultats, vous pouvez générer des prédictions à l’aide de la Générateur de requêtes de prédiction sous l’onglet **prédiction de modèle d’exploration** de données du concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="4cf87-103">After you have tested the accuracy of your mining models and decided that you are satisfied with the results, you can then generate predictions by using the Prediction Query Builder on the **Mining Model Prediction** tab in the Data Mining Designer.</span></span>  
  
 <span data-ttu-id="4cf87-104">Le Générateur de requêtes de prédiction a trois vues.</span><span class="sxs-lookup"><span data-stu-id="4cf87-104">The Prediction Query Builder has three views.</span></span> <span data-ttu-id="4cf87-105">Avec les vues de **conception** et de **requête** , vous pouvez générer et examiner votre requête.</span><span class="sxs-lookup"><span data-stu-id="4cf87-105">With the **Design** and **Query** views, you can build and examine your query.</span></span> <span data-ttu-id="4cf87-106">Vous pouvez ensuite exécuter la requête et afficher les résultats dans l' **affichage des résultats.**</span><span class="sxs-lookup"><span data-stu-id="4cf87-106">You can then run the query and view the results in the **Result** view.</span></span>  
  
 <span data-ttu-id="4cf87-107">Toutes les requêtes de prédictions utilisent DMX, qui est l'abréviation du langage Data Mining Extensions (DMX).</span><span class="sxs-lookup"><span data-stu-id="4cf87-107">All prediction queries use DMX, which is short for the Data Mining Extensions (DMX) language.</span></span> <span data-ttu-id="4cf87-108">DMX a une syntaxe similaire à celle de T-SQL mais est utilisée pour des requêtes sur des objets d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="4cf87-108">DMX has syntax like that of T-SQL but is used for queries against data mining objects.</span></span> <span data-ttu-id="4cf87-109">Bien que la syntaxe DMX ne soit pas compliquée, l’utilisation d’un générateur de requêtes comme celui-ci, ou celle des [compléments d’exploration de données SQL Server pour Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), facilite grandement la sélection des entrées et la création d’expressions. nous vous recommandons donc vivement d’apprendre les principes de base.</span><span class="sxs-lookup"><span data-stu-id="4cf87-109">Although DMX syntax is not complicated, using a query builder like this one, or the one in the [SQL Server Data Mining Add-Ins for Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), makes it much easier to select inputs and build expressions, so we highly recommend that you learn the basics.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="4cf87-110">Création de la requête</span><span class="sxs-lookup"><span data-stu-id="4cf87-110">Creating the Query</span></span>  
 <span data-ttu-id="4cf87-111">La première étape dans la création d'une requête de prédiction consiste à sélectionner un modèle d'exploration de données et une table d'entrée.</span><span class="sxs-lookup"><span data-stu-id="4cf87-111">The first step in creating a prediction query is to select a mining model and input table.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="4cf87-112">Pour sélectionner un modèle et une table d'entrée</span><span class="sxs-lookup"><span data-stu-id="4cf87-112">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="4cf87-113">Sous l’onglet **prédiction de modèle d’exploration** de données du concepteur d’exploration de données, dans la zone modèle d' **exploration** de données, cliquez sur **Sélectionner un modèle**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-113">On the **Mining Model Prediction** tab of Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="4cf87-114">Dans la boîte de dialogue **Sélectionner le modèle d’exploration de données** , parcourez l’arborescence jusqu’à la structure de **publipostage ciblée** , développez la structure, sélectionnez `TM_Decision_Tree` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-114">In the **Select Mining Model** dialog box, navigate through the tree to the **Targeted Mailing** structure, expand the structure, select `TM_Decision_Tree`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="4cf87-115">Dans la zone **Sélectionner une ou plusieurs tables d’entrée** , cliquez sur **Sélectionner la table de cas**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-115">In the **Select Input Table(s)** box, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="4cf87-116">Dans la boîte de dialogue **Sélectionner une table** , dans la liste **source de données** , sélectionnez la vue de source de données [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cf87-116">In the **Select Table** dialog box, in the **Data Source** list, select the data source view [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
5.  <span data-ttu-id="4cf87-117">Dans **nom de la table/vue**, sélectionnez la table **ProspectiveBuyer (DBO)** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-117">In **Table/View Name**, select the **ProspectiveBuyer (dbo)** table, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4cf87-118">La `ProspectiveBuyer` table ressemble le mieux à la table de cas **vTargetMail** .</span><span class="sxs-lookup"><span data-stu-id="4cf87-118">The `ProspectiveBuyer` table most closely resembles the **vTargetMail** case table.</span></span>  
  
## <a name="mapping-the-columns"></a><span data-ttu-id="4cf87-119">Mappage des colonnes</span><span class="sxs-lookup"><span data-stu-id="4cf87-119">Mapping the Columns</span></span>  
 <span data-ttu-id="4cf87-120">Une fois la table d'entrée sélectionnée, le Générateur de requêtes de prédiction crée un mappage par défaut entre le modèle d'exploration de données et la table d'entrée en fonction des noms des colonnes.</span><span class="sxs-lookup"><span data-stu-id="4cf87-120">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="4cf87-121">Au moins une colonne de la structure doit correspondre à une colonne dans les données externes.</span><span class="sxs-lookup"><span data-stu-id="4cf87-121">At least one column from the structure must match a column in the external data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4cf87-122">Les données que vous utilisez pour déterminer la précision des modèles doivent contenir une colonne qui peut être mappée à la colonne prédictible.</span><span class="sxs-lookup"><span data-stu-id="4cf87-122">The data that you use to determine the accuracy of the models must contain a column that can be mapped to the predictable column.</span></span> <span data-ttu-id="4cf87-123">Si une telle colonne n'existe pas, vous pouvez en créer une avec des valeurs vides, mais elle doit avoir le même type de données que la colonne prédictible.</span><span class="sxs-lookup"><span data-stu-id="4cf87-123">If such a column does not exist, you can create one with empty values, but it must have the same data type as the predictable column.</span></span>  
  
#### <a name="to-map-the-inputs-to-the-model"></a><span data-ttu-id="4cf87-124">Pour mapper les entrées au modèle</span><span class="sxs-lookup"><span data-stu-id="4cf87-124">To map the inputs to the model</span></span>  
  
1.  <span data-ttu-id="4cf87-125">Cliquez avec le bouton droit sur les lignes qui connectent la fenêtre du **modèle d’exploration de données** à la fenêtre Sélectionner une **table d’entrée** , puis sélectionnez **modifier les connexions**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-125">Right-click the lines connecting the **Mining Model** window to the **Select Input Table** window, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="4cf87-126">Vous remarquez que toutes les colonnes ne sont pas mappées.</span><span class="sxs-lookup"><span data-stu-id="4cf87-126">Notice that not every column is mapped.</span></span> <span data-ttu-id="4cf87-127">Nous allons ajouter des mappages pour plusieurs **colonnes de table**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-127">We will add mappings for several **Table Columns**.</span></span> <span data-ttu-id="4cf87-128">Nous allons également générer une nouvelle colonne de date de naissance sur la colonne de date actuelle, afin que les colonnes correspondent mieux.</span><span class="sxs-lookup"><span data-stu-id="4cf87-128">We will also generate a new birth date column based on the current date column, so that the columns match better.</span></span>  
  
2.  <span data-ttu-id="4cf87-129">Sous **colonne de table**, cliquez sur la `Bike Buyer` cellule et sélectionnez ProspectiveBuyer. Unknown dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="4cf87-129">Under **Table Column**, click the `Bike Buyer` cell and select ProspectiveBuyer.Unknown from the dropdown.</span></span>  
  
     <span data-ttu-id="4cf87-130">Cette action mappe la colonne prédictible, [Bike Buyer], à une colonne de la table d'entrée.</span><span class="sxs-lookup"><span data-stu-id="4cf87-130">This maps the predictable column, [Bike Buyer], to an input table column.</span></span>  
  
3.  <span data-ttu-id="4cf87-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-131">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="4cf87-132">Dans **Explorateur de solutions**, cliquez avec le bouton droit sur la vue de source de données de **publipostage ciblée** et sélectionnez **Concepteur de vues**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-132">In **Solution Explorer**, right-click the **Targeted Mailing** data source view and select **View Designer**.</span></span>  
  
5.  <span data-ttu-id="4cf87-133">Cliquez avec le bouton droit sur la table ProspectiveBuyer, puis sélectionnez **nouveau calcul nommé**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-133">Right-click the table, ProspectiveBuyer, and select **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="4cf87-134">Dans la boîte de dialogue **créer un calcul nommé** , pour **nom de colonne**, tapez `calcAge` .</span><span class="sxs-lookup"><span data-stu-id="4cf87-134">In the **Create Named Calculation** dialog box, for **Column name**, type `calcAge`.</span></span>  
  
7.  <span data-ttu-id="4cf87-135">Pour **Description**, tapez **calculer l’âge en fonction de la date de naissance**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-135">For **Description**, type **Calculate age based on birthdate**.</span></span>  
  
8.  <span data-ttu-id="4cf87-136">Dans la zone **expression** , tapez, `DATEDIFF(YYYY,[BirthDate],getdate())` puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-136">In the **Expression** box, type `DATEDIFF(YYYY,[BirthDate],getdate())` and then click **OK**.</span></span>  
  
     <span data-ttu-id="4cf87-137">Étant donné que la table d’entrée n’a pas de colonne **Age** qui correspond à celle du modèle, vous pouvez utiliser cette expression pour calculer l’âge du client à partir de la colonne BirthDate de la table d’entrée.</span><span class="sxs-lookup"><span data-stu-id="4cf87-137">Because the input table has no **Age** column corresponding to the one in the model, you can use this expression to calculate customer age from the BirthDate column in the input table.</span></span> <span data-ttu-id="4cf87-138">Dans la mesure où **Age** a été identifié comme la colonne la plus influente pour la prédiction de l’achat de bicyclettes, il doit exister à la fois dans le modèle et dans la table d’entrée.</span><span class="sxs-lookup"><span data-stu-id="4cf87-138">Since **Age** was identified as the most influential column for predicting bike buying, it must exist in both the model and in the input table.</span></span>  
  
9. <span data-ttu-id="4cf87-139">Dans le concepteur d’exploration de données, sélectionnez l’onglet **prédiction de modèle d’exploration** de données et rouvrez la fenêtre **modifier les connexions** .</span><span class="sxs-lookup"><span data-stu-id="4cf87-139">In Data Mining Designer, select the **Mining Model Prediction** tab and re-open the **Modify Connections** window.</span></span>  
  
10. <span data-ttu-id="4cf87-140">Sous **colonne de table**, cliquez sur la cellule **Age** et sélectionnez ProspectiveBuyer. recalcing dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="4cf87-140">Under **Table Column**, click the **Age** cell and select ProspectiveBuyer.calcAge from the dropdown.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="4cf87-141">Si vous ne voyez pas la colonne dans la liste, vous devrez peut-être actualiser la définition de la vue de source de données chargée dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="4cf87-141">If you do not see the column in the list, you might have to refresh the definition of the data source view that is loaded in the designer.</span></span> <span data-ttu-id="4cf87-142">Pour ce faire, dans le menu **fichier** , sélectionnez **enregistrer tout**, puis fermez et rouvrez le projet dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="4cf87-142">To do this, from the **File** menu, select **Save all**, and then close and re-open the project in the designer.</span></span>  
  
11. <span data-ttu-id="4cf87-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-143">Click **OK**.</span></span>  
  
## <a name="designing-the-prediction-query"></a><span data-ttu-id="4cf87-144">Conception de la requête de prédiction</span><span class="sxs-lookup"><span data-stu-id="4cf87-144">Designing the Prediction Query</span></span>  
  
1.  <span data-ttu-id="4cf87-145">Le premier bouton de la barre d’outils de l’onglet **prédiction de modèle d’exploration de données** est le bouton **basculer en mode création/basculer vers la vue résultat/basculer vers la vue requête** .</span><span class="sxs-lookup"><span data-stu-id="4cf87-145">The first button on the toolbar of the **Mining Model Prediction** tab is the **Switch to design view / Switch to result view / Switch to query view** button.</span></span> <span data-ttu-id="4cf87-146">Cliquez sur la flèche vers le bas de ce bouton, puis sélectionnez **conception**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-146">Click the down arrow on this button, and select **Design**.</span></span>  
  
2.  <span data-ttu-id="4cf87-147">Dans la grille de l’onglet **prédiction de modèle d’exploration de données** , cliquez sur la cellule de la première ligne vide de la colonne **source** , puis sélectionnez **fonction de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-147">In the grid on the **Mining Model Prediction** tab, click the cell in the first empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
3.  <span data-ttu-id="4cf87-148">Dans la ligne **fonction de prédiction** , dans la colonne **champ** , sélectionnez `PredictProbability` .</span><span class="sxs-lookup"><span data-stu-id="4cf87-148">In the **Prediction Function** row, in the **Field** column, select `PredictProbability`.</span></span>  
  
     <span data-ttu-id="4cf87-149">Dans la colonne **alias** de la même ligne, tapez **probabilité de résultat**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-149">In the **Alias** column of the same row, type **Probability of result**.</span></span>  
  
4.  <span data-ttu-id="4cf87-150">Dans la fenêtre **modèle d’exploration de données** ci-dessus, sélectionnez et faites glisser [Bike Buyer] dans la cellule **Criteria/argument** .</span><span class="sxs-lookup"><span data-stu-id="4cf87-150">From the **Mining Model** window above, select and drag [Bike Buyer] into the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="4cf87-151">Lorsque vous relâchez, [TM_Decision_Tree]. [Vélo Buyer] s’affiche dans la cellule **critères/argument** .</span><span class="sxs-lookup"><span data-stu-id="4cf87-151">When you let go, [TM_Decision_Tree].[Bike Buyer] appears in the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="4cf87-152">Ceci permet de spécifier la colonne cible pour la fonction `PredictProbability`.</span><span class="sxs-lookup"><span data-stu-id="4cf87-152">This specifies the target column for the `PredictProbability` function.</span></span> <span data-ttu-id="4cf87-153">Pour plus d’informations sur les fonctions, consultez [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="4cf87-153">For more information about functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
5.  <span data-ttu-id="4cf87-154">Cliquez sur la ligne vide suivante dans la colonne **source** , puis sélectionnez **TM_Decision_Tree** modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="4cf87-154">Click the next empty row in the **Source** column, and then select **TM_Decision_Tree** mining model.</span></span>  
  
6.  <span data-ttu-id="4cf87-155">Dans la `TM_Decision_Tree` ligne, dans la colonne **champ** , sélectionnez `Bike Buyer` .</span><span class="sxs-lookup"><span data-stu-id="4cf87-155">In the `TM_Decision_Tree` row, in the **Field** column, select `Bike Buyer`.</span></span>  
  
7.  <span data-ttu-id="4cf87-156">Dans la `TM_Decision_Tree` ligne, dans la colonne **critères/argument** , tapez `=1` .</span><span class="sxs-lookup"><span data-stu-id="4cf87-156">In the `TM_Decision_Tree` row, in the **Criteria/Argument** column, type `=1`.</span></span>  
  
8.  <span data-ttu-id="4cf87-157">Cliquez sur la ligne vide suivante dans la colonne **source** , puis sélectionnez la **table ProspectiveBuyer**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-157">Click the next empty row in the **Source** column, and then select **ProspectiveBuyer table**.</span></span>  
  
9. <span data-ttu-id="4cf87-158">Dans la `ProspectiveBuyer` ligne, dans la colonne **champ** , sélectionnez **ProspectiveBuyerKey**.</span><span class="sxs-lookup"><span data-stu-id="4cf87-158">In the `ProspectiveBuyer` row, in the **Field** column, select **ProspectiveBuyerKey**.</span></span>  
  
     <span data-ttu-id="4cf87-159">Un identificateur unique est ainsi ajouté à la requête de prédiction, lequel vous permet d'identifier les personnes susceptibles ou non d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="4cf87-159">This adds the unique identifier to the prediction query so that you can identify who is and who is not likely to buy a bicycle.</span></span>  
  
10. <span data-ttu-id="4cf87-160">Ajoutez cinq lignes en plus à la grille.</span><span class="sxs-lookup"><span data-stu-id="4cf87-160">Add five more rows to the grid.</span></span> <span data-ttu-id="4cf87-161">Pour chaque ligne, sélectionnez la **table ProspectiveBuyer** comme **source** , puis ajoutez les colonnes suivantes dans les cellules du **champ** :</span><span class="sxs-lookup"><span data-stu-id="4cf87-161">For each row, select **ProspectiveBuyer table** as the **Source** and then add the following columns in the **Field** cells:</span></span>  
  
    -   <span data-ttu-id="4cf87-162">calcAge</span><span class="sxs-lookup"><span data-stu-id="4cf87-162">calcAge</span></span>  
  
    -   <span data-ttu-id="4cf87-163">LastName</span><span class="sxs-lookup"><span data-stu-id="4cf87-163">LastName</span></span>  
  
    -   <span data-ttu-id="4cf87-164">FirstName</span><span class="sxs-lookup"><span data-stu-id="4cf87-164">FirstName</span></span>  
  
    -   <span data-ttu-id="4cf87-165">AddressLine1</span><span class="sxs-lookup"><span data-stu-id="4cf87-165">AddressLine1</span></span>  
  
    -   <span data-ttu-id="4cf87-166">AddressLine2</span><span class="sxs-lookup"><span data-stu-id="4cf87-166">AddressLine2</span></span>  
  
 <span data-ttu-id="4cf87-167">Enfin, exécutez la requête et consultez les résultats.</span><span class="sxs-lookup"><span data-stu-id="4cf87-167">Finally, run the query and browse the results.</span></span>  
  
 <span data-ttu-id="4cf87-168">Le **Générateur de requêtes de prédiction** comprend également les contrôles suivants :</span><span class="sxs-lookup"><span data-stu-id="4cf87-168">The **Prediction Query Builder** also includes these controls:</span></span>  
  
-   <span data-ttu-id="4cf87-169">**Afficher** la case à cocher</span><span class="sxs-lookup"><span data-stu-id="4cf87-169">**Show** check box</span></span>  
  
     <span data-ttu-id="4cf87-170">Vous permet de supprimer des clauses de la requête sans devoir les supprimer du concepteur.</span><span class="sxs-lookup"><span data-stu-id="4cf87-170">Lets you remove clauses from the query without having to delete them from the designer.</span></span> <span data-ttu-id="4cf87-171">Ceci s'avère utile lorsque vous travaillez avec des requêtes complexes et souhaitez conserver la syntaxe sans devoir copier et coller le DMX dans la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="4cf87-171">This can be useful when you are working with complex queries and want to preserve syntax without having to copy and paste DMX into the window.</span></span>  
  
-   <span data-ttu-id="4cf87-172">**Groupe**</span><span class="sxs-lookup"><span data-stu-id="4cf87-172">**Group**</span></span>  
  
     <span data-ttu-id="4cf87-173">Insère une parenthèse ouvrante (gauche) au début de la ligne sélectionnée, ou insère une parenthèse fermante (droite) à la fin de la ligne active.</span><span class="sxs-lookup"><span data-stu-id="4cf87-173">Inserts an opening (left) parentheses at the beginning of the selected line, or inserts a closing (right) parenthesis at the end of the current line.</span></span>  
  
-   <span data-ttu-id="4cf87-174">**ET/OU**</span><span class="sxs-lookup"><span data-stu-id="4cf87-174">**AND/OR**</span></span>  
  
     <span data-ttu-id="4cf87-175">Insère l'opérateur `AND` ou l'opérateur `OR` immédiatement après la fonction ou la colonne active.</span><span class="sxs-lookup"><span data-stu-id="4cf87-175">Inserts the  `AND` operator or the `OR` operator immediately after the current function or column.</span></span>  
  
#### <a name="to-run-the-query-and-view-results"></a><span data-ttu-id="4cf87-176">Pour exécuter la requête et afficher les résultats</span><span class="sxs-lookup"><span data-stu-id="4cf87-176">To run the query and view results</span></span>  
  
1.  <span data-ttu-id="4cf87-177">Sous l’onglet **prédiction de modèle d’exploration de données** , sélectionnez le bouton **résultat** .</span><span class="sxs-lookup"><span data-stu-id="4cf87-177">In the **Mining Model Prediction** tab, select the **Result** button.</span></span>  
  
2.  <span data-ttu-id="4cf87-178">Après l'exécution de la requête et l'affichage des résultats, vous pouvez examiner les résultats.</span><span class="sxs-lookup"><span data-stu-id="4cf87-178">After the query runs and the results are displayed, you can review the results.</span></span>  
  
     <span data-ttu-id="4cf87-179">L’onglet **prédiction de modèle d’exploration** de données affiche les informations de contact des clients potentiels qui sont susceptibles d’être des acheteurs de vélos.</span><span class="sxs-lookup"><span data-stu-id="4cf87-179">The **Mining Model Prediction** tab displays contact information for potential customers who are likely to be bike buyers.</span></span> <span data-ttu-id="4cf87-180">La colonne **probabilité de résultat** indique la probabilité que la prédiction soit correcte.</span><span class="sxs-lookup"><span data-stu-id="4cf87-180">The **Probability of result** column indicates the probability of the prediction being correct.</span></span> <span data-ttu-id="4cf87-181">Ces résultats peuvent vous aider à déterminer les clients potentiels à cibler pour le publipostage.</span><span class="sxs-lookup"><span data-stu-id="4cf87-181">You can use these results to determine which potential customers to target for the mailing.</span></span>  
  
3.  <span data-ttu-id="4cf87-182">À ce stade, vous pouvez enregistrer les résultats.</span><span class="sxs-lookup"><span data-stu-id="4cf87-182">At this point, you can save the results.</span></span> <span data-ttu-id="4cf87-183">Vous avez le choix entre trois options.</span><span class="sxs-lookup"><span data-stu-id="4cf87-183">You have three options:</span></span>  
  
    -   <span data-ttu-id="4cf87-184">Cliquez avec le bouton droit sur une ligne de données dans les résultats, puis sélectionnez **copier** pour enregistrer uniquement cette valeur (et l’en-tête de colonne) dans le presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="4cf87-184">Right-click a row of data in the results, and select **Copy** to save just that value (and the column heading) to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="4cf87-185">Cliquez avec le bouton droit sur une ligne dans les résultats, puis sélectionnez **copier tout** pour copier l’intégralité du jeu de résultats, y compris les en-têtes de colonne, dans le presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="4cf87-185">Right-click any row in the results, and select **Copy All** to copy the entire result set, including column headings, to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="4cf87-186">Cliquez sur **enregistrer le résultat** de la requête pour enregistrer les résultats directement dans une base de données comme suit :</span><span class="sxs-lookup"><span data-stu-id="4cf87-186">Click **Save query result** to save the results directly to a database as follows:</span></span>  
  
        1.  <span data-ttu-id="4cf87-187">Dans la boîte de dialogue Enregistrer le résultat de la **requête d’exploration de données** , sélectionnez une source de données ou définissez une nouvelle source de données.</span><span class="sxs-lookup"><span data-stu-id="4cf87-187">In the **Save Data Mining Query Result** dialog box, select a data source, or define a new data source.</span></span>  
  
        2.  <span data-ttu-id="4cf87-188">Tapez le nom de la table dans laquelle seront enregistrés les résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="4cf87-188">Type a name for the table that will contain the query results.</span></span>  
  
        3.  <span data-ttu-id="4cf87-189">Utilisez l’option **Ajouter à DSV**pour créer la table et l’ajouter à une vue de source de données existante.</span><span class="sxs-lookup"><span data-stu-id="4cf87-189">Use the option, **Add to DSV**, to create the table and add it to an existing data source view.</span></span> <span data-ttu-id="4cf87-190">Cela est utile si vous souhaitez conserver toutes les tables associées pour un modèle, telles que les données d’apprentissage, les données sources de prédiction et les résultats de la requête, dans la même vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="4cf87-190">This is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source view.</span></span>  
  
        4.  <span data-ttu-id="4cf87-191">Utilisez l’option **remplacer si Exists**pour mettre à jour une table existante avec les résultats les plus récents.</span><span class="sxs-lookup"><span data-stu-id="4cf87-191">Use the option, **Overwrite if exists**, to update an existing table with the latest results.</span></span>  
  
             <span data-ttu-id="4cf87-192">Vous devez utiliser l'option permettant de remplacer la table si vous avez ajouté des colonnes à la requête de prédiction, modifié les noms des types de données des colonnes dans la requête de prédiction ou si vous avez exécuté des instructions ALTER sur la table de destination.</span><span class="sxs-lookup"><span data-stu-id="4cf87-192">You must use the option to overwrite the table if you have added any columns to the prediction query, changed the names or data types of any columns in the prediction query, or if you have run any ALTER statements on the destination table.</span></span>  
  
             <span data-ttu-id="4cf87-193">En outre, si plusieurs colonnes portent le même nom (par exemple, l' **expression**de nom de colonne par défaut), vous devez créer un alias pour les colonnes avec des noms dupliqués, ou une erreur est déclenchée lorsque le concepteur tente d’enregistrer les résultats dans SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4cf87-193">Also, if multiple columns have the same name (for example, the default column name **Expression**) you must create an alias for the columns with duplicate names, or an error will be raised when the designer tries to save the results to SQL Server.</span></span> <span data-ttu-id="4cf87-194">En effet, SQL Server n'autorise pas plusieurs colonnes à porter le même nom.</span><span class="sxs-lookup"><span data-stu-id="4cf87-194">The reason is that SQL Server does not allow multiple columns to have the same name.</span></span>  
  
             <span data-ttu-id="4cf87-195">Pour plus d’informations, consultez [boîte de dialogue Enregistrer le résultat de la requête d’exploration de données &#40;vue prévision de modèle d’exploration de données&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span><span class="sxs-lookup"><span data-stu-id="4cf87-195">For more information, see [Save Data Mining Query Result Dialog Box &#40;Mining Model Prediction View&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4cf87-196">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="4cf87-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4cf87-197">Utilisation de l’extraction sur les données de structure &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="4cf87-197">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4cf87-198">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4cf87-198">See Also</span></span>  
 [<span data-ttu-id="4cf87-199">Créer une requête de prédiction à l’aide du Générateur de requêtes de prédiction</span><span class="sxs-lookup"><span data-stu-id="4cf87-199">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
