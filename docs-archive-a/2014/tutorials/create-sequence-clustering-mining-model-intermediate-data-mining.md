---
title: Création d’une structure de modèle d’exploration de données Sequence Clustering (Didacticiel intermédiaire sur l’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9339227-6c2e-4c4b-8be2-8c1960bc4a8d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 37d0a1738a758a9d8c4fd6b80310037937a9803f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603742"
---
# <a name="creating-a-sequence-clustering-mining-model-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="89378-102">Création d'une structure de modèle d'exploration de données Sequence Clustering (Didacticiel intermédiaire sur l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="89378-102">Creating a Sequence Clustering Mining Model Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="89378-103">La première étape pour créer un modèle d'exploration de données Sequence Clustering est d'utiliser l'Assistant Exploration de données pour créer une nouvelle structure d'exploration de données et un modèle d'exploration de données selon l'algorithme MSC ([!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering).</span><span class="sxs-lookup"><span data-stu-id="89378-103">The first step in creating a sequence clustering mining model is to use the Data Mining Wizard to create a new mining structure and a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span>  
  
 <span data-ttu-id="89378-104">Vous utiliserez la même vue de source de données que vous avez utilisée pour l'analyse du panier d'achat, mais vous ajouterez une colonne qui contient l'identificateur `sequence`.</span><span class="sxs-lookup"><span data-stu-id="89378-104">You will use the same data source view that you used for the market basket analysis, but you will add a column that contains the `sequence` identifier.</span></span> <span data-ttu-id="89378-105">Dans ce scénario, la séquence signifie l'ordre dans lequel le client a ajouté des éléments au panier.</span><span class="sxs-lookup"><span data-stu-id="89378-105">In this scenario, the sequence means the order in which the customer added items to the shopping basket.</span></span>  
  
 <span data-ttu-id="89378-106">Vous ajouterez également des colonnes utilisées dans l'un des modèles pour regrouper des clients par démographie.</span><span class="sxs-lookup"><span data-stu-id="89378-106">You will also add some columns that are used in one of the models to group customers by demographics.</span></span>  
  
### <a name="to-create-a-sequence-clustering-structure-and-model"></a><span data-ttu-id="89378-107">Pour créer un modèle et une structure Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="89378-107">To create a sequence clustering structure and model</span></span>  
  
1.  <span data-ttu-id="89378-108">Dans Explorateur de solutions dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , cliquez avec le bouton droit sur **structures d’exploration de données** et sélectionnez **nouvelle structure d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="89378-108">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="89378-109">Dans la page **Assistant Exploration de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="89378-109">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="89378-110">Sur la page **Sélectionner la méthode de définition** , vérifiez que **à partir de la base de données relationnelle ou de l’entrepôt de données existant** est sélectionné, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="89378-110">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="89378-111">Dans la page **créer la structure d’exploration de données** , vérifiez que l’option **créer une structure d’exploration de données avec un modèle d’exploration** de données est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="89378-111">On the **Create the Data Mining Structure** page, verify that the option **Create mining structure with a mining model** is selected.</span></span> <span data-ttu-id="89378-112">Ensuite, cliquez sur la liste déroulante de l’option, **quelle technique d’exploration de données voulez-vous utiliser ?**, puis sélectionnez **Microsoft Sequence Clustering**.</span><span class="sxs-lookup"><span data-stu-id="89378-112">Next, click the dropdown list for the option, **Which data mining technique do you want to use?**, and select **Microsoft Sequence Clustering**.</span></span> <span data-ttu-id="89378-113">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="89378-113">Click **Next**.</span></span>  
  
     <span data-ttu-id="89378-114">La page **Sélectionner une vue de source de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="89378-114">The **Select Data Source View** page appears.</span></span> <span data-ttu-id="89378-115">Sous **vues de sources de données disponibles**, sélectionnez `Orders` .</span><span class="sxs-lookup"><span data-stu-id="89378-115">Under **Available data source views**, select `Orders`.</span></span>  
  
     <span data-ttu-id="89378-116">Orders est la même vue de source de données que vous avez utilisée pour le scénario d'analyse de panier.</span><span class="sxs-lookup"><span data-stu-id="89378-116">Orders is the same data source view that you used for the market basket scenario.</span></span> <span data-ttu-id="89378-117">Si vous n’avez pas créé cette vue de source de données, consultez [Ajout d’une vue de source de données avec des tables imbriquées &#40;didacticiel sur l’exploration de données intermédiaire&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="89378-117">If you have not created this data source view, see [Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="89378-118">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="89378-118">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="89378-119">Dans la **page spécifier les types des tables** , activez la case à cocher **cas** en regard de la table **vAssocSeqOrders** , puis activez la case à cocher **imbriquée** en regard de la table **vAssocSeqLineItems** .</span><span class="sxs-lookup"><span data-stu-id="89378-119">On the **Specify Table Types** page, select the **Case** check box next to the **vAssocSeqOrders** table, and select the **Nested** check box next to the **vAssocSeqLineItems** table.</span></span> <span data-ttu-id="89378-120">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="89378-120">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89378-121">Si une erreur se produit lorsque vous activez les cases à cocher **cas** ou **imbriquées** , il se peut que la jointure dans la vue de source de données ne soit pas correcte.</span><span class="sxs-lookup"><span data-stu-id="89378-121">If an error occurs when you select the **Case** or **Nested** check boxes, it may be that the join in the data source view is not correct.</span></span> <span data-ttu-id="89378-122">La table imbriquée, **vAssocSeqLineItems**, doit être connectée à la table de cas, **vAssocSeqOrders,** par une jointure plusieurs-à-un.</span><span class="sxs-lookup"><span data-stu-id="89378-122">The nested table, **vAssocSeqLineItems**, must be connected to the case table, **vAssocSeqOrders,** by a many-to-one join.</span></span> <span data-ttu-id="89378-123">Vous pouvez modifier la relation en cliquant avec le bouton droit sur la ligne de jointure et en inversant la direction de la jointure.</span><span class="sxs-lookup"><span data-stu-id="89378-123">You can edit the relationship by right-clicking on the join line and then reversing the direction of the join.</span></span> <span data-ttu-id="89378-124">Pour plus d’informations, consultez [boîte de dialogue créer ou modifier une relation &#40;Analysis Services-&#41;de données multidimensionnelles ](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="89378-124">For more information, see [Create or Edit Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
7.  <span data-ttu-id="89378-125">Dans la page **spécifier les données d’apprentissage** , choisissez les colonnes à utiliser dans le modèle en activant une case à cocher comme suit :</span><span class="sxs-lookup"><span data-stu-id="89378-125">On the **Specify the Training Data** page, choose the columns for use in the model by selecting a check box as follows:</span></span>  
  
    -   <span data-ttu-id="89378-126">**IncomeGroup** Activez la case à cocher **entrée** .</span><span class="sxs-lookup"><span data-stu-id="89378-126">**IncomeGroup** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="89378-127">Cette colonne contient des informations pertinentes sur les clients que vous pouvez utiliser pour le clustering.</span><span class="sxs-lookup"><span data-stu-id="89378-127">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="89378-128">Vous les utiliserez dans le premier modèle puis les ignorerez dans le deuxième modèle.</span><span class="sxs-lookup"><span data-stu-id="89378-128">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="89378-129">**OrderNumber** Activez la `Key` case à cocher.</span><span class="sxs-lookup"><span data-stu-id="89378-129">**OrderNumber** Select the `Key` check box.</span></span>  
  
         <span data-ttu-id="89378-130">Ce champ sera utilisé comme l'identificateur de la table de cas, ou `Key`.</span><span class="sxs-lookup"><span data-stu-id="89378-130">This field will be used as the identifier for the case table, or `Key`.</span></span> <span data-ttu-id="89378-131">En général, vous ne devez jamais utiliser le champ clé de la table de cas comme entrée, parce que la clé contient des valeurs uniques qui ne sont pas utiles pour le clustering.</span><span class="sxs-lookup"><span data-stu-id="89378-131">In general, you should never use the key field of the case table as an input, because the key contains unique values that are not useful for clustering.</span></span>  
  
    -   <span data-ttu-id="89378-132">**Région** Activez la case à cocher **entrée** .</span><span class="sxs-lookup"><span data-stu-id="89378-132">**Region** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="89378-133">Cette colonne contient des informations pertinentes sur les clients que vous pouvez utiliser pour le clustering.</span><span class="sxs-lookup"><span data-stu-id="89378-133">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="89378-134">Vous les utiliserez dans le premier modèle puis les ignorerez dans le deuxième modèle.</span><span class="sxs-lookup"><span data-stu-id="89378-134">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="89378-135">**LineNumber** Activez les `Key` cases à cocher et **d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="89378-135">**LineNumber** Select the `Key` and **Input** check boxes.</span></span>  
  
         <span data-ttu-id="89378-136">Le champ **LineNumber** sera utilisé comme identificateur pour la table imbriquée, ou `Sequence Key` .</span><span class="sxs-lookup"><span data-stu-id="89378-136">The **LineNumber** field will be used as the identifier for the nested table, or `Sequence Key`.</span></span> <span data-ttu-id="89378-137">La clé pour une table imbriquée doit toujours être utilisée pour l'entrée.</span><span class="sxs-lookup"><span data-stu-id="89378-137">The key for a nested table must always be used for input.</span></span>  
  
    -   <span data-ttu-id="89378-138">**Modèle** Activez les cases à cocher **entrée** et **prédiction** .</span><span class="sxs-lookup"><span data-stu-id="89378-138">**Model** Select the **Input** and **Predictable** check boxes.</span></span>  
  
     <span data-ttu-id="89378-139">Vérifiez que les sélections sont correctes, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="89378-139">Verify that the selections are correct, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="89378-140">Dans la page **spécifier le type de contenu et de données des colonnes** , vérifiez que la grille contient les colonnes, les types de contenu et les types de données indiqués dans le tableau suivant, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="89378-140">On the **Specify Columns' Content and Data Type** page, verify that the grid contains the columns, content types, and data types shown in the following table, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="89378-141">Tables/Colonnes</span><span class="sxs-lookup"><span data-stu-id="89378-141">Tables/Columns</span></span>|<span data-ttu-id="89378-142">Type de contenu</span><span class="sxs-lookup"><span data-stu-id="89378-142">Content Type</span></span>|<span data-ttu-id="89378-143">Type de données</span><span class="sxs-lookup"><span data-stu-id="89378-143">Data Type</span></span>|  
    |---------------------|------------------|---------------|  
    |<span data-ttu-id="89378-144">IncomeGroup</span><span class="sxs-lookup"><span data-stu-id="89378-144">IncomeGroup</span></span>|<span data-ttu-id="89378-145">Discret</span><span class="sxs-lookup"><span data-stu-id="89378-145">Discrete</span></span>|<span data-ttu-id="89378-146">Texte</span><span class="sxs-lookup"><span data-stu-id="89378-146">Text</span></span>|  
    |<span data-ttu-id="89378-147">OrderNumber</span><span class="sxs-lookup"><span data-stu-id="89378-147">OrderNumber</span></span>|<span data-ttu-id="89378-148">Clé</span><span class="sxs-lookup"><span data-stu-id="89378-148">Key</span></span>|<span data-ttu-id="89378-149">Texte</span><span class="sxs-lookup"><span data-stu-id="89378-149">Text</span></span>|  
    |<span data-ttu-id="89378-150">Région</span><span class="sxs-lookup"><span data-stu-id="89378-150">Region</span></span>|<span data-ttu-id="89378-151">Discret</span><span class="sxs-lookup"><span data-stu-id="89378-151">Discrete</span></span>|<span data-ttu-id="89378-152">Texte</span><span class="sxs-lookup"><span data-stu-id="89378-152">Text</span></span>|  
    |<span data-ttu-id="89378-153">vAssocSeqLineItems</span><span class="sxs-lookup"><span data-stu-id="89378-153">vAssocSeqLineItems</span></span>|||  
    |<span data-ttu-id="89378-154">Numéro de ligne</span><span class="sxs-lookup"><span data-stu-id="89378-154">Line Number</span></span>|<span data-ttu-id="89378-155">Séquence clé</span><span class="sxs-lookup"><span data-stu-id="89378-155">Key Sequence</span></span>|<span data-ttu-id="89378-156">Long</span><span class="sxs-lookup"><span data-stu-id="89378-156">Long</span></span>|  
    |<span data-ttu-id="89378-157">Modèle</span><span class="sxs-lookup"><span data-stu-id="89378-157">Model</span></span>|<span data-ttu-id="89378-158">Discret</span><span class="sxs-lookup"><span data-stu-id="89378-158">Discrete</span></span>|<span data-ttu-id="89378-159">Texte</span><span class="sxs-lookup"><span data-stu-id="89378-159">Text</span></span>|  
  
9. <span data-ttu-id="89378-160">Sur la page **créer un jeu de test** , modifiez le **pourcentage de données pour le test** sur 20, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="89378-160">On the **Create Testing Set** page, change the **Percentage of data for testing** to 20, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="89378-161">Dans la page **fin de l’Assistant** , pour **nom**de la structure d’exploration de données, tapez `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="89378-161">On the **Completing the Wizard** page, for the **Mining structure name**, type `Sequence Clustering with Region`.</span></span>  
  
11. <span data-ttu-id="89378-162">Pour le **nom du modèle d’exploration de données**, tapez `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="89378-162">For the **Mining model name**, type `Sequence Clustering with Region`.</span></span>  
  
12. <span data-ttu-id="89378-163">Cochez la case **autoriser l’extraction** , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="89378-163">Check the **Allow drill through** box, and then click **Finish**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="89378-164">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="89378-164">Next Task in Lesson</span></span>  
 [<span data-ttu-id="89378-165">Traitement du modèle Sequence Clustering</span><span class="sxs-lookup"><span data-stu-id="89378-165">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="89378-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89378-166">See Also</span></span>  
 <span data-ttu-id="89378-167">[Concepteur d’exploration de données](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="89378-167">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="89378-168">Algorithme MSC (Microsoft Sequence Clustering)</span><span class="sxs-lookup"><span data-stu-id="89378-168">Microsoft Sequence Clustering Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)  
  
  
