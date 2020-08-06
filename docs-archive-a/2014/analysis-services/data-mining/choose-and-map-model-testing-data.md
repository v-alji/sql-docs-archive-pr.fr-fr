---
title: Choisir et mapper les données de test du modèle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining accuracy charts
- Mining Accuracy Chart [Analysis Services], column mappings
- input column mapping [Analysis Services]
- mapping input columns [Analysis Services]
ms.assetid: be0d9f20-40c3-4dac-81da-281cfe724126
author: minewiskan
ms.author: owend
ms.openlocfilehash: 84f1d01c40070069d610bb028ab003223c5afbcd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604295"
---
# <a name="choose-and-map-model-testing-data"></a><span data-ttu-id="d96c8-102">Choisir et mapper les données de test du modèle</span><span class="sxs-lookup"><span data-stu-id="d96c8-102">Choose and Map Model Testing Data</span></span>
  <span data-ttu-id="d96c8-103">Pour créer un graphique d’analyse de précision dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vous devez choisir les données à utiliser pour tester le modèle et mapper les données au modèle.</span><span class="sxs-lookup"><span data-stu-id="d96c8-103">To create an accuracy chart in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must choose the data that will be used to test the model, and map the data to the model.</span></span>  
  
 <span data-ttu-id="d96c8-104">Par défaut, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilise les données de test du modèle d’exploration de données, sous réserve que vous ayez créé un jeu de données d’exclusion au moment de la génération de la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d96c8-104">By default, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will use the mining model testing data, provided that you created a holdout data set when you built the mining structure.</span></span> <span data-ttu-id="d96c8-105">La création d'un jeu de test d'exclusion est la méthode la plus simple pour tester les modèles basés sur la même structure d'exploration de données, car les noms de colonnes et les types de données correspondront toujours au modèle, et vous pouvez être raisonnablement assuré que la distribution des données est similaire.</span><span class="sxs-lookup"><span data-stu-id="d96c8-105">Creating a holdout test set is the easiest way to test models that are based on the same mining structure, because the column names and data types will always match the model, and you can be reasonably assured that the distribution of the data is similar.</span></span> <span data-ttu-id="d96c8-106">En outre, le concepteur créera automatiquement les relations entre l'entrée et les colonnes du modèle.</span><span class="sxs-lookup"><span data-stu-id="d96c8-106">Also, the designer will automatically create the relationships between the input and model columns.</span></span>  
  
 <span data-ttu-id="d96c8-107">Ou bien, vous pouvez spécifier une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d96c8-107">Alternatively, you can specify an external source of data.</span></span> <span data-ttu-id="d96c8-108">Pour les données externes, il existe certaines exigences supplémentaires :</span><span class="sxs-lookup"><span data-stu-id="d96c8-108">For external data, there are some additional requirements:</span></span>  
  
