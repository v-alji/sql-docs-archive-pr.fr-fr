---
title: Créer un graphique de courbes d’élévation, un graphique des bénéfices ou une matrice de classification | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], mining structures
ms.assetid: aa3d052f-58a9-4417-8e7a-5e6feb562af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 932138b37b36269bed86df42786bd5d684f75ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696332"
---
# <a name="create-a-lift-chart-profit-chart-or-classification-matrix"></a><span data-ttu-id="79101-102">Créer un graphique de courbes d'élévation, un graphique des bénéfices ou une matrice de classification</span><span class="sxs-lookup"><span data-stu-id="79101-102">Create a Lift Chart, Profit Chart, or Classification Matrix</span></span>
  <span data-ttu-id="79101-103">Vous pouvez créer un graphique d'analyse de précision pour un modèle d'exploration de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en cinq étapes de base :</span><span class="sxs-lookup"><span data-stu-id="79101-103">You can create an accuracy chart for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data mining model in five basic steps:</span></span>  
  
-   <span data-ttu-id="79101-104">Sélectionnez la structure d'exploration de données contenant les modèles d'exploration de données à comparer.</span><span class="sxs-lookup"><span data-stu-id="79101-104">Select the mining structure that contains the mining models that you want to compare.</span></span>  
  
-   <span data-ttu-id="79101-105">Sélectionnez les modèles d'exploration de données à ajouter au graphique.</span><span class="sxs-lookup"><span data-stu-id="79101-105">Select the mining models to add to the chart.</span></span>  
  
-   <span data-ttu-id="79101-106">Spécifiez une source de données de test à utiliser pour générer le graphique.</span><span class="sxs-lookup"><span data-stu-id="79101-106">Specify a source of testing data to use in generating the chart.</span></span>  
  
-   <span data-ttu-id="79101-107">Choisissez le type de graphique.</span><span class="sxs-lookup"><span data-stu-id="79101-107">Choose the chart type.</span></span>  
  
-   <span data-ttu-id="79101-108">Configurez les options du graphique.</span><span class="sxs-lookup"><span data-stu-id="79101-108">Configure the chart options.</span></span>  
  
 <span data-ttu-id="79101-109">Ces étapes de base sont les mêmes pour le graphique de courbes d'élévation, le graphique des bénéfices et la matrice de classification.</span><span class="sxs-lookup"><span data-stu-id="79101-109">These basic steps are the same for the lift chart, profit chart, and classification matrix.</span></span> <span data-ttu-id="79101-110">Les procédures suivantes présentent les étapes à suivre pour configurer les options des graphiques de base pour ces types de graphiques.</span><span class="sxs-lookup"><span data-stu-id="79101-110">The following procedures outline the steps to configure the basic chart options for these chart types.</span></span> <span data-ttu-id="79101-111">Pour plus d’informations sur la création d’un rapport de validation croisée, consultez [Mesures dans le rapport de validation croisée](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="79101-111">For information about how to create a cross-validation report, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
### <a name="open-the-mining-structure-in-the-accuracy-chart-designer"></a><span data-ttu-id="79101-112">Ouvrir la structure d'exploration de données dans le concepteur graphique d'analyse de précision</span><span class="sxs-lookup"><span data-stu-id="79101-112">Open the mining structure in the Accuracy Chart Designer</span></span>  
  
1.  <span data-ttu-id="79101-113">Ouvrez le Concepteur d'exploration de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79101-113">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="79101-114">Dans l'Explorateur de solutions, double-cliquez sur la structure qui contient le ou les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="79101-114">In Solution Explorer, double-click the structure that contains the mining model or models.</span></span>  
  
3.  <span data-ttu-id="79101-115">Cliquez sur l'onglet **Graphique d'analyse de précision de l'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="79101-115">Click the **Mining Accuracy Chart** tab.</span></span>  
  
### <a name="select-mining-models-for-inclusion-in-the-chart"></a><span data-ttu-id="79101-116">Sélectionner des modèles d'exploration de données à inclure dans le graphique</span><span class="sxs-lookup"><span data-stu-id="79101-116">Select mining models for inclusion in the chart</span></span>  
  
1.  <span data-ttu-id="79101-117">Sous l'onglet **Graphique d'analyse de précision de l'exploration de données** du Concepteur d'exploration de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur l'onglet **Sélection d'entrée** .</span><span class="sxs-lookup"><span data-stu-id="79101-117">On the **Mining Accuracy Chart** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Input Selection** tab.</span></span>  
  
     <span data-ttu-id="79101-118">La liste affiche tous les modèles dans la structure actuelle qui ont le même attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="79101-118">The list displays all models in the current structure that have the same predictable attribute.</span></span>  
  
