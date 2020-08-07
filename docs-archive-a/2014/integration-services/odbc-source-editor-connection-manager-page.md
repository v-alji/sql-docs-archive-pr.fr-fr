---
title: Éditeur de source ODBC (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.connection.f1
ms.assetid: e2c8dc83-6394-4d6c-9232-97e94be72431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c8b54ce4a1c1b3fea0afb51f1cbf7447971ccab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703184"
---
# <a name="odbc-source-editor-connection-manager-page"></a><span data-ttu-id="97339-102">Éditeur de source ODBC (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="97339-102">ODBC Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="97339-103">Utilisez la page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de source ODBC** pour sélectionner le gestionnaire de connexions ODBC pour la source.</span><span class="sxs-lookup"><span data-stu-id="97339-103">Use the **Connection Manager** page of the **ODBC Source Editor** dialog box to select the ODBC connection manager for the source.</span></span> <span data-ttu-id="97339-104">Cette page vous permet également de sélectionner une table ou une vue à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="97339-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="97339-105">Pour plus d'informations sur la source ODBC, consultez [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="97339-105">For more information about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="97339-106">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="97339-106">Task List</span></span>  
 <span data-ttu-id="97339-107">**Pour ouvrir l'Éditeur de source ODBC (page Gestionnaire de connexions)**</span><span class="sxs-lookup"><span data-stu-id="97339-107">**To open the ODBC Source Editor Connection Manager Page**</span></span>  
  
-   <span data-ttu-id="97339-108">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le package [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] qui possède la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="97339-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="97339-109">Sous l’onglet **Flux de données** , double-cliquez sur la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="97339-109">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="97339-110">Options</span><span class="sxs-lookup"><span data-stu-id="97339-110">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="97339-111">Gestionnaire de connexions</span><span class="sxs-lookup"><span data-stu-id="97339-111">Connection manager</span></span>  
 <span data-ttu-id="97339-112">Sélectionnez un gestionnaire de connexions ODBC existant dans la liste ou cliquez sur **nouveau** pour créer une nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="97339-112">Select an existing ODBC connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="97339-113">La connexion peut concerner n'importe quelle base de données prise en charge par ODBC.</span><span class="sxs-lookup"><span data-stu-id="97339-113">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="97339-114">Nouveau</span><span class="sxs-lookup"><span data-stu-id="97339-114">New</span></span>  
 <span data-ttu-id="97339-115">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="97339-115">Click **New**.</span></span> <span data-ttu-id="97339-116">La boîte de dialogue **Configurer l'Éditeur du gestionnaire de connexions ODBC** s'ouvre et vous permet de créer un nouveau gestionnaire de connexions ODBC.</span><span class="sxs-lookup"><span data-stu-id="97339-116">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new ODBC connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="97339-117">Mode d'accès aux données</span><span class="sxs-lookup"><span data-stu-id="97339-117">Data Access Mode</span></span>  
 <span data-ttu-id="97339-118">Spécifiez la méthode de sélection des données dans la source.</span><span class="sxs-lookup"><span data-stu-id="97339-118">Select the method for selecting data from the source.</span></span> <span data-ttu-id="97339-119">Ces fonctions sont répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="97339-119">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="97339-120">Option</span><span class="sxs-lookup"><span data-stu-id="97339-120">Option</span></span>|<span data-ttu-id="97339-121">Description</span><span class="sxs-lookup"><span data-stu-id="97339-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="97339-122">Nom de la table</span><span class="sxs-lookup"><span data-stu-id="97339-122">Table Name</span></span>|<span data-ttu-id="97339-123">Permet de récupérer les données d'une table ou d'une vue dans la source de données ODBC.</span><span class="sxs-lookup"><span data-stu-id="97339-123">Retrieve data from a table or view in the ODBC data source.</span></span> <span data-ttu-id="97339-124">Lorsque vous sélectionnez cette option, sélectionnez une valeur parmi les suivantes dans la liste :</span><span class="sxs-lookup"><span data-stu-id="97339-124">When you select this option, select a value from the list for the following:</span></span>|  
||<span data-ttu-id="97339-125">**Nom de la table ou de la vue**: sélectionnez une table ou une vue disponible dans la liste ou tapez une expression régulière pour identifier la table.</span><span class="sxs-lookup"><span data-stu-id="97339-125">**Name of the table or the view**: Select an available table or view from the list or type a regular expression to identify the table.</span></span>|  
||<span data-ttu-id="97339-126">Cette liste contient les 1 000 premières tables uniquement.</span><span class="sxs-lookup"><span data-stu-id="97339-126">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="97339-127">Si votre base de données contient plus de 1 000 tables, vous pouvez taper le début du nom d'une table ou utiliser le caractère générique (\*) pour entrer une partie du nom afin d'afficher la table ou les tables que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="97339-127">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
|<span data-ttu-id="97339-128">Commande SQL</span><span class="sxs-lookup"><span data-stu-id="97339-128">SQL command</span></span>|<span data-ttu-id="97339-129">Extrayez les données de la source de données ODBC à l'aide d'une requête SQL.</span><span class="sxs-lookup"><span data-stu-id="97339-129">Retrieve data from the ODBC data source by using an SQL query.</span></span> <span data-ttu-id="97339-130">Vous devez écrire la requête dans la syntaxe de la base de données source dans laquelle vous travaillez.</span><span class="sxs-lookup"><span data-stu-id="97339-130">You should write the query in the syntax of the source database you are working with.</span></span> <span data-ttu-id="97339-131">Lorsque vous sélectionnez cette option, entrez une requête selon l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="97339-131">When you select this option, enter a query in one of the following ways:</span></span>|  
||<span data-ttu-id="97339-132">Entrez le texte de la requête SQL dans le champ **Texte de la commande SQL** .</span><span class="sxs-lookup"><span data-stu-id="97339-132">Enter the text of the SQL query in the **SQL command text** field.</span></span>|  
||<span data-ttu-id="97339-133">Cliquez sur **Parcourir** pour charger la requête SQL à partir d'un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="97339-133">Click **Browse** to load the SQL query from a text file.</span></span>|  
||<span data-ttu-id="97339-134">Pour vérifier la syntaxe du texte de la requête, cliquez sur **Analyser** .</span><span class="sxs-lookup"><span data-stu-id="97339-134">Click **Parse query** to verify the syntax of the query text.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="97339-135">PRÉVERSION</span><span class="sxs-lookup"><span data-stu-id="97339-135">Preview</span></span>  
 <span data-ttu-id="97339-136">Cliquez sur **Aperçu** pour afficher les 200 premières lignes de données extraites de la table ou de la vue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="97339-136">Click **Preview** to view up to the first 200 rows of the data extracted from the table or view you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97339-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97339-137">See Also</span></span>  
 <span data-ttu-id="97339-138">[Propriétés personnalisées des sources ODBC](data-flow/odbc-source-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="97339-138">[ODBC Source Custom Properties](data-flow/odbc-source-custom-properties.md) </span></span>  
 <span data-ttu-id="97339-139">[Éditeur de source ODBC &#40;page colonnes&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="97339-139">[ODBC Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="97339-140">Éditeur de source ODBC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="97339-140">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
