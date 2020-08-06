---
title: Éditeur de transformation de recherche (page connexion) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.referencetable.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: e90d6b69-5a26-43c5-8433-5c3c9588e08c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 381378ac1aca85c6bca825033bc439ebc39fb063
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605553"
---
# <a name="lookup-transformation-editor-connection-page"></a><span data-ttu-id="a45fa-102">Éditeur de transformation de recherche (page Connexion)</span><span class="sxs-lookup"><span data-stu-id="a45fa-102">Lookup Transformation Editor (Connection Page)</span></span>
  <span data-ttu-id="a45fa-103">Utilisez la page **Connexion** de la boîte de dialogue **Éditeur de transformation de recherche** pour sélectionner un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="a45fa-103">Use the **Connection** page of the **Lookup Transformation Editor** dialog box to select a connection manager.</span></span> <span data-ttu-id="a45fa-104">Si vous sélectionnez un gestionnaire de connexions OLE DB, vous sélectionnez également une requête, une table ou une vue pour générer le dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="a45fa-104">If you select an OLE DB connection manager, you also select a query, table, or view to generate the reference dataset.</span></span>  
  
 <span data-ttu-id="a45fa-105">Pour en savoir plus sur la transformation de recherche, consultez [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a45fa-105">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a45fa-106">Options</span><span class="sxs-lookup"><span data-stu-id="a45fa-106">Options</span></span>  
 <span data-ttu-id="a45fa-107">Les options suivantes sont disponibles quand vous sélectionnez **Cache complet** et **Gestionnaire de connexions du cache** dans la page Général de la boîte de dialogue **Éditeur de transformation de recherche** .</span><span class="sxs-lookup"><span data-stu-id="a45fa-107">The following options are available when you select **Full cache** and **Cache connection manager** on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="a45fa-108">**Gestionnaire de connexions du cache**</span><span class="sxs-lookup"><span data-stu-id="a45fa-108">**Cache connection manager**</span></span>  
 <span data-ttu-id="a45fa-109">Sélectionnez un gestionnaire de connexions du cache existant dans la liste ou créez une connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a45fa-109">Select an existing Cache connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="a45fa-110">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="a45fa-110">**New**</span></span>  
 <span data-ttu-id="a45fa-111">Créez une connexion à l’aide de la boîte de dialogue **Éditeur du gestionnaire de connexions du cache** .</span><span class="sxs-lookup"><span data-stu-id="a45fa-111">Create a new connection by using the **Cache Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="a45fa-112">Les options suivantes sont disponibles quand vous sélectionnez **Cache complet**, **Cache partiel**ou **Aucun cache**et **Gestionnaire de connexions OLE DB**dans la page Général de la boîte de dialogue **Éditeur de transformation de recherche** .</span><span class="sxs-lookup"><span data-stu-id="a45fa-112">The following options are available when you select **Full cache**, **Partial cache**, or **No cache**, and **OLE DB connection manager**, on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="a45fa-113">**Gestionnaire de connexions OLE DB**</span><span class="sxs-lookup"><span data-stu-id="a45fa-113">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="a45fa-114">Sélectionnez un gestionnaire de connexions OLE DB existant dans la liste ou créez une connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a45fa-114">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="a45fa-115">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="a45fa-115">**New**</span></span>  
 <span data-ttu-id="a45fa-116">Crée une connexion en utilisant la boîte de dialogue **Configurer le gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="a45fa-116">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="a45fa-117">**Utiliser une table ou une vue**</span><span class="sxs-lookup"><span data-stu-id="a45fa-117">**Use a table or view**</span></span>  
 <span data-ttu-id="a45fa-118">Sélectionnez une table ou une vue existante dans la liste, ou créez une nouvelle table en cliquant sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a45fa-118">Select an existing table or view from the list, or create a new table by clicking **New**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a45fa-119">Si vous spécifiez une instruction SQL dans la page **Avancé** de l’ **Éditeur de transformation de recherche**, cette instruction SQL substitue et remplace le nom de table a sélectionné ici.</span><span class="sxs-lookup"><span data-stu-id="a45fa-119">If you specify a SQL statement on the **Advanced** page of the **Lookup Transformation Editor**, that SQL statement overrides and replaces the table name selected here.</span></span> <span data-ttu-id="a45fa-120">Pour plus d’informations, consultez [Éditeur de transformation de recherche &#40;page Avancé&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="a45fa-120">For more information, see [Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span></span>  
  
 <span data-ttu-id="a45fa-121">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="a45fa-121">**New**</span></span>  
 <span data-ttu-id="a45fa-122">Utilisez la boîte de dialogue **Créer une table** pour créer une table.</span><span class="sxs-lookup"><span data-stu-id="a45fa-122">Create a new table by using the **Create Table** dialog box.</span></span>  
  
 <span data-ttu-id="a45fa-123">**Utiliser les résultats d'une requête SQL**</span><span class="sxs-lookup"><span data-stu-id="a45fa-123">**Use results of an SQL query**</span></span>  
 <span data-ttu-id="a45fa-124">Choisissez cette option pour rechercher une requête existante, générer une requête, vérifier la syntaxe d'une requête et afficher un aperçu des résultats d'une requête.</span><span class="sxs-lookup"><span data-stu-id="a45fa-124">Choose this option to browse to a preexisting query, build a new query, check query syntax, and preview query results.</span></span>  
  
 <span data-ttu-id="a45fa-125">**Construire une requête**</span><span class="sxs-lookup"><span data-stu-id="a45fa-125">**Build query**</span></span>  
 <span data-ttu-id="a45fa-126">Créez l’instruction Transact-SQL à exécuter à l’aide du **Générateur de requêtes**. Cet outil graphique permet de créer des requêtes en explorant les données.</span><span class="sxs-lookup"><span data-stu-id="a45fa-126">Create the Transact-SQL statement to run by using **Query Builder**, a graphical tool that is used to create queries by browsing through data.</span></span>  
  
 <span data-ttu-id="a45fa-127">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="a45fa-127">**Browse**</span></span>  
 <span data-ttu-id="a45fa-128">Permet de rechercher une requête existante enregistrée dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="a45fa-128">Use this option to browse to a preexisting query saved as a file.</span></span>  
  
 <span data-ttu-id="a45fa-129">**Analyser la requête**</span><span class="sxs-lookup"><span data-stu-id="a45fa-129">**Parse Query**</span></span>  
 <span data-ttu-id="a45fa-130">Contrôle la syntaxe d'une requête.</span><span class="sxs-lookup"><span data-stu-id="a45fa-130">Check the syntax of the query.</span></span>  
  
 <span data-ttu-id="a45fa-131">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="a45fa-131">**Preview**</span></span>  
 <span data-ttu-id="a45fa-132">Affichez un aperçu des résultats à l’aide de la boîte de dialogue **Visualiser les résultats de la requête** .</span><span class="sxs-lookup"><span data-stu-id="a45fa-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="a45fa-133">Cette option affiche jusqu'à 200 lignes.</span><span class="sxs-lookup"><span data-stu-id="a45fa-133">This option displays up to 200 rows.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="a45fa-134">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="a45fa-134">External Resources</span></span>  
 <span data-ttu-id="a45fa-135">Entrée de blog, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) sur blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="a45fa-135">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45fa-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a45fa-136">See Also</span></span>  
 <span data-ttu-id="a45fa-137">[Éditeur de transformation de recherche &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a45fa-137">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="a45fa-138">[Éditeur de transformation de recherche &#40;page colonnes&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="a45fa-138">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="a45fa-139">[Éditeur de transformation de recherche &#40;&#41;de page avancé](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="a45fa-139">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="a45fa-140">[Éditeur de transformation de recherche &#40;page sortie d’erreur&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="a45fa-140">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="a45fa-141">transformation de recherche floue</span><span class="sxs-lookup"><span data-stu-id="a45fa-141">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