-   <span data-ttu-id="d96c8-109">Le jeu de données externes doit être défini comme vue de source de données dans une instance d’ [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d96c8-109">The external data set must be defined as a data source view in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="d96c8-110">Le jeu de données externes doit au moins contenir une colonne qui peut être mappée à la colonne prédictible dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d96c8-110">The external data set must at least contain one column that can be mapped to the predictable column in the mining model.</span></span> <span data-ttu-id="d96c8-111">Vous pouvez choisir d'ignorer certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="d96c8-111">You can choose to ignore some columns.</span></span>  
  
-   <span data-ttu-id="d96c8-112">Vous ne pouvez pas ajouter de nouvelles colonnes ou mapper des colonnes dans une vue de source de données différente.</span><span class="sxs-lookup"><span data-stu-id="d96c8-112">You cannot add new columns or map columns in a different data source view.</span></span> <span data-ttu-id="d96c8-113">La vue de source de données que vous sélectionnez doit contenir toutes les colonnes dont vous avez besoin pour la requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="d96c8-113">The data source view that you select must contain all the columns that you need for the prediction query.</span></span>  
  
-   <span data-ttu-id="d96c8-114">Si les noms des colonnes externes correspondent exactement à ceux du modèle, le concepteur les mappera automatiquement.</span><span class="sxs-lookup"><span data-stu-id="d96c8-114">If the external column names exactly match those in the model, the designer will map them for you.</span></span> <span data-ttu-id="d96c8-115">Si les mappages sont erronés, vous pouvez les modifier, ou supprimer et créer de nouveaux mappages pour les colonnes existantes.</span><span class="sxs-lookup"><span data-stu-id="d96c8-115">If the mappings are wrong, you can change them, or delete and create new mappings for existing columns.</span></span>  
  
-   <span data-ttu-id="d96c8-116">Si vous utilisez une source de données externe, vous pouvez appliquer des filtres pour restreindre les données de test à un sous-ensemble approprié de cas.</span><span class="sxs-lookup"><span data-stu-id="d96c8-116">If you use an external data source, you can apply filters to restrict the testing data to a relevant subset of cases.</span></span>  
  
-   <span data-ttu-id="d96c8-117">Même lorsque vous utilisez le jeu de test d'exclusion, tenez compte du fait que les filtres peuvent provoquer des différences entre les données de test associées à une structure d'exploration de données et les cas de test du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d96c8-117">Even when you use the holdout test set, you should be aware that filters can cause differences between the testing data associated with a mining structure and the mining model test cases.</span></span>  
  
 <span data-ttu-id="d96c8-118">Cette rubrique explique comment choisir et mapper les données de test :</span><span class="sxs-lookup"><span data-stu-id="d96c8-118">This topic describes how to choose and map the testing data:</span></span>  
  
 [<span data-ttu-id="d96c8-119">Sélectionner des tables d'entrée pour tester la précision d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="d96c8-119">Select input tables to test the accuracy of a mining model</span></span>](#bkmk_SelectInputs)  
  
 [<span data-ttu-id="d96c8-120">Mapper des colonnes aux colonnes des données de test</span><span class="sxs-lookup"><span data-stu-id="d96c8-120">Map model columns to the columns in the testing data</span></span>](#bkmk_MapColumns)  
  
 [<span data-ttu-id="d96c8-121">Modifier la façon dont les colonnes des données de test sont mappées au modèle</span><span class="sxs-lookup"><span data-stu-id="d96c8-121">Change the way that columns in the testing data are mapped to the model</span></span>](#bkmk_ChangeMappings)  
  
##  <a name="to-select-input-tables-to-test-the-accuracy-of-a-mining-model"></a><a name="bkmk_SelectInputs"></a> <span data-ttu-id="d96c8-122">Pour sélectionner des tables d'entrée pour tester la précision d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="d96c8-122">To select input tables to test the accuracy of a mining model</span></span>  
  
1.  <span data-ttu-id="d96c8-123">Dans le Concepteur d'exploration de données de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-cliquez sur la structure d'exploration de données qui contient les modèles pour lesquels vous souhaitez établir un graphique.</span><span class="sxs-lookup"><span data-stu-id="d96c8-123">In Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="d96c8-124">Sélectionnez l’onglet **Graphique d’analyse de précision de l’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="d96c8-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="d96c8-125">Sous l’onglet **Sélection d’entrée** de la vue **Graphique d’analyse de précision de l’exploration de données** , sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d96c8-125">On the **Input Selection Tab** of the **Mining Accuracy Chart** view, select one of the following options:</span></span>  
  
     <span data-ttu-id="d96c8-126">**Utiliser des scénarios de test de modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="d96c8-126">**Use mining model test cases**</span></span>  
  
     <span data-ttu-id="d96c8-127">**Utiliser des scénarios de test de structure d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="d96c8-127">**Use mining structure test cases**</span></span>  
  
     <span data-ttu-id="d96c8-128">**Spécifier un autre jeu de données**</span><span class="sxs-lookup"><span data-stu-id="d96c8-128">**Specify a different data set**</span></span>  
  
4.  <span data-ttu-id="d96c8-129">Si vous avez sélectionné **Spécifier un autre jeu de données**, cliquez éventuellement sur **Ouvrir l’Éditeur de filtre** pour créer les conditions de filtrage sur le jeu de données d’entrée.</span><span class="sxs-lookup"><span data-stu-id="d96c8-129">If you selected **Specify a different data set**, optionally click **Open Filter Editor** to create filter conditions on the input data set.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="d96c8-130">Cliquez sur l’onglet **Graphique de courbes d’élévation** ou sur l’onglet **Matrice de classification** pour générer automatiquement le graphique en utilisant les données de test spécifiées.</span><span class="sxs-lookup"><span data-stu-id="d96c8-130">Click the **Lift Chart** tab or the **Classification Matrix** tab to automatically build the chart by using the testing data you specified.</span></span>  
  
##  <a name="to-map-model-columns-to-the-columns-in-the-testing-data"></a><a name="bkmk_MapColumns"></a> <span data-ttu-id="d96c8-131">Pour mapper des colonnes aux colonnes des données de test</span><span class="sxs-lookup"><span data-stu-id="d96c8-131">To map model columns to the columns in the testing data</span></span>  
  
1.  <span data-ttu-id="d96c8-132">Pour ouvrir la structure et les modèles dans le Concepteur d'exploration de données, double-cliquez sur la structure d'exploration de données qui contient les modèles pour lesquels vous souhaitez établir un graphique.</span><span class="sxs-lookup"><span data-stu-id="d96c8-132">Double-click the mining structure that contains the models you want to chart, to open the structure and models in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="d96c8-133">Sélectionnez l’onglet **Graphique d’analyse de précision de l’exploration de données** puis l’onglet **Sélection d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="d96c8-133">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="d96c8-134">Dans **Sélection d’entrée** , sous **Sélectionner le jeu de données à utiliser pour le graphique d’analyse de précision**, sélectionnez **Spécifier un autre jeu de données**.</span><span class="sxs-lookup"><span data-stu-id="d96c8-134">In the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="d96c8-135">Cliquez sur le bouton Parcourir **(...)** pour ouvrir une boîte de dialogue et créer la définition du jeu de données externe.</span><span class="sxs-lookup"><span data-stu-id="d96c8-135">Click the browse button **(...)** to open a dialog box and build the definition of the external data set.</span></span>  
  
5.  <span data-ttu-id="d96c8-136">Dans la boîte de dialogue **Sélectionner la structure d’exploration de données** , sélectionnez la structure d’exploration de données qui contient les modèles à utiliser, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d96c8-136">In the **Select Mining Structure** dialog box, select the mining structure that contains the models you want to work with, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="d96c8-137">Dans la table **Sélectionner une ou plusieurs tables d’entrée** de l’onglet **Graphique d’analyse de précision de l’exploration de données** , cliquez sur **Sélectionner la table de cas** pour ouvrir la boîte de dialogue **Sélectionner une table** .</span><span class="sxs-lookup"><span data-stu-id="d96c8-137">On the **Select Input Table(s)** table of the **Mining Accuracy Chart** tab, click **Select Case Table** to open the **Select Table** dialog box.</span></span>  
  
7.  <span data-ttu-id="d96c8-138">Dans la boîte de dialogue **Sélectionner une table** , sélectionnez une source de données dans la liste **Source de données** .</span><span class="sxs-lookup"><span data-stu-id="d96c8-138">In the **Select Table** dialog box, select a data source from the **Data Source** list.</span></span> <span data-ttu-id="d96c8-139">Sélectionnez une table qui contient les données à utiliser dans les requêtes de prédiction pour déterminer la précision des modèles.</span><span class="sxs-lookup"><span data-stu-id="d96c8-139">Choose a table that contains the data that you want to use in the prediction queries to determine the accuracy of the models.</span></span>  
  
8.  <span data-ttu-id="d96c8-140">Dans la zone **Nom de la table/vue** , sélectionnez la table qui contient les données à utiliser pour tester les modèles.</span><span class="sxs-lookup"><span data-stu-id="d96c8-140">In the **Table/View Name** box, select the table that contains the data that you want to use to test the models.</span></span>  
  
9. <span data-ttu-id="d96c8-141">Modifiez les mappages, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="d96c8-141">Edit the mappings, if necessary.</span></span> <span data-ttu-id="d96c8-142">Les colonnes de la structure d’exploration de données sont mappées automatiquement aux colonnes portant le même nom dans la table d’entrée.</span><span class="sxs-lookup"><span data-stu-id="d96c8-142">Columns in the mining structure are automatically mapped to the columns with the same name in the input table.</span></span> <span data-ttu-id="d96c8-143">Pour créer des mappages manuellement, cliquez sur une colonne dans la table **Sélectionner une ou plusieurs tables d’entrée** et faites-la glisser vers la colonne correspondante dans la table **Structure d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="d96c8-143">To manually create mappings, click a column in the **Select Input Table(s)** table and drag it onto the corresponding column in the **Mining Structure** table.</span></span> <span data-ttu-id="d96c8-144">Pour supprimer un mappage, cliquez sur la ligne qui lie la colonne de la table **Structure d’exploration de données** à la colonne associée de la table **Sélectionner une ou plusieurs tables d’entrée** et appuyez sur Suppr.</span><span class="sxs-lookup"><span data-stu-id="d96c8-144">To delete a mapping, click the line that links the column in the **Mining Structure** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="to-modify-the-way-input-data-is-mapped-to-the-model"></a><a name="bkmk_ChangeMappings"></a><span data-ttu-id="d96c8-145">Pour modifier la façon dont les données d’entrée sont mappées au modèle</span><span class="sxs-lookup"><span data-stu-id="d96c8-145">To modify the way input data is mapped to the model</span></span>  
  
1.  <span data-ttu-id="d96c8-146">Dans le Concepteur d’exploration de données, double-cliquez sur la structure qui contient les modèles pour lesquels vous souhaitez établir un graphique.</span><span class="sxs-lookup"><span data-stu-id="d96c8-146">In Data Mining Designer, double-click the structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="d96c8-147">Sélectionnez l’onglet **Graphique d’analyse de précision de l’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="d96c8-147">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="d96c8-148">Cliquez sur l’onglet **Sélection d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="d96c8-148">Click the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="d96c8-149">Dans **Sélectionner le jeu de données à utiliser pour le graphique d’exactitude**, sélectionnez l’option **spécifier un autre jeu de données**.</span><span class="sxs-lookup"><span data-stu-id="d96c8-149">In **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
5.  <span data-ttu-id="d96c8-150">Cliquez sur le bouton Parcourir **(...)** pour ouvrir une boîte de dialogue et créer la définition de la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d96c8-150">Click the browse button **(...)** to open a dialog box and build the definition of the external data source.</span></span>  
  
6.  <span data-ttu-id="d96c8-151">Dans la boîte de dialogue **Spécifier le mappage des colonnes** , cliquez sur **Sélectionner la table de cas**.</span><span class="sxs-lookup"><span data-stu-id="d96c8-151">In the **Specify Column Mapping** dialog box, click **Select Case Table**.</span></span>  
  
7.  <span data-ttu-id="d96c8-152">Dans la boîte de dialogue Sélectionner une table, sélectionnez une vue de source de données dans la liste, puis sélectionnez la table qui contient les données de cas.</span><span class="sxs-lookup"><span data-stu-id="d96c8-152">In the Select Table dialog box, Select a data source view from the list, and select the table that contains the case data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="d96c8-153">Si les tables dont vous avez besoin ne sont pas disponibles, fermez la boîte de dialogue et créez une nouvelle vue de source de données qui contient la table.</span><span class="sxs-lookup"><span data-stu-id="d96c8-153">If the tables you need are not available, close the dialog box and create a new data source view that contains the table.</span></span> <span data-ttu-id="d96c8-154">Pour plus d’informations sur la création d’une vue de source de données, consultez [Définition d’une vue de source de données &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d96c8-154">For information about how to create a data source view, see [Defining a Data Source View &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span></span>  
  
9. <span data-ttu-id="d96c8-155">Si le modèle d’exploration de données contient une table imbriquée, cliquez sur **Sélectionner la table imbriquée**, puis sélectionnez la table imbriquée dans la liste de tables de la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="d96c8-155">If the mining model contains a nested table, click **Select Nested Table**, and select the nested table from the list of tables in the data source view.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="d96c8-156">Sélectionnez la ligne de jointure du mappage à modifier, puis sélectionnez **Modifier les connexions**.</span><span class="sxs-lookup"><span data-stu-id="d96c8-156">Select the join line of the mapping you want to modify, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="d96c8-157">La boîte de dialogue **Modifier le mappage** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="d96c8-157">The **Modify Mapping** dialog box opens.</span></span> <span data-ttu-id="d96c8-158">Dans la table de cette boîte de dialogue, **Colonne de la structure d’exploration de données** contient la liste des colonnes de la structure d’exploration de données sélectionnée, et **Colonne de table** contient la liste des colonnes des tables d’entrée qui sont associées aux colonnes de la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d96c8-158">In the table in this dialog box, **Mining Structure Column** lists each column that the selected mining structure contains, and **Table Column** lists the columns from input tables that are mapped to columns in the mining structure.</span></span>  
  
11. <span data-ttu-id="d96c8-159">Sous **Colonne de table**, sélectionnez la ligne qui correspond à la ligne sous **Colonne de la structure d’exploration de données** pour laquelle vous souhaitez modifier une relation.</span><span class="sxs-lookup"><span data-stu-id="d96c8-159">Under **Table Column**, select the row that corresponds to the row under **Mining Structure Column** for which you want to modify a relationship.</span></span> <span data-ttu-id="d96c8-160">Sélectionnez une nouvelle colonne dans la liste ou l'entrée vide de la liste pour supprimer la colonne.</span><span class="sxs-lookup"><span data-stu-id="d96c8-160">Select a new column from the list, or select the blank entry from the list to delete the column.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="d96c8-161">Les nouveaux mappages de colonnes sont affichés dans la boîte de dialogue **Spécifier le mappage des colonnes** .</span><span class="sxs-lookup"><span data-stu-id="d96c8-161">The new column mappings are displayed in the **Specify Column Mapping** dialog box.</span></span> <span data-ttu-id="d96c8-162">Pour supprimer un mappage, sélectionnez la ligne située entre les colonnes, puis appuyez sur la touche Suppr.</span><span class="sxs-lookup"><span data-stu-id="d96c8-162">You can remove a mapping by selecting the line between the columns and pressing the DELETE key.</span></span> <span data-ttu-id="d96c8-163">Pour créer une connexion, sélectionnez une colonne dans la table **Structure d’exploration de données** , puis faites-la glisser vers la colonne correspondante de la table **Sélectionner une ou plusieurs tables d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="d96c8-163">You can create a new connection by selecting a column in the **Mining Structure** table and dragging it to the corresponding column in the **SelectInput Table(s)** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96c8-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d96c8-164">See Also</span></span>  
 [<span data-ttu-id="d96c8-165">Tâches de test et validation et procédures &#40;exploration des données&#41;</span><span class="sxs-lookup"><span data-stu-id="d96c8-165">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
  
