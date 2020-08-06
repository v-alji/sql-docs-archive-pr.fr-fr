---
title: Boîte de dialogue Propriétés du DataSet, requête | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10160"
- sql12.rtp.rptdesigner.datasetproperties.query.f1
ms.assetid: 1fa34a4b-7de0-4e92-99fa-bc28a206773f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bffb14155d37e67333eb626747e1fcc54e618bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614395"
---
# <a name="dataset-properties-dialog-box-query"></a><span data-ttu-id="7a45e-102">Boîte de dialogue Propriétés du dataset, Requête</span><span class="sxs-lookup"><span data-stu-id="7a45e-102">Dataset Properties Dialog Box, Query</span></span>
  <span data-ttu-id="7a45e-103">Sélectionnez **Requête** dans la boîte de dialogue **Propriétés du dataset** pour choisir une source de données et créer une requête.</span><span class="sxs-lookup"><span data-stu-id="7a45e-103">Select **Query** on the **Dataset Properties** dialog box to choose a data source and create a query.</span></span>  
  
 <span data-ttu-id="7a45e-104">La boîte de dialogue **Propriétés du dataset** inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7a45e-104">The **Dataset Properties** dialog box includes the following:</span></span>  
  
-   [<span data-ttu-id="7a45e-105">Boîte de dialogue Propriétés du dataset, Paramètres</span><span class="sxs-lookup"><span data-stu-id="7a45e-105">Dataset Properties Dialog Box, Parameters</span></span>](report-data/dataset-properties-dialog-box-parameters.md)  
  
-   [<span data-ttu-id="7a45e-106">Boîte de dialogue Propriétés du dataset, Champs</span><span class="sxs-lookup"><span data-stu-id="7a45e-106">Dataset Properties Dialog Box, Fields</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-fields.md)  
  
-   [<span data-ttu-id="7a45e-107">Boîte de dialogue Propriétés du dataset, Options</span><span class="sxs-lookup"><span data-stu-id="7a45e-107">Dataset Properties Dialog Box, Options</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-options.md)  
  
-   [<span data-ttu-id="7a45e-108">Boîte de dialogue Propriétés du dataset, Filtres</span><span class="sxs-lookup"><span data-stu-id="7a45e-108">Dataset Properties Dialog Box, Filters</span></span>](report-data/dataset-properties-dialog-box-filters.md)  
  