2.  <span data-ttu-id="79101-119">Activez la case à cocher **Afficher** pour chaque modèle à inclure dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="79101-119">Select the **Show box** for each model that you want to include in the chart.</span></span>  
  
3.  <span data-ttu-id="79101-120">Cliquez sur la zone de texte **Nom de la colonne prédictible** et sélectionnez le nom d'une colonne prédictible dans la liste.</span><span class="sxs-lookup"><span data-stu-id="79101-120">Click the **Predictable Column Name** text box, and select the name of a predictable column from the list.</span></span> <span data-ttu-id="79101-121">Tous les modèles que vous incluez dans un graphique doivent avoir la même colonne prédictible.</span><span class="sxs-lookup"><span data-stu-id="79101-121">All models that you put in one chart must have the same predictable column.</span></span>  
  
4.  <span data-ttu-id="79101-122">Si vous comparez deux modèles et que les colonnes prédictibles ont des valeurs différentes ou des types de données différents, désactivez la case à cocher **Synchroniser les colonnes de prédiction et les valeurs** pour forcer une comparaison.</span><span class="sxs-lookup"><span data-stu-id="79101-122">If you compare two models and the predictable columns have different values or different data types, clear the **Synchonize prediction columns and values** box to force a comparison.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="79101-123">Si la case à cocher **Synchroniser les colonnes de prédiction et les valeurs** est activée, Analysis Services analyse les données dans les colonnes prédictibles du modèle et les données de test, puis tente de trouver la meilleure correspondance.</span><span class="sxs-lookup"><span data-stu-id="79101-123">If the **Synchonize prediction columns and values** box is selected, Analysis Services analyzes the data in the predictable columns of the model and the test data, and attempts to find the best match.</span></span> <span data-ttu-id="79101-124">Par conséquent, ne désactivez pas la case à cocher sauf en cas d'absolue nécessité pour forcer une comparaison des colonnes.</span><span class="sxs-lookup"><span data-stu-id="79101-124">Therefore, do not clear the box unless absolutely necessary to force a comparison of the columns.</span></span>  
  
