---
title: Filtrage d’une table imbriquée dans un modèle d’exploration de données (didacticiel sur l’exploration de données intermédiaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0a3ae0e5-897b-4898-a60d-5455eec3d305
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1e6ce2936a3c6763ea41999b2724c0fe8c79301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706919"
---
# <a name="filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="cfaff-102">Filtrage d'une table imbriquée dans un modèle d'exploration de données (Didacticiel sur l'exploration de données intermédiaire)</span><span class="sxs-lookup"><span data-stu-id="cfaff-102">Filtering a Nested Table in a Mining Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="cfaff-103">Après avoir créé et exploré le modèle, vous décidez de vous concentrer sur un sous-ensemble des données des clients.</span><span class="sxs-lookup"><span data-stu-id="cfaff-103">After you have created and explored the model, you decide that you want to focus on a subset of the customer data.</span></span> <span data-ttu-id="cfaff-104">Par exemple, vous pouvez souhaiter analyser uniquement les paniers qui contiennent un article spécifique ou les caractéristiques démographiques des clients qui n'ont rien acheté pendant une certaine période.</span><span class="sxs-lookup"><span data-stu-id="cfaff-104">For example, you might want to analyze only the baskets that contain a specific item, or to analyze the demographics of customers who have not purchased anything in a certain period.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="cfaff-105">permet de filtrer les données utilisées dans un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="cfaff-105">provides the ability to filter the data that is used in a mining model.</span></span> <span data-ttu-id="cfaff-106">Cette fonctionnalité est utile, car vous n’avez pas besoin de configurer une nouvelle vue de source de données pour utiliser des données différentes.</span><span class="sxs-lookup"><span data-stu-id="cfaff-106">This feature is useful because you do not need to set up a new data source view to use different data.</span></span> <span data-ttu-id="cfaff-107">Dans le didacticiel sur l'exploration de données de base, vous avez appris à filtrer des données provenant d'une table plate en appliquant des conditions à la table de cas.</span><span class="sxs-lookup"><span data-stu-id="cfaff-107">In the Basic Data Mining Tutorial, you learned how to filter data from a flat table by applying conditions to the case table.</span></span> <span data-ttu-id="cfaff-108">Au cours de cette tâche, vous allez créer un filtre qui s'applique à une table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="cfaff-108">In this task, you create a filter that applies to a nested table.</span></span>  
  
## <a name="filters-on-nested-vs-case-tables"></a><span data-ttu-id="cfaff-109">Filtres sur des tables imbriquées ou des tables de cas</span><span class="sxs-lookup"><span data-stu-id="cfaff-109">Filters on Nested vs. Case Tables</span></span>  
 <span data-ttu-id="cfaff-110">Si votre vue de source de données contient une table de cas et une table imbriquée, à l'instar de la vue de source de données utilisée dans le modèle Association, vous pouvez effectuer un filtrage sur les valeurs de la table de cas, sur la présence ou l'absence d'une valeur dans la table imbriquée ou sur une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="cfaff-110">If your data source view contains a case table and a nested table, like the data source view used in the Association model, you can filter on values from the case table, the presence or absence of a value in the nested table, or some combination of both.</span></span>  
  
 <span data-ttu-id="cfaff-111">Au cours de cette tâche, vous allez d'abord effectuer une copie du modèle Association, puis ajouter les attributs IncomeGroup et Region au nouveau modèle associé, afin de pouvoir filtrer ces attributs dans la table de cas.</span><span class="sxs-lookup"><span data-stu-id="cfaff-111">In this task, you will first make a copy of the Association model and then add the IncomeGroup and Region attributes to the new related model, so that you can filter on those attributes in the case table.</span></span>  
  
#### <a name="to-create-and-modify-a-copy-of-the-association-model"></a><span data-ttu-id="cfaff-112">Pour créer et modifier une copie du modèle Association</span><span class="sxs-lookup"><span data-stu-id="cfaff-112">To create and modify a copy of the Association model</span></span>  
  
1.  <span data-ttu-id="cfaff-113">Sous l’onglet **modèles d’exploration de données** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , cliquez avec le bouton droit sur le `Association` modèle, puis sélectionnez **nouveau modèle d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-113">In the **Mining Models** tab of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click the `Association` model, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="cfaff-114">Pour le **nom du modèle**, tapez `Association Filtered` .</span><span class="sxs-lookup"><span data-stu-id="cfaff-114">For **Model Name**, type `Association Filtered`.</span></span> <span data-ttu-id="cfaff-115">Pour **nom de l’algorithme**, sélectionnez **règles d’association Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-115">For **Algorithm Name**, select **Microsoft Association Rules**.</span></span> <span data-ttu-id="cfaff-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-116">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="cfaff-117">Dans la colonne du modèle Association filtrée, cliquez sur la ligne IncomeGroup et remplacez la valeur **Ignorer** par **entrée**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-117">In the column for the Association Filtered model, click the IncomeGroup row and change the value from **Ignore** to **Input**.</span></span>  
  
 <span data-ttu-id="cfaff-118">Ensuite, vous allez créer un filtre sur la table de cas dans le nouveau modèle Association.</span><span class="sxs-lookup"><span data-stu-id="cfaff-118">Next, you will create a filter on the case table in the new association model.</span></span> <span data-ttu-id="cfaff-119">Le filtre va passer au modèle uniquement les clients inclus dans la région cible ou possédant le niveau de revenu cible.</span><span class="sxs-lookup"><span data-stu-id="cfaff-119">The filter will pass to the model only the customers in the target region or with the target income level.</span></span> <span data-ttu-id="cfaff-120">Ensuite, vous allez ajouter un deuxième jeu de conditions de filtre pour spécifier que le modèle utilise uniquement les clients dont les paniers ont contenu au moins un article.</span><span class="sxs-lookup"><span data-stu-id="cfaff-120">Then, you will add a second set of filter conditions to specify that the model uses only customers whose shopping baskets contained at least one item.</span></span>  
  
#### <a name="to-add-a-filter-to-a-mining-model"></a><span data-ttu-id="cfaff-121">Pour ajouter un filtre à un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="cfaff-121">To add a filter to a mining model</span></span>  
  
1.  <span data-ttu-id="cfaff-122">Dans l’onglet **modèles d’exploration de données** , cliquez avec le bouton droit sur l’Association de modèle filtrée, puis sélectionnez définir le filtre de **modèle**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-122">In the **Mining Models** tab, right-click the model Association Filtered, and select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="cfaff-123">Dans la boîte de dialogue **Filtre de modèle** , cliquez sur la ligne supérieure dans la grille, dans la zone de texte **Colonne de la structure d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="cfaff-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
3.  <span data-ttu-id="cfaff-124">Dans la zone de texte colonne de la **structure d’exploration de données** , sélectionnez IncomeGroup.</span><span class="sxs-lookup"><span data-stu-id="cfaff-124">In the **Mining Structure Column** text box, select IncomeGroup.</span></span>  
  
     <span data-ttu-id="cfaff-125">L'icône située à gauche de la zone de texte change pour indiquer que l'élément sélectionné est une colonne.</span><span class="sxs-lookup"><span data-stu-id="cfaff-125">The icon at the left side of the text box changes to indicate that the selected item is a column.</span></span>  
  
4.  <span data-ttu-id="cfaff-126">Cliquez sur la zone de texte **opérateur** et sélectionnez l' **=** opérateur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="cfaff-126">Click the **Operator** text box and select the **=** operator from the list.</span></span>  
  
5.  <span data-ttu-id="cfaff-127">Cliquez sur la zone de texte **valeur** , puis tapez `High` dans la zone.</span><span class="sxs-lookup"><span data-stu-id="cfaff-127">Click the **Value** text box, and type `High` in the box.</span></span>  
  
6.  <span data-ttu-id="cfaff-128">Cliquez sur la ligne suivante dans la grille.</span><span class="sxs-lookup"><span data-stu-id="cfaff-128">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="cfaff-129">Cliquez sur la zone de texte **and/or** dans la ligne suivante de la grille, puis sélectionnez **ou**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-129">Click the **AND/OR** text box in the next row of the grid and select **OR**.</span></span>  
  
8.  <span data-ttu-id="cfaff-130">Dans la zone de texte colonne de la **structure d’exploration de données** , sélectionnez IncomeGroup.</span><span class="sxs-lookup"><span data-stu-id="cfaff-130">In the **Mining Structure Column** text box, select IncomeGroup.</span></span> <span data-ttu-id="cfaff-131">Dans la zone de texte **valeur** , tapez `Moderate` .</span><span class="sxs-lookup"><span data-stu-id="cfaff-131">In the **Value** text box, type `Moderate`.</span></span>  
  
     <span data-ttu-id="cfaff-132">La condition de filtre que vous avez créée est automatiquement ajoutée à la zone de texte de l' **expression** et doit apparaître comme suit :</span><span class="sxs-lookup"><span data-stu-id="cfaff-132">The filter condition that you created is automatically added to the **Expression** text box, and should appears as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate'`  
  
9. <span data-ttu-id="cfaff-133">Cliquez sur la ligne suivante dans la grille, en laissant l’opérateur comme valeur par défaut **et**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-133">Click the next row in the grid, leaving the operator as the default, **AND**.</span></span>  
  
10. <span data-ttu-id="cfaff-134">Pour **opérateur**, laissez la valeur par défaut, **contient**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-134">For **Operator**, leave the default value, **Contains**.</span></span> <span data-ttu-id="cfaff-135">Cliquez sur la zone de texte **valeur** .</span><span class="sxs-lookup"><span data-stu-id="cfaff-135">Click the **Value** text box.</span></span>  
  
11. <span data-ttu-id="cfaff-136">Dans la boîte de dialogue **filtre** , dans la première ligne sous colonne de la **structure d’exploration de données**, sélectionnez `Model` .</span><span class="sxs-lookup"><span data-stu-id="cfaff-136">In the **Filter** dialog box, in the first row under **Mining Structure Column**, select `Model`.</span></span>  
  
12. <span data-ttu-id="cfaff-137">Pour l' **opérateur**, SELECT **n’a pas la valeur null**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-137">For **Operator**, select **IS NOT NULL**.</span></span> <span data-ttu-id="cfaff-138">Laissez la zone de texte **valeur** vide.</span><span class="sxs-lookup"><span data-stu-id="cfaff-138">Leave the **Value** text box blank.</span></span> <span data-ttu-id="cfaff-139">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-139">Click **OK**.</span></span>  
  
     <span data-ttu-id="cfaff-140">La condition de filtre dans la zone de texte **expression** de la boîte de dialogue **filtre de modèle** est automatiquement mise à jour pour inclure la nouvelle condition sur la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="cfaff-140">The filter condition in the **Expression** text box of the **Model Filter** dialog box is automatically updated to include the new condition on the nested table.</span></span> <span data-ttu-id="cfaff-141">L'expression complétée se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="cfaff-141">The completed expression is as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate' AND EXISTS SELECT * FROM [vAssocSeqLineItems] WHERE [Model] <> NULL).`  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)] ``  
  
