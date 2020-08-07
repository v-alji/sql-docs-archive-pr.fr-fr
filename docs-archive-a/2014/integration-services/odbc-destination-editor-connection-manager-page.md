---
title: Éditeur de destination ODBC (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.connection.f1
ms.assetid: f6d9c6c2-e4c4-468b-9e0d-af7b9609614d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e4fc1073bb187c0864d2991459a358a7f81d066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703196"
---
# <a name="odbc-destination-editor-connection-manager-page"></a><span data-ttu-id="61d58-102">Éditeur de destination ODBC (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="61d58-102">ODBC Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="61d58-103">Utilisez la page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de destination ODBC** pour sélectionner le gestionnaire de connexions ODBC de la destination.</span><span class="sxs-lookup"><span data-stu-id="61d58-103">Use the **Connection Manager** page of the **ODBC Destination Editor** dialog box to select the ODBC connection manager for the destination.</span></span> <span data-ttu-id="61d58-104">Cette page vous permet également de sélectionner une table ou une vue à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="61d58-104">This page also lets you select a table or view from the database</span></span>  
  
 <span data-ttu-id="61d58-105">Pour plus d'informations sur cette destination ODBC, consultez [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="61d58-105">For more information about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="61d58-106">**Pour ouvrir l'Éditeur de destination ODBC (page Gestionnaire de connexions)**</span><span class="sxs-lookup"><span data-stu-id="61d58-106">**To open the ODBC Destination Editor Connection Manager Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="61d58-107">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="61d58-107">Task List</span></span>  
  
-   <span data-ttu-id="61d58-108">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le package [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] qui possède la destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="61d58-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="61d58-109">Sous l’onglet **Flux de données** , double-cliquez sur la destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="61d58-109">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="61d58-110">Dans l' **Éditeur de destination ODBC**, cliquez sur **Gestionnaire de connexions**.</span><span class="sxs-lookup"><span data-stu-id="61d58-110">In the **ODBC Destination Editor**, click **Connection Manager**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="61d58-111">Options</span><span class="sxs-lookup"><span data-stu-id="61d58-111">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="61d58-112">Gestionnaire de connexions</span><span class="sxs-lookup"><span data-stu-id="61d58-112">Connection manager</span></span>  
 <span data-ttu-id="61d58-113">Sélectionnez un gestionnaire de connexions ODBC existant dans la liste ou cliquez sur Nouveau pour créer une nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="61d58-113">Select an existing ODBC connection manager from the list, or click New to create a new connection.</span></span> <span data-ttu-id="61d58-114">La connexion peut concerner n'importe quelle base de données prise en charge par ODBC.</span><span class="sxs-lookup"><span data-stu-id="61d58-114">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="61d58-115">Nouveau</span><span class="sxs-lookup"><span data-stu-id="61d58-115">New</span></span>  
 <span data-ttu-id="61d58-116">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="61d58-116">Click **New**.</span></span> <span data-ttu-id="61d58-117">La boîte de dialogue **Configurer l'Éditeur du gestionnaire de connexions ODBC** s'ouvre et vous permet de créer un nouveau gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="61d58-117">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="61d58-118">Mode d'accès aux données</span><span class="sxs-lookup"><span data-stu-id="61d58-118">Data Access Mode</span></span>  
 <span data-ttu-id="61d58-119">Spécifiez la méthode de chargement des données dans la destination.</span><span class="sxs-lookup"><span data-stu-id="61d58-119">Select the method for loading data to the destination.</span></span> <span data-ttu-id="61d58-120">Ces fonctions sont répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="61d58-120">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="61d58-121">Option</span><span class="sxs-lookup"><span data-stu-id="61d58-121">Option</span></span>|<span data-ttu-id="61d58-122">Description</span><span class="sxs-lookup"><span data-stu-id="61d58-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="61d58-123">Nom de la table - Lot</span><span class="sxs-lookup"><span data-stu-id="61d58-123">Table Name - Batch</span></span>|<span data-ttu-id="61d58-124">Sélectionnez cette option pour configurer la destination ODBC en mode par lot.</span><span class="sxs-lookup"><span data-stu-id="61d58-124">Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="61d58-125">Lorsque vous sélectionnez cette option, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="61d58-125">When you select this option the following options are available:</span></span>|  
||<span data-ttu-id="61d58-126">**Nom de la table ou de la vue**: sélectionnez une table ou une vue disponible dans la liste.</span><span class="sxs-lookup"><span data-stu-id="61d58-126">**Name of the table or the view**: Select an available table or view from the list.</span></span><br /><br /> <span data-ttu-id="61d58-127">Cette liste contient les 1 000 premières tables uniquement.</span><span class="sxs-lookup"><span data-stu-id="61d58-127">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="61d58-128">Si votre base de données contient plus de 1000 tables, vous pouvez taper le début du nom d’une table ou utiliser le caractère générique (\*) pour entrer une partie du nom afin d’afficher la table ou les tables que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="61d58-128">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span><br /><br /> <span data-ttu-id="61d58-129">**Taille du lot**: entrez la taille du lot pour le chargement en bloc.</span><span class="sxs-lookup"><span data-stu-id="61d58-129">**Batch size**: Type the size of the batch for bulk loading.</span></span> <span data-ttu-id="61d58-130">Il s'agit du nombre de lignes chargées dans un même lot.</span><span class="sxs-lookup"><span data-stu-id="61d58-130">This is the number of rows loaded as a batch</span></span>|  
|<span data-ttu-id="61d58-131">Nom de la table - Ligne par ligne</span><span class="sxs-lookup"><span data-stu-id="61d58-131">Table Name - Row by Row</span></span>|<span data-ttu-id="61d58-132">Sélectionnez cette option pour configurer la destination ODBC de manière à insérer les lignes dans la table de destination une par une.</span><span class="sxs-lookup"><span data-stu-id="61d58-132">Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="61d58-133">Lorsque vous sélectionnez cette option, l'option suivante est disponible :</span><span class="sxs-lookup"><span data-stu-id="61d58-133">When you select this option the following option is available:</span></span>|  
||<span data-ttu-id="61d58-134">**Nom de la table ou de la vue**: sélectionnez dans la liste une table ou une vue disponible dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="61d58-134">**Name of the table or the view**: Select an available table or view from the database from the list.</span></span><br /><br /> <span data-ttu-id="61d58-135">Cette liste contient les 1 000 premières tables uniquement.</span><span class="sxs-lookup"><span data-stu-id="61d58-135">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="61d58-136">Si votre base de données contient plus de 1 000 tables, vous pouvez taper le début du nom d'une table ou utiliser le caractère générique (\*) pour entrer une partie du nom afin d'afficher la table ou les tables que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="61d58-136">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="61d58-137">PRÉVERSION</span><span class="sxs-lookup"><span data-stu-id="61d58-137">Preview</span></span>  
 <span data-ttu-id="61d58-138">Cliquez sur **Aperçu** pour afficher jusqu'à 200 lignes de données pour la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="61d58-138">Click **Preview** to view up to 200 rows of data for the table that you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d58-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61d58-139">See Also</span></span>  
 <span data-ttu-id="61d58-140">[Propriétés personnalisées de la destination ODBC](data-flow/odbc-destination-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="61d58-140">[ODBC Destination Custom Properties](data-flow/odbc-destination-custom-properties.md) </span></span>  
 <span data-ttu-id="61d58-141">[Éditeur de destination ODBC &#40;page Mappages&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="61d58-141">[ODBC Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="61d58-142">Éditeur de destination ODBC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="61d58-142">ODBC Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-error-output-page.md)  
  
  