5.  <span data-ttu-id="79101-125">Cliquez sur la zone de texte **Prédire la valeur** et sélectionnez une valeur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="79101-125">Click the **Predict Value** text box, and select a value from the list.</span></span> <span data-ttu-id="79101-126">Si la colonne prédictible est un type de données continu, vous devez taper une valeur dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="79101-126">If the predictable column is a continuous data type, you must type a value in the text box.</span></span>  
  
     <span data-ttu-id="79101-127">Pour plus d’informations, consultez [Choisir la colonne à utiliser pour tester un modèle d’exploration de données](choose-the-column-to-use-for-testing-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="79101-127">For more information, see [Choose the Column to Use for Testing a Mining Model](choose-the-column-to-use-for-testing-a-mining-model.md).</span></span>  
  
### <a name="select-testing-data"></a><span data-ttu-id="79101-128">Sélectionner des données de test</span><span class="sxs-lookup"><span data-stu-id="79101-128">Select testing data</span></span>  
  
1.  <span data-ttu-id="79101-129">Sous l'onglet **Sélection d'entrée** de l'onglet **Graphique d'analyse de précision de l'exploration de données** , spécifiez la source des données à utiliser pour générer le graphique en sélectionnant l'une des options dans le groupe, **Sélectionner le jeu de données à utiliser pour le graphique d'analyse de précision**.</span><span class="sxs-lookup"><span data-stu-id="79101-129">On the **Input Selection** tab of the **Mining Accuracy Chart** tab, specify the source of the data that you will use to generate the chart by selecting one of the options in the group, **Select data set to be used for accuracy chart**.</span></span>  
  
    -   <span data-ttu-id="79101-130">Sélectionnez l'option **Utiliser des scénarios de test de modèle d'exploration de données**, si vous souhaitez utiliser le sous-ensemble de scénarios défini par l'intersection des scénarios de test de la structure d'exploration de données et les filtres qui ont pu être appliqués lors de la création du modèle.</span><span class="sxs-lookup"><span data-stu-id="79101-130">Select the option, **Use Mining Model test cases**, if you want to use the subset of cases that is defined by the intersection of the mining structure test cases and any filters that may have been applied during model creation.</span></span>  
  
    -   <span data-ttu-id="79101-131">Sélectionnez l'option **Utiliser des scénarios de test de structure d'exploration de données**, pour utiliser le jeu complet de scénarios de test définis dans le jeu de données d'exclusion des structures d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="79101-131">Select the option, **Use mining structure test cases**, to use the full set of testing cases that were defined as part of the mining structures holdout data set.</span></span>  
  
    -   <span data-ttu-id="79101-132">Sélectionnez l’option **Spécifier un autre jeu de données**si vous souhaitez utiliser des données externes.</span><span class="sxs-lookup"><span data-stu-id="79101-132">Select the option, **Specify a different data set**, if you want to use external data.</span></span>  <span data-ttu-id="79101-133">Le jeu de données doit être disponible comme vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="79101-133">The data set must be available as a data source view.</span></span>   <span data-ttu-id="79101-134">Cliquez sur le bouton Parcourir (**...**) pour choisir les tables de données à utiliser pour le graphique d’exactitude.</span><span class="sxs-lookup"><span data-stu-id="79101-134">Click the browse (**...**) button to choose the data tables to use for the accuracy chart.</span></span> <span data-ttu-id="79101-135">Pour plus d’informations, consultez [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="79101-135">For more information, see [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span></span>  
  
         <span data-ttu-id="79101-136">Si vous utilisez un jeu de données externes, vous pouvez éventuellement filtrer le jeu de données d'entrée.</span><span class="sxs-lookup"><span data-stu-id="79101-136">If you are using an external data set, you can optionally filter the input data set.</span></span> <span data-ttu-id="79101-137">Pour plus d’informations, consultez [Appliquer des filtres aux données de test du modèle](apply-filters-to-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="79101-137">For more information, see [Apply Filters to Model Testing Data](apply-filters-to-model-testing-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79101-138">Vous ne pouvez pas créer de filtre sur les cas de test de modèle ou les cas de test de la structure d’exploration de données sous l’onglet **sélection d’entrée** . Pour créer un filtre sur le modèle d’exploration de données, modifiez la propriété Filter du modèle.</span><span class="sxs-lookup"><span data-stu-id="79101-138">You cannot create a filter on the model test cases or the mining structure test cases on the **Input Selection** tab. To create a filter on the mining model, modify the Filter property of the model.</span></span> <span data-ttu-id="79101-139">Pour plus d’informations, consultez [Appliquer un filtre à un modèle d’exploration de données](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="79101-139">For more information, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
### <a name="configure-chart-settings-and-generate-the-chart"></a><span data-ttu-id="79101-140">Configurer les paramètres du graphique et générer le graphique</span><span class="sxs-lookup"><span data-stu-id="79101-140">Configure chart settings and generate the chart</span></span>  
  
1.  <span data-ttu-id="79101-141">Sous l'onglet **Graphique d'analyse de précision de l'exploration de données** , cliquez sur l'onglet correspondant au graphique à créer.</span><span class="sxs-lookup"><span data-stu-id="79101-141">In the **Mining Accuracy Chart** tab, click the tab for the chart you want to create.</span></span>  
  
2.  <span data-ttu-id="79101-142">Pour un **graphique de courbes d’élévation**, cliquez sur l’onglet **graphique de courbes d’élévation** . Le graphique est automatiquement généré en fonction du modèle, des attributs prévisibles et des données d’entrée que vous venez de sélectionner.</span><span class="sxs-lookup"><span data-stu-id="79101-142">For a **lift chart**, click the **Lift Chart** tab. The chart is automatically generated based on the model, predictable attributes, and input data that you just selected.</span></span>  
  
3.  <span data-ttu-id="79101-143">Pour une **matrice de classification**, cliquez sur l’onglet **matrice de classification** . Aucun autre paramètre n’est nécessaire. le graphique est automatiquement généré en fonction des données d’entrée et du modèle que vous avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="79101-143">For a **classification matrix**, click the **Classification Matrix** tab. No further settings are needed; the chart is automatically generated based on the input data and model that you selected.</span></span>  
  
4.  <span data-ttu-id="79101-144">Pour un **graphique des bénéfices**, cliquez d’abord sur l’onglet **graphique de courbes d’élévation** . Ensuite, dans la liste déroulante **type de graphique** , sélectionnez **graphique des bénéfices**.</span><span class="sxs-lookup"><span data-stu-id="79101-144">For a **profit chart**, first click the **Lift Chart** tab. Then, from the **Chart type** drop-down list, select **Profit chart**.</span></span>  
  
     <span data-ttu-id="79101-145">Entrez les paramètres suivants dans la boîte de dialogue **Paramètres du graphique des bénéfices** .</span><span class="sxs-lookup"><span data-stu-id="79101-145">Enter the following settings in the **Profit Chart Settings** dialog box.</span></span>  
  
     <span data-ttu-id="79101-146">**Habitants**</span><span class="sxs-lookup"><span data-stu-id="79101-146">**Population**</span></span>  
     <span data-ttu-id="79101-147">Nombre de cas du jeu de données que vous voulez utiliser lors de la création du graphique de courbes d'élévation.</span><span class="sxs-lookup"><span data-stu-id="79101-147">The number of cases from the data set that you want to use when creating the lift chart.</span></span>  
  
     <span data-ttu-id="79101-148">Le modèle choisit toujours les cas par ordre décroissant de probabilité ; en d'autres termes, si vous évaluez des clients potentiels et que vous choisissez un nombre qui représente uniquement la moitié des enregistrements de votre base de données de clients, le modèle mesurera la précision sur le sous-ensemble des cas les mieux adaptés à votre modèle.</span><span class="sxs-lookup"><span data-stu-id="79101-148">The model always chooses the cases in order of decreasing probability; that is, if you are assessing potential customers and you choose a number that represents only half the records in your customer database, the model will measure accuracy on the subset of cases that best fit your model.</span></span>  
  
     <span data-ttu-id="79101-149">En effet, lorsque vous utilisez le modèle pour générer un publipostage ou créer une campagne, vous utiliserez la probabilité de prédiction associée à chaque cas pour cibler uniquement les clients qui ont la probabilité la plus élevée de faire une réponse positive.</span><span class="sxs-lookup"><span data-stu-id="79101-149">This is because when you use the model to generate a mailing or create a campaign, you will use the prediction probability associated with each case to target only the customers who have the highest probability of making a positive response.</span></span>  
  
     <span data-ttu-id="79101-150">**Coût fixe**</span><span class="sxs-lookup"><span data-stu-id="79101-150">**Fixed Cost**</span></span>  
     <span data-ttu-id="79101-151">Coût fixe associé au problème professionnel.</span><span class="sxs-lookup"><span data-stu-id="79101-151">The fixed cost that is associated with the business problem.</span></span>  
  
     <span data-ttu-id="79101-152">S'il s'agit d'une solution de publipostage ciblé, le coût fixe peut représenter des frais de configuration de l'imprimante qui couvrent le coût initial de préparation du publipostage promotionnel.</span><span class="sxs-lookup"><span data-stu-id="79101-152">If this were for a targeted mailing solution, the fixed cost might represent a printer setup fee that covers the initial cost of preparing the promotional mailing.</span></span>  
  
     <span data-ttu-id="79101-153">Ce coût s'applique une fois à l'ensemble de la population cible.</span><span class="sxs-lookup"><span data-stu-id="79101-153">This cost applies one time to the entire target population.</span></span>  
  
     <span data-ttu-id="79101-154">**Coût individuel**</span><span class="sxs-lookup"><span data-stu-id="79101-154">**Individual Cost**</span></span>  
     <span data-ttu-id="79101-155">Coûts s'ajoutant au coût fixe, qui peuvent être associés à chaque client contacté.</span><span class="sxs-lookup"><span data-stu-id="79101-155">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="79101-156">Par exemple, vous pouvez entrer le coût d'affranchissement pour un publipostage promotionnel ou le coût des appels téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="79101-156">For example, you might enter the postage cost for a promotional mailing or the cost of making telephone calls.</span></span>  
  
     <span data-ttu-id="79101-157">Ce coût doit être le même pour l'ensemble de la population cible.</span><span class="sxs-lookup"><span data-stu-id="79101-157">This cost must be the same for the entire target population.</span></span> <span data-ttu-id="79101-158">Chaque valeur est multipliée par le nombre de cas ciblés.</span><span class="sxs-lookup"><span data-stu-id="79101-158">Each value is multiplied by the number of cases that are targeted.</span></span>  
  
     <span data-ttu-id="79101-159">**Revenu par personne**</span><span class="sxs-lookup"><span data-stu-id="79101-159">**Revenue Per Individual**</span></span>  
     <span data-ttu-id="79101-160">Revenu associé à chaque vente réussie.</span><span class="sxs-lookup"><span data-stu-id="79101-160">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79101-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79101-161">See Also</span></span>  
 <span data-ttu-id="79101-162">[Graphique de courbes d’élévation &#40;Analysis Services d’exploration de données&#41;](lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="79101-162">[Lift Chart &#40;Analysis Services - Data Mining&#41;](lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="79101-163">Matrice de classification &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="79101-163">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](classification-matrix-analysis-services-data-mining.md)  
  
  