#### <a name="to-enable-drillthrough-and-to-process-the-filtered-model"></a><span data-ttu-id="cfaff-142">Pour activer l'extraction et traiter le modèle filtré</span><span class="sxs-lookup"><span data-stu-id="cfaff-142">To enable drillthrough and to process the filtered model</span></span>  
  
1.  <span data-ttu-id="cfaff-143">Dans l’onglet **modèles d’exploration de données** , cliquez avec le bouton droit sur le `Association Filtered` modèle, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-143">In the **Mining Models** tab, right-click the `Association Filtered` model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="cfaff-144">Remplacez la valeur de la propriété **AllowDrillThrough** par **true**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-144">Change the **AllowDrillThrough** property to **True**.</span></span>  
  
3.  <span data-ttu-id="cfaff-145">Cliquez avec le bouton droit sur le `Association Filtered` modèle d’exploration de données, puis sélectionnez **traiter le modèle**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-145">Right-click the `Association Filtered` mining model, and select **Process Model**.</span></span>  
  
4.  <span data-ttu-id="cfaff-146">Cliquez sur **Oui** dans le message d’erreur pour déployer le nouveau modèle dans la [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="cfaff-146">Click **Yes** in the error message to deploy the new model to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
5.  <span data-ttu-id="cfaff-147">Dans la boîte de dialogue **traiter la structure d’exploration de données** , cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cfaff-147">In the **Process Mining Structure** dialog box, click **Run**.</span></span>  
  
6.  <span data-ttu-id="cfaff-148">Une fois le traitement terminé, cliquez sur **Fermer** pour quitter la boîte de dialogue **État d’avancement** du traitement, puis cliquez de nouveau sur **Fermer** pour quitter la boîte de dialogue traiter la structure d' **exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="cfaff-148">When processing is complete click **Close** to exit the **Process Progress** dialog box, and click **Close** again to exit the **Process Mining Structure** dialog box.</span></span>  
  
 <span data-ttu-id="cfaff-149">Vous pouvez vérifier que le modèle filtré contient moins de cas que le modèle d'origine en utilisant la visionneuse de l'arborescence de contenu générique Microsoft et en recherchant la valeur de NODE_SUPPORT.</span><span class="sxs-lookup"><span data-stu-id="cfaff-149">You can verify by using the Microsoft Generic Content Tree viewer and looking at the value for NODE_SUPPORT that the filtered model contains fewer cases than the original model.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfaff-150">Notes</span><span class="sxs-lookup"><span data-stu-id="cfaff-150">Remarks</span></span>  
 <span data-ttu-id="cfaff-151">Le filtre de table imbriquée que vous venez de créer recherche uniquement la présence d'au moins une ligne dans la table imbriquée ; toutefois, vous pouvez également créer des conditions de filtre qui permettent de rechercher la présence de produits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cfaff-151">The nested table filter that you just created checks only for the presence of at least one row in the nested table; however, you can also create filter conditions that check for the presence of specific products.</span></span>  <span data-ttu-id="cfaff-152">Par exemple, vous pouvez créer le filtre suivant :</span><span class="sxs-lookup"><span data-stu-id="cfaff-152">For example, you could create the following filter:</span></span>  
  
```  
[IncomeGroup] = 'High' AND  
 EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] = 'Water Bottle' )   
```  
  
 <span data-ttu-id="cfaff-153">Cette instruction signifie que vous restreignez les clients figurant dans la table de cas à uniquement ceux qui ont acheté une bouteille d'eau.</span><span class="sxs-lookup"><span data-stu-id="cfaff-153">This statement means that you are restricting the customers from the case table to only those who have purchased a water bottle.</span></span> <span data-ttu-id="cfaff-154">Toutefois, puisque le nombre d'attributs de table imbriquée est potentiellement illimité, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ne fournit pas de liste de valeurs possibles à sélectionner.</span><span class="sxs-lookup"><span data-stu-id="cfaff-154">However, because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="cfaff-155">Vous devez alors taper la valeur exacte.</span><span class="sxs-lookup"><span data-stu-id="cfaff-155">Instead, you must type the exact value.</span></span>  
  
 <span data-ttu-id="cfaff-156">Vous pouvez cliquer sur **modifier la requête** pour modifier manuellement l’expression de filtre.</span><span class="sxs-lookup"><span data-stu-id="cfaff-156">You can click **Edit Query** to manually change the filter expression.</span></span> <span data-ttu-id="cfaff-157">Toutefois, si vous modifiez manuellement quelque partie que ce soit d'une expression de filtre, la grille est alors désactivée et vous devez utiliser l'expression de filtre en mode édition de texte uniquement.</span><span class="sxs-lookup"><span data-stu-id="cfaff-157">However, if you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="cfaff-158">Pour restaurer le mode de modification de grille, vous devez effacer l'expression de filtre et recommencer.</span><span class="sxs-lookup"><span data-stu-id="cfaff-158">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="cfaff-159">Vous ne pouvez pas utiliser l'opérateur LIKE dans un filtre de table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="cfaff-159">You cannot use the LIKE operator in a nested table filter.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="cfaff-160">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="cfaff-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="cfaff-161">Prédiction d’associations &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="cfaff-161">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="cfaff-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cfaff-162">See Also</span></span>  
 <span data-ttu-id="cfaff-163">[Syntaxe de filtre de modèle et exemples &#40;Analysis Services d’exploration de données&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="cfaff-163">[Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="cfaff-164">Filtres pour les modèles d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="cfaff-164">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
