---
title: Ajouter des paramètres en cascade à un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a22eec3-57a7-478e-b6fc-102a9dbe0591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5419d448b2fa9526224e1bccd80d5c195e2763d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696408"
---
# <a name="add-cascading-parameters-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="6f547-102">Ajouter des paramètres en cascade à un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="6f547-102">Add Cascading Parameters to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6f547-103">Les paramètres en cascade permettent de gérer d'importantes quantités de données de rapport.</span><span class="sxs-lookup"><span data-stu-id="6f547-103">Cascading parameters provide a way of managing large amounts of report data.</span></span> <span data-ttu-id="6f547-104">Vous pouvez définir un ensemble de paramètres associés, de telle sorte que la liste des valeurs d'un paramètre dépende de la valeur choisie dans un autre paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-104">You can define a set of related parameters so that the list of values for one parameter depends on the value chosen in another parameter.</span></span> <span data-ttu-id="6f547-105">Par exemple, le premier paramètre est indépendant et peut présenter une liste de catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="6f547-105">For example, the first parameter is independent and might present a list of product categories.</span></span> <span data-ttu-id="6f547-106">Lorsque l'utilisateur sélectionne une catégorie, le deuxième paramètre dépend de la valeur du premier paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-106">When the user selects a category, the second parameter is dependent on the value of the first parameter.</span></span> <span data-ttu-id="6f547-107">Ses valeurs sont mises à jour avec une liste de sous-catégories au sein de la catégorie choisie.</span><span class="sxs-lookup"><span data-stu-id="6f547-107">Its values are updated with a list of subcategories within the chosen category.</span></span> <span data-ttu-id="6f547-108">Lorsque l'utilisateur affiche le rapport, les valeurs des paramètres de catégorie et de sous-catégorie permettent de filtrer les données du rapport.</span><span class="sxs-lookup"><span data-stu-id="6f547-108">When the user views the report, the values for both the category and subcategory parameters are used to filter report data.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="6f547-109">Pour créer des paramètres en cascade, commencez par définir la requête de dataset et incluez un paramètre de requête pour chaque paramètre en cascade dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="6f547-109">To create cascading parameters, you define the dataset query first and include a query parameter for each cascading parameter that you need.</span></span> <span data-ttu-id="6f547-110">Vous devez également créer un dataset distinct pour chaque paramètre en cascade pour fournir les valeurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="6f547-110">You must also create a separate dataset for each cascading parameter to provide available values.</span></span> <span data-ttu-id="6f547-111">Pour plus d’informations, consultez [Ajouter, modifier ou supprimer les valeurs disponibles d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="6f547-111">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
 <span data-ttu-id="6f547-112">L'ordre des paramètres en cascade est important, car la requête de dataset d'un paramètre situé plus bas dans la liste comporte une référence à chaque paramètre situé plus haut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6f547-112">Order is important for cascading parameters because the dataset query for a parameter later in the list includes a reference to each parameter that is earlier in the list.</span></span> <span data-ttu-id="6f547-113">Au moment de l'exécution, l'ordre des paramètres dans le volet des données de rapport détermine l'ordre d'apparition des requêtes de paramètre dans le rapport et, par conséquent, l'ordre dans lequel un utilisateur choisit chaque valeur de paramètre consécutive.</span><span class="sxs-lookup"><span data-stu-id="6f547-113">At run time, the order of the parameters in the Report Data pane determines the order in which the parameter queries appear in the report, and therefore, the order in which a user chooses each successive parameter value.</span></span>  
  
 <span data-ttu-id="6f547-114">Pour plus d'informations sur la création de paramètres en cascade avec plusieurs valeurs et notamment la fonctionnalité Sélectionner tout, consultez [Comment avoir un paramètre Tout sélectionner en cascade à valeurs multiples](https://go.microsoft.com/fwlink/?LinkId=184757)(en anglais).</span><span class="sxs-lookup"><span data-stu-id="6f547-114">For information about creating cascading parameters with multiple values and including the Select All feature, see [How to have a Select All Multivalue Cascading Parameter](https://go.microsoft.com/fwlink/?LinkId=184757).</span></span>  
  
