---
title: Éditeur de source OData (page connexion) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- Sql12.dts.designer.odatasource.connection.f1
ms.assetid: 20bcd347-4547-4fad-b182-9571030101df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ecd0d060ea2197ae7174325b654645fefa23505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611156"
---
# <a name="odata-source-editor-connection-page"></a><span data-ttu-id="e7b8e-102">Éditeur de source OData (page Connexion)</span><span class="sxs-lookup"><span data-stu-id="e7b8e-102">OData Source Editor (Connection Page)</span></span>
  <span data-ttu-id="e7b8e-103">La page **Connexion** de la boîte de dialogue **Éditeur de source OData** vous permet de sélectionner le gestionnaire de connexions OData pour la source OData.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-103">Use the **Connection** page of the **OData Source Editor** dialog box to select the OData connection manager for the OData source.</span></span> <span data-ttu-id="e7b8e-104">Cette page vous permet également de spécifier une collection ou un chemin d'accès de ressources et toutes les options de requête permettant de spécifier quelles données doivent être récupérées à partir de la source OData.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-104">This page also lets you specify a collection or a resource path and any query options to indicate what data needs to be retrieved from the OData source.</span></span> <span data-ttu-id="e7b8e-105">Pour en savoir plus sur la source OData, consultez [Source OData](data-flow/odata-source.md).</span><span class="sxs-lookup"><span data-stu-id="e7b8e-105">To learn more about the OData source, see [OData Source](data-flow/odata-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="e7b8e-106">Options statiques</span><span class="sxs-lookup"><span data-stu-id="e7b8e-106">Static Options</span></span>  
 <span data-ttu-id="e7b8e-107">**Gestionnaire de connexions OData**</span><span class="sxs-lookup"><span data-stu-id="e7b8e-107">**OData connection manager**</span></span>  
 <span data-ttu-id="e7b8e-108">Sélectionnez un gestionnaire de connexions existant dans la liste ou créez une nouvelle connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-108">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="e7b8e-109">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="e7b8e-109">**New**</span></span>  
 <span data-ttu-id="e7b8e-110">Créez un gestionnaire de connexions à l’aide de la boîte de dialogue **Éditeur du gestionnaire de connexions OData** .</span><span class="sxs-lookup"><span data-stu-id="e7b8e-110">Create a new connection manager by using the **OData Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="e7b8e-111">**Utilisez une collection ou un chemin d'accès de ressource.**</span><span class="sxs-lookup"><span data-stu-id="e7b8e-111">**Use collection or resource path**</span></span>  
 <span data-ttu-id="e7b8e-112">Spécifiez la méthode de sélection des données dans la source.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-112">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="e7b8e-113">Option</span><span class="sxs-lookup"><span data-stu-id="e7b8e-113">Option</span></span>|<span data-ttu-id="e7b8e-114">Description</span><span class="sxs-lookup"><span data-stu-id="e7b8e-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e7b8e-115">Collection</span><span class="sxs-lookup"><span data-stu-id="e7b8e-115">Collection</span></span>|<span data-ttu-id="e7b8e-116">Extrayez les données de la source OData à l'aide d'un nom de collection.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-116">Retrieve data from the OData source by using a collection name.</span></span>|  
|<span data-ttu-id="e7b8e-117">Chemin d'accès de ressource</span><span class="sxs-lookup"><span data-stu-id="e7b8e-117">Resource Path</span></span>|<span data-ttu-id="e7b8e-118">Extrayez les données de la source OData à l'aide d'un chemin d'accès de ressource.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-118">Retrieve data from the OData source by using a resource path.</span></span>|  
  
 <span data-ttu-id="e7b8e-119">**Options de requête**</span><span class="sxs-lookup"><span data-stu-id="e7b8e-119">**Query options**</span></span>  
 <span data-ttu-id="e7b8e-120">Permet d'indiquer les options de la requête.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-120">Specify options for the query.</span></span>  <span data-ttu-id="e7b8e-121">Par exemple : $top=5</span><span class="sxs-lookup"><span data-stu-id="e7b8e-121">For example: $top=5</span></span>  
  
 <span data-ttu-id="e7b8e-122">**URL du flux**</span><span class="sxs-lookup"><span data-stu-id="e7b8e-122">**Feed url**</span></span>  
 <span data-ttu-id="e7b8e-123">Affiche l'URL du flux en lecture seule en fonction des options sélectionnées dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-123">Displays the read-only Feed URL based on options you selected on this dialog box.</span></span>  
  
 <span data-ttu-id="e7b8e-124">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="e7b8e-124">**Preview**</span></span>  
 <span data-ttu-id="e7b8e-125">Affichez un aperçu des résultats à l’aide de la boîte de dialogue **Aperçu** .</span><span class="sxs-lookup"><span data-stu-id="e7b8e-125">Preview results by using the **Preview** dialog box.</span></span> <span data-ttu-id="e7b8e-126">L’**Aperçu** peut afficher jusqu’à 20 lignes.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-126">**Preview** can display up to 20 rows.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="e7b8e-127">Options dynamiques</span><span class="sxs-lookup"><span data-stu-id="e7b8e-127">Dynamic Options</span></span>  
  
### <a name="use-collection-or-resource-path--collection"></a><span data-ttu-id="e7b8e-128">Utilisez une collection ou un chemin d'accès de ressource = Collection.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-128">Use collection or resource path = Collection</span></span>  
 <span data-ttu-id="e7b8e-129">**Collection**</span><span class="sxs-lookup"><span data-stu-id="e7b8e-129">**Collection**</span></span>  
 <span data-ttu-id="e7b8e-130">Sélectionnez une collection dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-130">Select a collection from the drop-down list.</span></span>  
  
### <a name="use-collection-or-resource-path--resource-path"></a><span data-ttu-id="e7b8e-131">Utilisez une collection ou un chemin d'accès de ressource = Resource Path.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-131">Use collection or resource path = Resource Path</span></span>  
 <span data-ttu-id="e7b8e-132">**Chemin de la ressource**</span><span class="sxs-lookup"><span data-stu-id="e7b8e-132">**Resource path**</span></span>  
 <span data-ttu-id="e7b8e-133">Type de chemin d'accès de ressource.</span><span class="sxs-lookup"><span data-stu-id="e7b8e-133">Type a resource path.</span></span> <span data-ttu-id="e7b8e-134">Par exemple : Employees</span><span class="sxs-lookup"><span data-stu-id="e7b8e-134">For example: Employees</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b8e-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7b8e-135">See Also</span></span>  
 <span data-ttu-id="e7b8e-136">[Éditeur de source OData &#40;page colonnes&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="e7b8e-136">[OData Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="e7b8e-137">[Éditeur de source OData &#40;page sortie d’erreur&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="e7b8e-137">[OData Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="e7b8e-138">Gestionnaire de connexions OData</span><span class="sxs-lookup"><span data-stu-id="e7b8e-138">OData Connection Manager</span></span>](connection-manager/odata-connection-manager.md)  
  
  
