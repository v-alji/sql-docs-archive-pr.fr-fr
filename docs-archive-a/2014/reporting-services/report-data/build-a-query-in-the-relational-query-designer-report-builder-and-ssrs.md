---
title: Générer une requête dans le concepteur de requêtes relationnelles (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 28b25861-f3b4-4c3e-a9b0-03d6e4cfea26
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 555d72c4d3bca8677d04fdc4160639f004d6bbe9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707192"
---
# <a name="build-a-query-in-the-relational-query-designer-report-builder-and-ssrs"></a><span data-ttu-id="90be1-102">Générer une requête dans le concepteur de requêtes relationnelles (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="90be1-102">Build a Query in the Relational Query Designer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="90be1-103">Un concepteur de requêtes vous aide à spécifier les données à récupérer à partir d'une source de données externe pour un dataset de rapport.</span><span class="sxs-lookup"><span data-stu-id="90be1-103">A query designer helps you specify which data to retrieve from an external data source for a report dataset.</span></span> <span data-ttu-id="90be1-104">Vous utilisez un concepteur de requêtes lorsque vous générez une requête dans un Assistant ou créez une requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="90be1-104">You use a query designer when you build a query in a wizard or create a dataset query.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="90be1-105">Un dataset repose sur une source de données.</span><span class="sxs-lookup"><span data-stu-id="90be1-105">A dataset is based on a data source.</span></span> <span data-ttu-id="90be1-106">Le type de source de données et l'environnement de création détermine le concepteur de requêtes qui s'ouvre lorsque vous définissez la requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="90be1-106">The type of data source and the authoring environment determines which query designer opens when you define the dataset query.</span></span> <span data-ttu-id="90be1-107">Les fonctionnalités du concepteur de requêtes varient selon le type de source de données sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="90be1-107">Query designer features vary based on the underlying data source.</span></span> <span data-ttu-id="90be1-108">Pour plus d’informations sur les couches de données, consultez [connexions de données, sources de données et chaînes de connexion dans générateur de rapports](../data-connections-data-sources-and-connection-strings-in-report-builder.md) ou [connexions de données, sources de données et chaînes de connexion dans Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="90be1-108">For more information about data layers, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) or [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span></span>  
  
 <span data-ttu-id="90be1-109">Vous pouvez utiliser un concepteur de requêtes pour les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="90be1-109">You can use a query designer for the following tasks:</span></span>  
  
-   <span data-ttu-id="90be1-110">explorer les métadonnées de plusieurs schémas sur la source de données externe ;</span><span class="sxs-lookup"><span data-stu-id="90be1-110">Explore the metadata for multiple schemas on the external data source</span></span>  
  
-   <span data-ttu-id="90be1-111">spécifier des champs à récupérer pour le dataset ;</span><span class="sxs-lookup"><span data-stu-id="90be1-111">Specify fields to retrieve for the dataset</span></span>  
  
-   <span data-ttu-id="90be1-112">spécifier des relations entre deux objets tels que des tables ;</span><span class="sxs-lookup"><span data-stu-id="90be1-112">Specify relationships between two objects such as tables</span></span>  
  
-   <span data-ttu-id="90be1-113">spécifier des filtres pour restreindre les données avant qu'elles ne soient récupérées en tant que données de rapport ;</span><span class="sxs-lookup"><span data-stu-id="90be1-113">Specify filters to restrict the data before it is retrieved as report data</span></span>  
  
-   <span data-ttu-id="90be1-114">indiquer s'il faut créer des paramètres ;</span><span class="sxs-lookup"><span data-stu-id="90be1-114">Indicate whether to create parameters</span></span>  
  
-   <span data-ttu-id="90be1-115">spécifier des agrégats pour effectuer des calculs sur la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="90be1-115">Specify aggregates to perform calculations on the external data source</span></span>  
  
 <span data-ttu-id="90be1-116">Après avoir ouvert un concepteur de requêtes, vous générez une requête de la même façon pour un dataset incorporé ou un dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="90be1-116">After you open a query designer, you build a query in the same way for either an embedded dataset or a shared dataset.</span></span> <span data-ttu-id="90be1-117">Les procédures suivantes utilisent une requête de dataset incorporé.</span><span class="sxs-lookup"><span data-stu-id="90be1-117">The following procedures use an embedded dataset query.</span></span>  
  
 <span data-ttu-id="90be1-118">Pour plus d’informations, consultez [Interface utilisateur du Concepteur de requêtes relationnelles &#40;Générateur de rapports&#41;](relational-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="90be1-118">For more information, see [Relational Query Designer User Interface &#40;Report Builder&#41;](relational-query-designer-user-interface-report-builder.md).</span></span>  
  
### <a name="to-build-a-query-for-an-embedded-dataset-in-report-design-view"></a><span data-ttu-id="90be1-119">Pour générer une requête pour un dataset incorporé en mode création de rapport</span><span class="sxs-lookup"><span data-stu-id="90be1-119">To build a query for an embedded dataset in Report Design View</span></span>  
  
1.  <span data-ttu-id="90be1-120">Ouvrir le concepteur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="90be1-120">Open the query designer.</span></span> <span data-ttu-id="90be1-121">Dans le volet des données de rapport, cliquez avec le bouton droit sur le dataset, puis cliquez sur **Requête**.</span><span class="sxs-lookup"><span data-stu-id="90be1-121">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
     <span data-ttu-id="90be1-122">Le concepteur de requêtes associé à la source de données s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="90be1-122">The query designer that is associated with the data source opens.</span></span>  
  
2.  <span data-ttu-id="90be1-123">Dans le volet Vue de base de données, développez les dossiers qui affichent une vue hiérarchique des objets de schéma de base de données tels que les tables, les vues et les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="90be1-123">In the Database view pane, expand the folders that display a hierarchical view of database schema objects such as tables, views, and stored procedures.</span></span> <span data-ttu-id="90be1-124">Cliquez sur la zone de sélection pour sélectionner tous les champs d'un objet ou développez le nœud pour sélectionner des champs individuels.</span><span class="sxs-lookup"><span data-stu-id="90be1-124">Click the select box to select all fields for an object or expand the node to select individual fields.</span></span>  
  
     <span data-ttu-id="90be1-125">Quand vous sélectionnez des champs du volet Vue de base de données, le volet **Champs sélectionnés** affiche vos sélections.</span><span class="sxs-lookup"><span data-stu-id="90be1-125">As you select fields from the Database view pane, the **Select fields** pane displays your selections.</span></span>  
  
     <span data-ttu-id="90be1-126">Si vous sélectionnez des champs à partir de plusieurs tables de base de données associées, utilisez le volet Relations pour voir les relations détectées entre les tables à partir du schéma de base de données.</span><span class="sxs-lookup"><span data-stu-id="90be1-126">If you select fields from more than one related database table, use the Relationships pane to view the table relationships that were detected from the database schema.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="90be1-127">La liste des champs de dataset s'affiche dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="90be1-127">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-specify-limits-for-a-query"></a><span data-ttu-id="90be1-128">Pour spécifier les limites d'une requête</span><span class="sxs-lookup"><span data-stu-id="90be1-128">To specify limits for a query</span></span>  
  
1.  <span data-ttu-id="90be1-129">Dans le concepteur de requêtes relationnelles, vérifiez que des champs sont sélectionnés et qu’ils sont affichés dans le volet **Champs sélectionnés** .</span><span class="sxs-lookup"><span data-stu-id="90be1-129">In the relational query designer, verify that you have fields selected and that the fields appear in the **Selected fields** pane.</span></span>  
  
2.  <span data-ttu-id="90be1-130">Dans la barre d’outils du volet Filtres appliqués, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="90be1-130">In the Applied filters pane toolbar, click **Add Filter**.</span></span> <span data-ttu-id="90be1-131">Une nouvelle ligne de filtres apparaît.</span><span class="sxs-lookup"><span data-stu-id="90be1-131">A new filter row appears.</span></span>  
  
3.  <span data-ttu-id="90be1-132">Dans **Nom du champ**, cliquez pour afficher la liste déroulante des champs, puis cliquez sur le nom du champ servant de filtre.</span><span class="sxs-lookup"><span data-stu-id="90be1-132">In **Field name**, click to display the drop-down list of fields, and then click the name of the field that you want to filter by.</span></span> <span data-ttu-id="90be1-133">Par exemple, pour filtrer par quantité, cliquez sur le champ qui contient le nombre d'éléments.</span><span class="sxs-lookup"><span data-stu-id="90be1-133">For example, to filter by quantity, click the field that contains the number of items.</span></span>  
  
4.  <span data-ttu-id="90be1-134">Dans **Opérateur**, cliquez pour afficher la liste déroulante des opérateurs, puis sélectionnez l’opérateur de comparaison à utiliser dans le filtre.</span><span class="sxs-lookup"><span data-stu-id="90be1-134">In **Operator**, click to display the drop-down list of operators, and then select the comparison operator to use in the filter.</span></span>  
  
5.  <span data-ttu-id="90be1-135">Dans **Valeur**, tapez la valeur qui doit servir de filtre.</span><span class="sxs-lookup"><span data-stu-id="90be1-135">In **Value**, type the value that you want to filter by.</span></span> <span data-ttu-id="90be1-136">Par exemple, pour filtrer les quantités supérieures à 100, tapez 100.</span><span class="sxs-lookup"><span data-stu-id="90be1-136">For example, to filter on quantity greater than 100, type 100.</span></span>  
  
6.  <span data-ttu-id="90be1-137">Sélectionnez l'option de paramètre dans cette ligne pour créer un paramètre de dataset afin de permettre à l'utilisateur de spécifier une valeur de filtre.</span><span class="sxs-lookup"><span data-stu-id="90be1-137">Select the parameter option in this row to create a dataset parameter to enable a user to specify a filter value.</span></span> <span data-ttu-id="90be1-138">Un paramètre de rapport qui correspond au paramètre de dataset est créé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="90be1-138">A report parameter that matches the dataset parameter is automatically created.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="90be1-139">La liste des champs de dataset s'affiche dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="90be1-139">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-view-a-query-result-set"></a><span data-ttu-id="90be1-140">Pour afficher un jeu de résultats de requête</span><span class="sxs-lookup"><span data-stu-id="90be1-140">To view a query result set</span></span>  
  
1.  <span data-ttu-id="90be1-141">Dans la barre d’outils du Concepteur de requêtes, cliquez sur **Exécuter la requête (!)** .</span><span class="sxs-lookup"><span data-stu-id="90be1-141">On the query designer toolbar, click **Run Query (!)**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="90be1-142">Le concepteur de requêtes utilise des informations d'identification au moment de la conception pour exécuter la requête et récupérer le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="90be1-142">The query designer uses design time credentials to run the query and retrieve the result set.</span></span> <span data-ttu-id="90be1-143">Pour plus d’informations, consultez [Spécifier des informations d’identification dans le Générateur de rapports](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="90be1-143">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="90be1-144">La requête s'exécute sur la source de données et retourne des exemples de données dans le volet Résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="90be1-144">The query runs on the data source and returns example data in the Query results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90be1-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90be1-145">See Also</span></span>  
 <span data-ttu-id="90be1-146">[Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="90be1-146">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="90be1-147">[Ajouter des données à partir de sources de données externes &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="90be1-147">[Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="90be1-148">[Concepteurs de requêtes &#40;Générateur de rapports&#41;](../query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="90be1-148">[Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="90be1-149">[Créer un dataset partagé ou incorporé &#40;Générateur de rapports et SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="90be1-149">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="90be1-150">[Vue Conception de rapport &#40;Générateur de rapports&#41;](../report-builder/report-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="90be1-150">[Report Design View &#40;Report Builder&#41;](../report-builder/report-design-view-report-builder.md) </span></span>  
 <span data-ttu-id="90be1-151">[Mode création de dataset partagé &#40;Générateur de rapports&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="90be1-151">[Shared Dataset Design View &#40;Report Builder&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span></span>  
 [<span data-ttu-id="90be1-152">Concepteurs de requêtes Reporting Services</span><span class="sxs-lookup"><span data-stu-id="90be1-152">Reporting Services Query Designers</span></span>](../reporting-services-query-designers.md)  
  
  