### <a name="to-create-the-main-dataset-with-a-query-that-includes-multiple-related-parameters"></a><span data-ttu-id="6f547-115">Pour créer le dataset principal avec une requête incluant plusieurs paramètres associés</span><span class="sxs-lookup"><span data-stu-id="6f547-115">To create the main dataset with a query that includes multiple related parameters</span></span>  
  
1.  <span data-ttu-id="6f547-116">Dans le volet Données du rapport, cliquez avec le bouton droit sur une source de données, puis cliquez sur **Ajouter un dataset**.</span><span class="sxs-lookup"><span data-stu-id="6f547-116">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="6f547-117">Dans **Nom**, tapez le nom du dataset.</span><span class="sxs-lookup"><span data-stu-id="6f547-117">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="6f547-118">Dans **Source de données**, sélectionnez le nom de la source de données ou cliquez sur **Nouvelle** pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="6f547-118">In **Data source**, choose the name of the data source or click **New** to create one.</span></span>  
  
4.  <span data-ttu-id="6f547-119">Dans **Type de requête**, choisissez le type de requête de la source de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6f547-119">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="6f547-120">Cette rubrique part du principe que le type de requête **Texte** est utilisé.</span><span class="sxs-lookup"><span data-stu-id="6f547-120">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="6f547-121">Dans **Requête**, tapez la requête à utiliser pour récupérer des données pour ce rapport.</span><span class="sxs-lookup"><span data-stu-id="6f547-121">In **Query**, type the query to use to retrieve data for this report.</span></span> <span data-ttu-id="6f547-122">La requête doit être constituée des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6f547-122">The query must include the following parts:</span></span>  
  
    1.  <span data-ttu-id="6f547-123">La liste des champs de sources de données.</span><span class="sxs-lookup"><span data-stu-id="6f547-123">A list of data source fields.</span></span> <span data-ttu-id="6f547-124">Par exemple, dans une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] , l'instruction SELECT spécifie la liste des noms de colonnes de bases de données à partir d'une table ou d'une vue donnée.</span><span class="sxs-lookup"><span data-stu-id="6f547-124">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, the SELECT statement specifies a list of database column names from a given table or view.</span></span>  
  
    2.  <span data-ttu-id="6f547-125">Un paramètre de requête par paramètre en cascade.</span><span class="sxs-lookup"><span data-stu-id="6f547-125">One query parameter for each cascading parameter.</span></span> <span data-ttu-id="6f547-126">Un paramètre de requête limite les données extraites de la source de données en spécifiant certaines valeurs à inclure dans la requête ou à exclure de la requête.</span><span class="sxs-lookup"><span data-stu-id="6f547-126">A query parameter limits the data retrieved from the data source by specifying certain values to include or exclude from the query.</span></span> <span data-ttu-id="6f547-127">En règle générale, les paramètres de requête se déclenchent dans une clause de restriction dans la requête.</span><span class="sxs-lookup"><span data-stu-id="6f547-127">Typically, query parameters occur in a restriction clause in the query.</span></span> <span data-ttu-id="6f547-128">Par exemple, dans une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT, les paramètres de requête se déclenchent dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="6f547-128">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement, query parameters occur in the WHERE clause.</span></span> <span data-ttu-id="6f547-129">Pour plus d'informations, consultez la rubrique « Filtrage des lignes avec les clauses WHERE et HAVING » dans la documentation [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] de la documentation en ligne [SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="6f547-129">For more information, see "Filtering Rows by Using WHERE and HAVING" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