## <a name="options"></a><span data-ttu-id="7a45e-109">Options</span><span class="sxs-lookup"><span data-stu-id="7a45e-109">Options</span></span>  
 <span data-ttu-id="7a45e-110">**Nom**</span><span class="sxs-lookup"><span data-stu-id="7a45e-110">**Name**</span></span>  
 <span data-ttu-id="7a45e-111">Tapez le nom du dataset.</span><span class="sxs-lookup"><span data-stu-id="7a45e-111">Type a name for the dataset.</span></span> <span data-ttu-id="7a45e-112">Ce nom doit être différent de celui des régions ou des groupes de données du rapport.</span><span class="sxs-lookup"><span data-stu-id="7a45e-112">The name cannot be the same as a name for any data region or group in the report.</span></span>  
  
 <span data-ttu-id="7a45e-113">**Source de données**</span><span class="sxs-lookup"><span data-stu-id="7a45e-113">**Data Source**</span></span>  
 <span data-ttu-id="7a45e-114">Sélectionnez la source de données sur laquelle baser le dataset.</span><span class="sxs-lookup"><span data-stu-id="7a45e-114">Select the data source on which to base the dataset.</span></span> <span data-ttu-id="7a45e-115">Cliquez sur **Nouvelle**pour créer une nouvelle source de données.</span><span class="sxs-lookup"><span data-stu-id="7a45e-115">To create a new data source, click **New**.</span></span>  
  
 <span data-ttu-id="7a45e-116">**Type de requête**</span><span class="sxs-lookup"><span data-stu-id="7a45e-116">**Query type**</span></span>  
 <span data-ttu-id="7a45e-117">Sélectionnez le type de commande ou de requête à utiliser pour le dataset.</span><span class="sxs-lookup"><span data-stu-id="7a45e-117">Select the type of command or query to use for the dataset.</span></span> <span data-ttu-id="7a45e-118">Sélectionnez **Texte** pour exécuter une requête afin d'extraire des données de la base de données.</span><span class="sxs-lookup"><span data-stu-id="7a45e-118">Select **Text** to run a query to retrieve data from the database.</span></span> <span data-ttu-id="7a45e-119">Sélectionnez **Table** pour utiliser la fonctionnalité **TableDirect** de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] afin de sélectionner tous les champs d'une table.</span><span class="sxs-lookup"><span data-stu-id="7a45e-119">Select **Table** to use the **TableDirect** feature of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to select all the fields within a table.</span></span> <span data-ttu-id="7a45e-120">Sélectionnez **Procédure stockée** pour exécuter une procédure stockée par nom.</span><span class="sxs-lookup"><span data-stu-id="7a45e-120">Select **Stored Procedure** to run a stored procedure by name.</span></span> <span data-ttu-id="7a45e-121">**Texte** est sélectionné par défaut et est utilisé pour la plupart des requêtes.</span><span class="sxs-lookup"><span data-stu-id="7a45e-121">**Text** is selected by default and is used for most queries.</span></span> <span data-ttu-id="7a45e-122">Pour modifier la requête de source de données sélectionnée, cliquez sur **Concepteur de requêtes**.</span><span class="sxs-lookup"><span data-stu-id="7a45e-122">To edit the selected data source query, click **Query Designer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a45e-123">Les types de requêtes ne sont pas tous pris en charge par toutes les sources de données.</span><span class="sxs-lookup"><span data-stu-id="7a45e-123">Not all query types are supported by all data sources.</span></span> <span data-ttu-id="7a45e-124">Par exemple, le type **Table** n'est pris en charge que par les types de sources de données **OLE DB** et **ODBC**.</span><span class="sxs-lookup"><span data-stu-id="7a45e-124">For example, **Table** is supported only by data source types **OLE DB** and **ODBC**.</span></span>  
  
 <span data-ttu-id="7a45e-125">**Requête**</span><span class="sxs-lookup"><span data-stu-id="7a45e-125">**Query**</span></span>  
 <span data-ttu-id="7a45e-126">Cette option apparaît quand vous choisissez l’option de type de commande **Texte** .</span><span class="sxs-lookup"><span data-stu-id="7a45e-126">This option appears when you choose the **Text** command type option.</span></span> <span data-ttu-id="7a45e-127">Tapez une requête ou importez-en une existante en cliquant sur **Importer**.</span><span class="sxs-lookup"><span data-stu-id="7a45e-127">Type a query or import a pre-existing query by clicking **Import**.</span></span> <span data-ttu-id="7a45e-128">Cliquez sur le bouton **Expression** (*fx*) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="7a45e-128">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a45e-129">Si vous avez utilisé un concepteur de requêtes pour générer une requête, le texte de celle-ci s'affiche dans cette zone.</span><span class="sxs-lookup"><span data-stu-id="7a45e-129">If you used a query designer to build a query, the text of the query appears in this box.</span></span>  
  
 <span data-ttu-id="7a45e-130">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="7a45e-130">**Table name**</span></span>  
 <span data-ttu-id="7a45e-131">Entrez le nom de la table que vous souhaitez utiliser comme dataset.</span><span class="sxs-lookup"><span data-stu-id="7a45e-131">Enter the name of the table that you want to use as a dataset.</span></span> <span data-ttu-id="7a45e-132">Cette option apparaît lorsque vous sélectionnez **Table**.</span><span class="sxs-lookup"><span data-stu-id="7a45e-132">This option appears when you select **Table**.</span></span>  
  
 <span data-ttu-id="7a45e-133">**Sélectionnez ou entrez un nom de procédure stockée**</span><span class="sxs-lookup"><span data-stu-id="7a45e-133">**Select or enter stored procedure name**</span></span>  
 <span data-ttu-id="7a45e-134">Tapez ou choisissez le nom de la procédure stockée que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="7a45e-134">Type or choose the name of the stored procedure that you want to use.</span></span> <span data-ttu-id="7a45e-135">Cliquez sur le bouton **Expression** (*fx*) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="7a45e-135">Click the **Expression** (*fx*) button to edit the expression.</span></span> <span data-ttu-id="7a45e-136">Cette option apparaît lorsque vous choisissez l'option de type de commande Procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="7a45e-136">This option appears when you choose the Stored Procedure command type option.</span></span>  
  
 <span data-ttu-id="7a45e-137">**Délai dépassé (en secondes)**</span><span class="sxs-lookup"><span data-stu-id="7a45e-137">**Time out (in seconds)**</span></span>  
 <span data-ttu-id="7a45e-138">Tapez le nombre de secondes avant l’expiration de la requête. La valeur par défaut est de 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="7a45e-138">Type the number of seconds until the query times out. The default is 30 seconds.</span></span> <span data-ttu-id="7a45e-139">La valeur de **Délai dépassé** doit être vide ou supérieure à zéro.</span><span class="sxs-lookup"><span data-stu-id="7a45e-139">The value for **Time out** must be empty or greater than zero.</span></span> <span data-ttu-id="7a45e-140">Si elle ne contient aucune valeur, la requête n'est soumise à aucun délai d'expiration.</span><span class="sxs-lookup"><span data-stu-id="7a45e-140">If it is empty, the query does not time out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a45e-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a45e-141">See Also</span></span>  
 <span data-ttu-id="7a45e-142">[Connexions de données, sources de données et chaînes de connexion dans Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7a45e-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="7a45e-143">[Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7a45e-143">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="7a45e-144">[Concepteurs de requêtes &#40;Générateur de rapports&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="7a45e-144">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 [<span data-ttu-id="7a45e-145">Concepteurs de requêtes Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7a45e-145">Reporting Services Query Designers</span></span>](../../2014/reporting-services/reporting-services-query-designers.md)  
  
  