6.  <span data-ttu-id="6f547-130">Cliquez sur **Exécuter** (**!**).</span><span class="sxs-lookup"><span data-stu-id="6f547-130">Click **Run** (**!**).</span></span> <span data-ttu-id="6f547-131">Une fois que vous avez inclus les paramètres de requête et exécuté la requête, les paramètres de rapport qui correspondent aux paramètres de requête sont automatiquement créés.</span><span class="sxs-lookup"><span data-stu-id="6f547-131">After you include query parameters and then run the query, report parameters that correspond to the query parameters are automatically created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6f547-132">L'ordre des paramètres de requête lors de la première exécution d'une requête détermine leur ordre de création dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="6f547-132">The order of query parameters the first time you run a query determines the order that they are created in the report.</span></span> <span data-ttu-id="6f547-133">Pour modifier l’ordre, consultez [Modifier l’ordre d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6f547-133">To change the order, see [Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="6f547-134">Vous allez ensuite créer un dataset qui fournit les valeurs du paramètre indépendant.</span><span class="sxs-lookup"><span data-stu-id="6f547-134">Next, you will create a dataset that provides the values for the independent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-an-independent-parameter"></a><span data-ttu-id="6f547-135">Pour créer un dataset en vue de fournir les valeurs d'un paramètre indépendant</span><span class="sxs-lookup"><span data-stu-id="6f547-135">To create a dataset to provide values for an independent parameter</span></span>  
  
1.  <span data-ttu-id="6f547-136">Dans le volet Données du rapport, cliquez avec le bouton droit sur une source de données, puis cliquez sur **Ajouter un dataset**.</span><span class="sxs-lookup"><span data-stu-id="6f547-136">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="6f547-137">Dans **Nom**, tapez le nom du dataset.</span><span class="sxs-lookup"><span data-stu-id="6f547-137">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="6f547-138">Dans **Source de données**, vérifiez que le nom correspond au nom de la source de données que vous avez choisie au cours de l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="6f547-138">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="6f547-139">Dans **Type de requête**, choisissez le type de requête de la source de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6f547-139">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="6f547-140">Cette rubrique part du principe que le type de requête **Texte** est utilisé.</span><span class="sxs-lookup"><span data-stu-id="6f547-140">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="6f547-141">Dans **Requête**, tapez la requête à utiliser pour récupérer des valeurs pour ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-141">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="6f547-142">En règle générale, les requêtes des paramètres indépendants ne contiennent pas de paramètres de requête.</span><span class="sxs-lookup"><span data-stu-id="6f547-142">Queries for independent parameters typically do not contain query parameters.</span></span> <span data-ttu-id="6f547-143">Par exemple, pour créer une requête pour un paramètre qui fournit toutes les valeurs de catégorie, vous pouvez utiliser une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="6f547-143">For example, to create a query for a parameter that provides all category values, you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT <column name> FROM <table>  
    ```  
  
     <span data-ttu-id="6f547-144">La commande SELECT DISTINCT supprime les valeurs dupliquées du jeu de résultats, de telle sorte que vous puissiez obtenir chaque valeur unique de la colonne spécifiée dans la table spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6f547-144">The SELECT DISTINCT command removes duplicate values from the result set so that you get each unique value from the specified column in the specified table.</span></span>  
  
     <span data-ttu-id="6f547-145">Cliquez sur **Exécuter** (**!**).</span><span class="sxs-lookup"><span data-stu-id="6f547-145">Click **Run** (**!**).</span></span> <span data-ttu-id="6f547-146">Le jeu de résultats indique les valeurs qui sont disponibles pour ce premier paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-146">The result set shows the values that are available for this first parameter.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="6f547-147">Vous allez ensuite définir les propriétés du premier paramètre en vue d'utiliser ce dataset pour remplir ses valeurs disponibles au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="6f547-147">Next, you will set the properties of the first parameter to use this dataset to populate its available values at run-time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="6f547-148">Pour définir les valeurs disponibles d'un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="6f547-148">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="6f547-149">Dans le dossier Paramètres du volet Données du rapport, cliquez avec le bouton droit sur le premier paramètre, puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="6f547-149">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="6f547-150">Dans **Nom**, vérifiez que le nom du paramètre est correct.</span><span class="sxs-lookup"><span data-stu-id="6f547-150">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="6f547-151">Cliquez sur **Valeurs disponibles**.</span><span class="sxs-lookup"><span data-stu-id="6f547-151">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="6f547-152">Cliquez sur **Obtenir les valeurs à partir d'une requête**.</span><span class="sxs-lookup"><span data-stu-id="6f547-152">Click **Get values from a query**.</span></span> <span data-ttu-id="6f547-153">Trois champs apparaissent.</span><span class="sxs-lookup"><span data-stu-id="6f547-153">Three fields appear.</span></span>  
  
5.  <span data-ttu-id="6f547-154">Dans **Dataset**, dans la liste déroulante, cliquez sur le nom du dataset que vous avez créé lors de la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="6f547-154">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="6f547-155">Dans le champ **Valeur** , cliquez sur le nom du champ qui fournit la valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-155">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="6f547-156">Dans le champ **Étiquette** , cliquez sur le nom du champ qui fournit l'étiquette de paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-156">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="6f547-157">Vous allez ensuite créer un dataset qui fournit les valeurs d'un paramètre dépendant.</span><span class="sxs-lookup"><span data-stu-id="6f547-157">Next, you will create a dataset that provides the values for a dependent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-a-dependent-parameter"></a><span data-ttu-id="6f547-158">Pour créer un dataset en vue de fournir les valeurs d'un paramètre dépendant</span><span class="sxs-lookup"><span data-stu-id="6f547-158">To create a dataset to provide values for a dependent parameter</span></span>  
  
1.  <span data-ttu-id="6f547-159">Dans le volet Données du rapport, cliquez avec le bouton droit sur une source de données, puis cliquez sur **Ajouter un dataset**.</span><span class="sxs-lookup"><span data-stu-id="6f547-159">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="6f547-160">Dans **Nom**, tapez le nom du dataset.</span><span class="sxs-lookup"><span data-stu-id="6f547-160">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="6f547-161">Dans **Source de données**, vérifiez que le nom correspond au nom de la source de données que vous avez choisie au cours de l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="6f547-161">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="6f547-162">Dans **Type de requête**, choisissez le type de requête de la source de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6f547-162">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="6f547-163">Cette rubrique part du principe que le type de requête **Texte** est utilisé.</span><span class="sxs-lookup"><span data-stu-id="6f547-163">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="6f547-164">Dans **Requête**, tapez la requête à utiliser pour récupérer des valeurs pour ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-164">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="6f547-165">En règle générale, les requêtes pour les paramètres dépendants comportent des paramètres de requête pour chaque paramètre dont ce paramètre dépend.</span><span class="sxs-lookup"><span data-stu-id="6f547-165">Queries for dependent parameters typically include query parameters for each parameter that this parameter is dependent on.</span></span> <span data-ttu-id="6f547-166">Par exemple, pour créer une requête pour un paramètre qui fournit toutes les valeurs de sous-catégorie (paramètre dépendant) d’une catégorie (paramètre indépendant), vous pouvez utiliser une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="6f547-166">For example, to create a query for a parameter that provides all subcategory (dependent parameter) values for a category (independent parameter), you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT Subcategory FROM <table>   
    WHERE (Category = @Category)  
    ```  
  
     <span data-ttu-id="6f547-167">Dans la clause WHERE, Category est le nom d’un champ de \<table> et @Category est un paramètre de requête.</span><span class="sxs-lookup"><span data-stu-id="6f547-167">In the WHERE clause, Category is the name of a field from \<table> and @Category is a query parameter.</span></span> <span data-ttu-id="6f547-168">Cette instruction génère la liste des sous-catégories de la catégorie spécifiée dans @Category.</span><span class="sxs-lookup"><span data-stu-id="6f547-168">This statement produces a list of subcategories for the category specified in @Category.</span></span> <span data-ttu-id="6f547-169">Au moment de l'exécution, cette valeur est remplie avec la valeur que l'utilisateur choisit pour le paramètre de rapport qui porte le même nom.</span><span class="sxs-lookup"><span data-stu-id="6f547-169">At run time, this value will be filled in with the value that the user chooses for the report parameter that has the same name.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="6f547-170">Vous allez ensuite définir les propriétés du deuxième paramètre en vue d'utiliser ce dataset pour remplir ses valeurs disponibles au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="6f547-170">Next, you will set the properties of the second parameter to use this dataset to populate its available values at run time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="6f547-171">Pour définir les valeurs disponibles d'un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="6f547-171">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="6f547-172">Dans le dossier Paramètres du volet Données du rapport, cliquez avec le bouton droit sur le premier paramètre, puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="6f547-172">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="6f547-173">Dans **Nom**, vérifiez que le nom du paramètre est correct.</span><span class="sxs-lookup"><span data-stu-id="6f547-173">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="6f547-174">Cliquez sur **Valeurs disponibles**.</span><span class="sxs-lookup"><span data-stu-id="6f547-174">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="6f547-175">Cliquez sur **Obtenir les valeurs à partir d'une requête**.</span><span class="sxs-lookup"><span data-stu-id="6f547-175">Click **Get values from a query**.</span></span>  
  
5.  <span data-ttu-id="6f547-176">Dans **Dataset**, dans la liste déroulante, cliquez sur le nom du dataset que vous avez créé lors de la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="6f547-176">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="6f547-177">Dans le champ **Valeur** , cliquez sur le nom du champ qui fournit la valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-177">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="6f547-178">Dans le champ **Étiquette** , cliquez sur le nom du champ qui fournit l'étiquette de paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-178">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-cascading-parameters"></a><span data-ttu-id="6f547-179">Pour tester les paramètres en cascade</span><span class="sxs-lookup"><span data-stu-id="6f547-179">To test the cascading parameters</span></span>  
  
1.  <span data-ttu-id="6f547-180">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6f547-180">Click **Run**.</span></span>  
  
2.  <span data-ttu-id="6f547-181">Dans la liste déroulante du premier paramètre indépendant, choisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6f547-181">From the drop-down list for the first, independent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="6f547-182">Le processeur de rapports exécute la requête de dataset du paramètre suivant et lui transmet la valeur que vous avez choisie pour le premier paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-182">The report processor runs the dataset query for the next parameter and passes it the value you chose for the first parameter.</span></span> <span data-ttu-id="6f547-183">La liste déroulante du deuxième paramètre est remplie avec les valeurs disponibles qui reposent sur la première valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="6f547-183">The drop-down list for the second parameter is populated with the available values based on the first parameter value.</span></span>  
  
3.  <span data-ttu-id="6f547-184">Dans la liste déroulante du deuxième paramètre dépendant, choisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6f547-184">From the drop-down list for the second, dependent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="6f547-185">Le rapport ne s'exécute pas automatiquement une fois que vous avez choisi le dernier paramètre afin que vous puissiez modifier votre choix.</span><span class="sxs-lookup"><span data-stu-id="6f547-185">The report does not run automatically after you choose the last parameter so that you can change your choice.</span></span>  
  
4.  <span data-ttu-id="6f547-186">Cliquez sur **Afficher le rapport**.</span><span class="sxs-lookup"><span data-stu-id="6f547-186">Click **View Report**.</span></span> <span data-ttu-id="6f547-187">Le rapport actualise l'affichage en fonction des paramètres que vous avez choisis.</span><span class="sxs-lookup"><span data-stu-id="6f547-187">The report updates the display based on the parameters you have chosen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f547-188">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6f547-188">See Also</span></span>  
 <span data-ttu-id="6f547-189">[Ajoutez, modifiez ou supprimez un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6f547-189">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6f547-190">[Paramètres de rapport &#40;Générateur de rapports et de Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="6f547-190">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="6f547-191">[Didacticiel : ajouter un paramètre à votre rapport &#40;Générateur de rapports&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="6f547-191">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="6f547-192">[Didacticiels &#40;Générateur de rapports&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="6f547-192">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="6f547-193">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupe &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="6f547-193">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="6f547-194">Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6f547-194">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
